---
title: "Train Tracker"
date: 2025-01-05T22:15:48Z
draft: false
---

![Denver Union Station Train Platform](/images/train-tracker/station.png)

I happen to live right near Denver's Union Station, so my days are punctuated by the bells of Amtrak and Denver Transit trains just outside my window. I found myself consistently curious about which trains were coming and going and figured there had to be some sort of public data to get me those answers. In reality, things were a bit trickier to nail down.

# Amtrak

![Amtrak Train Map](/images/train-tracker/amtrak-map.png)

Amtrak publishes current position and schedule of their trains on a [map on their website](https://www.amtrak.com/track-your-train.html), so clearly train data is available somewhere. Unfortunately, they don't make it easy to find with a public API. Luckily, I'm not the first person to have this thought - Greg Walker did some sleuthing on how the map is populated and pubished his findings in [a great blog post](https://mgwalker.github.io/blog/amtrak-api/).

Effectively, the train position data is encrypted when fetched by the map application, but the encryption keys are also readily recoverable by working back through some intentionally obfuscated logic and variable names. Even more bizarrely, all of this logic is thoroughly (and sarcastically) described in comments in the original javascript. Some highlights:

```js
//FAKE VARIABLES to throw off people hahahahaha
```

```js
// cw: xxx - Dwell time bug lurks here.
```

```js
// I crib this shamelessly from SO...because it is so useful!!
```

And finally, the complete instructions for how to decrypt the train position data:
```js
/*MasterSegment is the length of the string at the end of the encrypted data that contains the secret key
 To decrypt - we do the following
1. Take masterSegment (88) length - from the right of the data - this has the private key
2. Everything from 0 to the end - master segment is the raw data - that needs to be decrypted
3. Decrypt the 88 characters using the public key - that will give you a pipe separated string of the private key (random guid from MDS) and a time stamp (to scramble it)
4. Now use the private key and decrypt the data stored from step 2.
5. Parse the decrypted data - and rejoice
6. KSUE -means key issue
7. __$$_jmd - the public key that we obtain
```

Thanks to this post, I took some fairly trivial steps to rewrite the decryption in python. The Amtrak data is fairly comprehensive, reporting each train's route, the stations on that route, and both scheduled, predicted, and actual times for arriving and departing those stations.

From there, I can limit to just trains that come through Denver (currently just the California Zephyr from Chicago to San Francisco) and focus on the predicted and actual times of arrival and departure in Denver.

# RTD GTFS

The Denver public transit agency, RTD, publishes [schedule and vehicle position data](https://www.rtd-denver.com/open-records/open-spatial-information/gtfs) via the General Transit Feed Specification (GTFS) standard. The story behind the standard is itself fairly interesting - before Google attempted to incorporate transit data into its maps, there was no standard for publishing timetables or positions. Google provided a standard specification for all transit agencies to adopt so that their timetables could be incorporated into Google Maps directions. This led to near-universal adoption across transit agencies, many of whom (including Denver) also make that data freely available in its raw form for analysis.

I grabbed the real-time vehicle position data feed, which gives me the latitude and longitude of active vehicles by route. The tracks I can see serve 4 commuter rail lines that radiate out from downtown. Critically, all 4 routes converge on a roughly 700m long straight section of track as they pull into Union Station, so I can identify which trains are arriving, sitting in the station, or departing just by checking whether their positions cross a boundary 200m away from me between successive updates of their positions.

This all works great, but unfortunately the GTFS data from these lines is roughly 5 minutes delayed, so really this is only good for telling me which train arrived 5 minutes ago rather than just now as intended. This seems to be limited just to these lines - buses and light rail have positions update much more rapidly, so I'll keep an eye on this delay and see if the data can be made more useful.

# Train Tracker

Pulling this all together, I ended up with a quick python script that can pull relevant arrival and departure times for the trains outside of my window so I can see in a glance what's happening out there. To make it real, I display the results on an e-ink display powered by a Raspberry Pi Zero 2W, refreshing periodically via a simple cron job. Since the RTD data is so delayed, I actually cut that out for now to focus just on Amtrak until it gets a bit closer to real time position reporting.

![Train status display](/images/train-tracker/tracker.png)

### Code

[https://github.com/brasich/train-outside/tree/main](https://github.com/brasich/train-outside/tree/main)
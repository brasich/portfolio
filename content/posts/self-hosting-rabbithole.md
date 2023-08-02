---
title: "Self Hosting Rabbithole"
date: 2023-07-03T18:09:18-04:00
draft: false
---

An alternative title might be **'Who Knew Doomsday Prepping Would Be Fun?'**. 


Winter and spring of 2023 have been an absurd time to be on the internet. We've seen Twitter acquired by Elon Musk and subsequently [run](https://mashable.com/article/twitter-api-elon-musk-developer-issues-apps) [into](https://www.theverge.com/2023/6/30/23779764/twitter-blocks-unregistered-users-account-tweets) [the](https://www.theverge.com/2023/7/1/23781198/twitter-daily-reading-limit-elon-musk-verified-paywall) [ground](https://www.theverge.com/2023/7/3/23783092/twitter-tweetdeck-new-preview-force-legacy-apis). At the exact same time, Reddit's [expensive new API pricing (complete with 30-day adoption timeline)](https://www.theverge.com/2023/6/13/23759180/reddit-protest-private-apollo-christian-selig-subreddit) and following [hostile reaction to community protest among unpaid moderators](https://www.theverge.com/23779477/reddit-protest-blackouts-crushed), place it at the same precipice.

I won't get into the fact that this was inevitable, or that I should have seen it coming, or that it happens to every social platform as it crashes into the need to make money, mainly because others have done a much better job expressing it:
+ [TikTok's Enshittification - Cory Doctorow](https://pluralistic.net/2023/01/21/potemkin-ai/)
+ [Stop Talking to Each Other and Start Buying Things - Catherynne M. Valente](https://catvalente.substack.com/p/stop-talking-to-each-other-and-start)

Still, it's been a shocking reminder that for so many people who use on the internet for community, entertainment, art, and work, reliance on a monolithic platform can be catastrophic. When one man over-pays for Twitter as a half-joke he can't back out of, his need to see a return means I can't talk to my friends across the country about the latest Righteous Gemstones episode without running into a paywall. When Reddit decides it's time to ramp up for an IPO, it means I can't use a tracker-free 3rd party app to keep up with reactions to the day's F1 race.

These decisions on the parts of these business make total sense - interest rates are up, investor money is no longer free, so it's time to flip the mytical switch to profitability. Everything costs, and a place to share Alex Albon memes isn't an inalienable right. 

Couple all of this with how slow and painful the modern web has become to navigate: Try to search for a recipe and it'll be buried beneath 1000 words of seo-optimized narrative, ad placements, cookie consent pop-ups - laptop fans ramping up as the browser chugs through dozens of external advertiser and analytics tracking scripts. To my eye, it doesn't need to be this way. We don't need cookie consent pop-ups if our sites don't need to use tracking cookies. We don't need tracking cookies if we don't need as much advertising. We don't need as much advertising if our costs are lower. We don't face as high hosting costs if our sites our simpler.

The way forward, is actually backwards. I've been hosting this blog on GitHub Pages as a static site generated with Hugo. Back when I started, it was just because that was the easiest and cheapest way I could build something I had complete control over while still learning useful skills. Now, though, I've been using some time that has been graciously returned to me by the twitter paywall to go even deeper. Turns out there are a number of people and organizations thinking along the same lines: 
+ [The Small Web is Beautiful - Ben Hoyt](https://benhoyt.com/writings/the-small-web-is-beautiful/)
+ [IndieWeb](https://indieweb.org)

None of these concepts are new. In the days before Reddit became the 1-stop shop, I would methodically hop between a couple dozen blogs and RSS feeds to get news, thoughts, musings, etc. on topics I cared about from sources I trusted. When I had an issue with my car, I could go on an entire forum dedicated specifically to owners of 1st generation Ford Escapes and get answers. It all loaded fast, ads were minimal, life was good. Those tools never went away, they just went out of style, and maybe it's time to bring them back.

Moving one step beyond my previous GitHub Pages deployment, this blog is self-hosted on a Raspberry Pi 4. The static Hugo site is served via Caddy through a Cloudflare Tunnel. The only analytics are done via access logs, locally parsed with GoAccess to give hit count statistics. Getting this all up and running was easier than I expected - maybe a couple of hours of actual time on the keyboard even as a beginner.  At the end of it all, it's so cool to pull up this site knowing that behind it all is a tiny little computer sitting on my desk sipping a couple watts, serving this site a couple dollars a year in electricity, with all of its data completely my own.

Once I'm comfortable it's all working, I might have to put together a quick tutorial for this full `rpi/hugo/caddy/cloudflare` stack.

To Do:
+ Migrate from SD Card to SSD [Done]
+ Run caddy and goaccess in docker containers to start running additional services alongside
+ Real-time HTML report access log monitoring [Done]
+ Point benrasich.com to this as well (currently just running on a domain I have for tinkering on) [Done]
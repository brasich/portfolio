---
title: "UT MSDS in Review"
date: 2023-12-15T17:15:04-05:00
draft: false
---

Back in early 2022, I [posted my thoughts after my first semester in the University of Texas Data Science master's program](/posts/online-data-science-masters/). Now, almost 2 years on, I've just wrapped up my last exam; the only thing left to do is wait for my diploma to show up in the mail and watch the Longhorns win the national championship. 

Looking back, this was absolutely a worthwhile experience and I'm glad to have taken on the challenge. From the outset, I was hoping this program would prove to be an antidote to imposter syndrome, as well as a sort of creative outlet to try new techniques that weren't necessarily well-suited to the types of problems I encounter at work. With few exceptions, each course certainly helped in those areas.

## Courses

**Machine Learning  - Fall '21**

Some separation from the 20-hour problem sets makes it easier to view this class with rose-tinted glasses, but it's definitely been helpful. While it never advanced beyond theory and toy datasets, working through the nuts and bolts of foundational ML building blocks on paper has given me the vocabulary I lacked to open the black box to stakeholders who are worried about trusting "magic" like `xgboost`.

**Probability and Simulation-Based Inference - Fall '21**

The span of the content didn't cover much beyond my undergrad stats classes, but the simulation-based techniques were eye-opening. Not only did they help advance my intuitive understanding of frequentist concepts I had only known through formulas before, but I used my own spin on them to great effect when having to do a presentation on the inner workings of a causal inference framework I built. 

**Foundations of Regression and Predictive Modeling - Spring '22**

This class was a heavily theory-based survey of parametric and non-parametric regression. I appreciated the content, but to me one of the key concepts in this area is balancing over/underfitting - especially in the choice between parametric and non-parametric families of models. This class heavily relied on simulated data with no real examples, so to me that message fell somewhat flat.

**Data Exploration and Visualization - Spring '22**

Making and looking at graphs is truly tough to beat, and this class was a joy. While it was taught in `R`, the concepts are obviously universal. Didn't learn anything groundbreaking here (beyond some jealousy of the simple syntax of `ggplot2` that I can't transfer to `pyplot`-land), but had a lot of fun.

**Data Structures and Algorithms - Spring '22**

Of the three classes I took in the spring of 2022, this was by far the most demanding, but was also quite rewarding. The assignments and quizzes were hard but fair, and they advanced my skills as a programmer by leaps and bounds.

**Advanced Predictive Models for Complex Data - Summer '22**

Another survey course that I feel suffered for its attempted breadth. Each of the topics covered (time series, spatial, spectral clustering, and network models) could have merited a course of their own. Still, this was a helpful class, and I'll be better equipped to do my own deep dives into these topics as needed when I see practical applications.

**Deep Learning - Fall '22**

A sharp and refreshing contrast from the toy/simulated datasets in prior courses, this class used data from frames of gameplay of [SuperTuxKart](https://en.wikipedia.org/wiki/SuperTuxKart) to allow us to build a portfolio of increasingly complex deep learning projects. Starting from simple image classification, we progressed to real-time object recognition, then finally built an AI agent, trained via PPO, to compete against other students' agents in a tournament. 

**Natural Language Processing - Fall '22**

Talk about timing - this was an incredible class to take in the fall/winter of 2022, right as Chat-GPT 3.5 and its competitors were starting to gather steam. Understanding how the underlying transformer architecture works, along with the human-in-the-loop reinforcement learning used to fine-tune the outputs, was critical as I looked to cut through the hype cycle around these products.

**Optimization - Spring '23**

Not my favorite - lectures made some interesting material feel like a series of unrelated linear algebra brainteasers until we finally made it to Gradient Descent and other topics with motivating uses in DS. 

**Design Principles and Causal Inference - Fall '23**

If I had to choose just one class from the program to take, this would be the one. The assessments were frustrating given the subjectivity of the subject matter, but - grading aside - this class was incredible. 

Compared to time spent writing code or fitting models, I spend easily as much time (if not more) advocating for buy-in on sound test design and model interpretations from non-technical business folks. That part of the job is far more art than science, and can be entirely devoid of rigor if it is allowed to be. This class gave me a framework and vocabulary to engage in those conversations with more confident backing, as well as a clearer understanding the types of trade-offs and assumptions involved.

## Parting Thoughts

When deciding to dive into this program, I found myself wishing for a simple case statement that would tell me if I should give it a go or not. Obviously it's too personal a decision for that to be possible, but if I had to tally up some points for and points against based on my experience, here's where I'd land:

**Points For**  
- Satisfying, productive intellectual challenge
- Hands-on experience with cutting edge techniques, especially in Deep Learning and NLP classes
- [Relatively] cheap/free - even at sticker price without employer tuition reimbursement, $10k for a masters degree vastly undercuts in-person options

**Points Against**
- Spotty class availability - I planned on finishing in 2 years rather than 2.5, but the final class I needed to graduate wasn't available in the summer session of 2023
- In grading and instructor attention, you get what you pay for. In the vast majority of cases, huge class sizes weren't an issue, but subjects like Causal Inference would have massively benefited from live discussions that simply aren't possible in the MOOC setting.

All in all, while I'll absolutely be enjoying some additional free time now that I'm done, I had a great experience and don't regret it in the slightest.
---
title: Why I Built a Conditions App Instead of Another Weather App
date: 2026-02-28
subtitle: Turning repeated forecast-checking into a simple conditions decision.
excerpt: "I didn’t wake up wanting to build a weather app. I was trying to answer one question: when and where are the conditions good for what I want to do?"
---

I didn’t wake up wanting to build a weather app.

If anything, I’ve spent years trying *not* to think about weather... and then doing exactly that anyway. I’ve been involved in airsports for a long time (paragliding, skydiving, speedflying, and more recently BASE), and if you do anything wind-dependent in the UK you end up with the same slightly silly routine.

You check one app. Then another. Then you switch models because they don’t agree. You look at gust spread. You look at wind at height. You check rain radar. You do it again later because maybe it’s shifted. You tell yourself you’re “just having a quick look” and twenty minutes disappears.

At some point it clicked that I wasn’t actually interested in weather. I was trying to answer one question:

**When and where are the conditions good for what I want to do?**

Everything else was me manually interpreting numbers to get to that answer.

## The small annoying loop

As a developer, the repetitive loops are the ones that start to itch. Not the grand problems. The small ones that steal time and attention every single week.

In most areas of software we’ve moved beyond “here’s the raw information, good luck”. Accounting tools don’t just list transactions, they forecast cashflow. Budgeting apps don’t just show balances, they tell you if you’re on track. Sat-nav doesn’t just display a map, it tells you the route and when to leave.

They take data and turn it into a decision.

Weather apps, for the most part, still stop one step earlier. They give you wind speed, direction, gusts, rain percentages, daylight, and you’re the one who has to synthesise it. Again. Tomorrow. And the day after.

That gap between data and decision felt oddly untouched.

## The first version was a script (of course it was)

This didn’t start as a “product”. It started as a hack.

I wrote a small script that pulled forecast data from an API, ran it through a few rules (wind under X, direction between Y and Z, no rain), and pinged my phone if everything lined up.

It worked. Properly useful.

It was also brittle and a bit embarrassing. Adding locations was a faff. Tweaking conditions was annoying. Sharing it with friends basically meant copying numbers into a WhatsApp chat and hoping nobody argued about which model to trust.

It was helpful for me, but it wasn’t something I could tell other people to use without apologising first.

## The mistake I made (and corrected)

A couple of years ago I started building it properly as an iOS app. I’m an iOS engineer professionally, so technically it wasn’t the hard part.

The hard part was me doing the usual builder thing: overthinking it.

Should it show forecasts too? Should it have maps? Should it support every weather variable? Should it be cross-platform from day one? Should it do *everything*?

That version stalled, mostly because the scope grew faster than my free time.

Recently I picked it back up with a stricter rule:

**Build the smallest version that genuinely replaces the checking habit.**

That meant stripping it back. No radar. No scrolling charts. No trying to be Windy.

Just:
- define your conditions
- choose a location
- get notified when they line up

That’s it.

## It doesn’t need to be perfect

Forecasting is probabilistic. Models disagree. Conditions shift.

I’m using more than one model and I’ll keep tweaking how it evaluates and compares them over time, but it doesn’t need to eliminate uncertainty. It just needs to cut down the constant manual checking.

If it takes you from opening weather apps six times a day to once, that’s already a win. If it helps you notice a decent window you’d have missed, even better.

## A quick technical aside (because I can’t help myself)

The interesting part of this isn’t exotic tech. It’s mostly boring, which I mean as a compliment.

It’s a straightforward iOS app with a simple backend that polls weather APIs, normalises the data, evaluates rule sets, and triggers notifications when conditions match. The “hard” bit is mostly product judgement: what to include, what to ignore, and how to present confidence without pretending certainty exists.

It also deep links out to other weather apps, because I’m not trying to replace them. I just want something that tells me when it’s worth looking more closely.

## Indie by design

This isn’t a venture-scale idea and it’s not meant to be.

It’s a focused utility. If it quietly earns enough to fund its own infrastructure and a bit extra on top, that’s a good trade for something I use myself. Indie software that pays its way is underrated.

## A builder question

If you build software, it’s worth paying attention to the loops you run in your own head every day.

What are you manually checking? What are you repeatedly interpreting? What decision are you synthesising from raw inputs?

That’s often where the interesting products live.

If you’re curious about the app this turned into, it’s here: [primewindow.app](https://primewindow.app) (iOS-only for now; other platforms can wait).

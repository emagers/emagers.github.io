---
layout: post
title:  "Web Analytics - Part 1"
date:   2023-04-22 10:17:59 -0800
categories: web-analytics
tags: web-analytics performance browsers tracking
---
{% include scripts.html %}

Although GitHub has made personal blogging very easy with the GitHub pages ecosystem, one thing which is lacking is analytics to understand who is visiting your blog, where they're coming from, what they're doing once here, and what blogs/pages are interesting to them.

Web analytics are useful for content creators, marketers, or anyone who needs to understand who is consuming their products and who needs to optimize future releases accordingly. For example, an engineering team might want to use web analytics to understand the impact of a new feature; a marketing team might use these analytics to track click-through rates of an email campaign to ensure that they're targeting the correct demographics; and a content creator may use content views as a metric to help decide what type of content to make in the future.

So while some may find the tracking involved with web analytics creepy (and it definitely can be), this is something I'd like to incorporate so that I can track the blog's growth and impact.

## Options

When searching for open-source web analytic tools, I found a lot. There seem to be very robust options out there which allow you to host it yourself or pay for cloud hosting. There are also 3rd party options such as Google Analytics which can complicate things if you're wanting to comply with legislation concerning the use of 3rd party cookies and use of personal data.

When choosing what to do I considered the following:
1. Minimal cost.
   * This blog is very small and does not need a robust solution that will allow it to scale infinitely.
2. No 3rd party cookies or data handling.
   * I never want my readers to have to deal with trying to understand complicated cookie notices or worry that their data is going to be misused or sold to some partner.
3. Data anonymization.
   * Related to the second point, but I don't care to know *who* you are, just how you're interacting with the site.

A lot of the open-source options could fit the bill when self-hosted, but if I'm going to self-host some system, I would much rather have it fine-tuned to exactly what I want to avoid any unnecessary overhead. Ultimately, I have decided to build a small solution myself that is tailored to exactly what I'm interested in tracking. This also gives me a chance to learn more about how the client-side trackers work and how things such as session identifier resolutions work when users are deleting or blocking cookies.

## Scope

* As mentioned earlier, I am only interested in tracking behavior across single sessions - I do not want or need to track users across multiple sessions.
* Able to handle existing traffic, though I don't know yet how much traffic the blog is currently getting (and one of the many reasons for this project). To provide some metrics to measure, I'll be very liberal and say 100 concurrent users each making 25 requests per minute (or roughly 42 requests per second). Hopefully, those requests per minute for a single user are never the case as I want people reading and not clicking aimlessly around the site, but it at least gives me a goal to benchmark against that will be applicable for some amount of growth.
* No PII is persisted (names, emails, IP addresses, etc.).
* What I do want to track:
   * Referring sites
   * What pages are visited
   * How long is spent on a page
   * Page performance data (how long did it take to download, how long it took to render, etc.)
   * What browsers people are using
   * What type of device are people using
   * What country/state/city are people viewing from
* Rate limiting to protect against gross misuse if it ever occurs (since I'm putting it on the internet, it likely will).
* Simplistic UI that will allow for reporting of the above data points on a daily, monthly, and yearly basis. live data streams are not needed, being able to see any day's metrics the next day is good enough.
* It will be hosted in Azure to take advantage of monthly free credits, so the hosting cost should not exceed that.
* Deployments should be scriptable and automated.

## Not in scope

* Robust scaling
   * With scale comes a cost, and with solutions that scale comes additional cost. I will follow patterns that can scale, but the scaling itself will not be a part of this effort.
   * As an example, if there is some distributed attack I would prefer the system to fail under the load and accept the missing data rather than scale to handle the attack or stress about adding firewall rules to prevent an ongoing attack. This is a personal pet project, not something I want to have to feel like I'm on-call for support.

## What's next

So there is a lot to do, I plan to get to it! I'll be spending some time organizing and planning out the work before jumping in. I'll also provide updates as I go, sharing whatever designs I come up with or any significant milestones.

Until then, thanks for reading!
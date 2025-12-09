---
title: "How to take effective architecture decisions"
slug: "architecture-decision"
date: 2025-12-06
draft: false
description: "A practical introduction to making architecture decisions based on facts, not opinions."
tags: ["Architecture"]
categories: ["tech"]
series: ["Architecture knowledge management"]
series_order: 3
---

In software architecture, every choice matters, but some decisions shape the
system more than others. These are called **architecture decisions (ADs)**,
and they define how your system will meet its most important requirements.

Taking the right decision isn’t about guessing or following the loudest voice
in the room. It’s about **analyzing options, weighing facts, and being free**
**from bias**.

## What is an AD ?

An architecture decision is a software design choice that addresses a list of
[significant requirements (ASRs)](/posts/architecturally-significant-requirement).

It may be a system-wide decision or a local decision, so the people involved
may be different, but the way the decision is made is the same. The role of
architects in an organization is a complex topic I’ll explore later, yet it’s
crucial that anyone on the engineering teams feels empowered to propose ideas
and take part in shaping these decisions.

## How to take an AD ?

> [!quote] Architecting is much more than decomposition.</br>Decomposition is easy, integration is difficult.

A decision must be taken based on facts and start from problem. In order to
avoid any bias, it is important to follow a strict methodology.

![architecture decision process](architecture_decision.svg)

During the analysis stage, all solutions, even the stupid ones, must be
analyzed.

During the decision step, it is important to search _consent rather than_
_consensus_ which means that we do not try to get everyone to agree but try to
have no one against the decision.

In general, a meeting may be suitable, even though by nature it requires
synchronous communication. However, it’s also entirely possible to make this
process fully asynchronous, as long as responses remain timely.

> [!tip]
> Limit the number of participants to only those who are truly necessary. This
> makes discussions smoother, more effective, and faster, regardless of the
> communication mode.

Before closing this article, I’d like to highlight the final step of the
process, which is crucial but often overlooked. Monitoring the outcome allows
you to address any unexpected effects and contributes to a culture of
continuous improvement. This monitoring should include clearly defined metrics
to measure success. It’s therefore wise to establish these metrics, set the
monitoring period at the time of the decision, and plan the review in advance.

In the next article, we’ll look at how to ensure this decision is properly
tracked.

{{< article link="/posts/architecture-decision-record/" showSummary=true compactSummary=true >}}

> [!info] Some links for further reading
> - https://adr.github.io/ad-practices/
> - https://www.gaudisite.nl/ArchitecturalDecisionMakingSlides.pdf
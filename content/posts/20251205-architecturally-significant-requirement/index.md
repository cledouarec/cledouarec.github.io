---
title: "ASR: The real driver behind every architecture decision"
slug: "architecturally-significant-requirement"
date: 2025-12-05
draft: false
description: "A practical guide to understanding and prioritizing architecturally significant requirements."
tags: ["Architecture"]
categories: ["tech"]
series: ["Architecture knowledge management"]
series_order: 2
---

Not every requirement shapes the way a system is built, but some leave a
lasting mark on the architecture. These are the requirements that really
matter, what architects call **architecturally significant requirements**
**(ASRs)**.

Spotting them early is key because they influence critical decisions, affect
performance, and sometimes make or break a project. In this article, we’ll
break down what ASRs are, why they deserve special attention, and how to
prioritize them objectively to guide your architecture in the right direction.

## What is an ASR ?

An ASR is a requirement that has a measurable effect on a software system’s
architecture.

Identifying these needs is essential to making an informed decision. Each time
an [architecture decision (AD)](/posts/architecture-decision) is taken an
[architecture decision record (ADR)](/posts/architecture-decision-record) will
be produced.

## Why identify most important ASRs ?

> [!warning] An ASR can have a different value at different times.

For example, a requirement related to a memory usage only becomes critical when
approaching the limit that's why a priorization must be defined.

The criteria used to priorize the ASRs can be grouped into several broad
categories:
- Project
- Performance
- Dependencies

### Project

- The requirement is directly associated with high business value (benefit vs.
  cost) or business risk.
- The requirement is a concern of a particularly important stakeholder such as
  the project sponsor or an external compliance auditor.
- The requirement has been troublesome and caused critical situations, budget
  overruns or client dissatisfaction on a previous project in a similar
  context.

### Performance

- The requirement includes runtime Quality-of-Service (QoS) characteristics
  (such as performance needs) that deviate from those already satisfied by the
  evolving architecture substantially.

### Dependencies

- The requirement causes new or deals with one or more existing external
  dependencies that might have unpredictable, unreliable and/or uncontrollable
  behavior.
- The requirement has a cross-cutting nature and therefore affects multiple
  parts of the system and their interactions; it may even have system-wide
  impact, short term and/or in the long run (examples: security,
  monitoring).
- The requirement has a First-of-a-Kind (FOAK) character. For instance, this
  team has never built a component or subsystem that satisfies this particular
  requirement before.

## How to prioritize ASRs in practice ?

Now that we have our evaluation criteria, we can create a table to score each
ASR.

![requirements assessment table](architecturally_significant_requirement.svg)

One option to fill the cells in such a table are basic values such as:
- High = 5
- Medium = 2
- Low = 1
- NA = 0

> [!tip]
> You can also use the Fibonacci scale, especially if you want more
> granularity.

The score obtained allows us to obtain an objective classification which should
be systematically re-evaluated.

Now that we’ve defined objective criteria, it’s time to move on to the
decision-making process itself.

{{< article link="/posts/architecture-decision/" showSummary=true compactSummary=true >}}

> [!info] Some links for further reading
> - https://www.ozimmer.ch/practices/2020/09/24/ASRTestECSADecisions.html
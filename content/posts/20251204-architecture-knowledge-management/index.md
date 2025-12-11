---
title: "Stop blaming architecture: understand the decisions behind it"
slug: "architecture-knowledge-management"
date: 2025-12-04
draft: false
description: "Learn how to document architecture decisions effectively and preserve the reasoning behind them for your future self and your team."
tags: ["Architecture"]
categories: ["tech"]
series: ["Architecture knowledge management"]
series_order: 1
---

You’ve probably heard someone complain about an architectural decision:
> [!quote] Why did we make this choice? It doesn’t make any sense!

Yet at the time it was made, the decision was perfectly reasonable, whether due
to time-to-market pressure, compatibility requirements, or other contextual
factors.

In this series of articles, we’ll explore several key concepts that help
structure and manage architectural knowledge. The goal is simple: to capture,
share, and track architectural decisions so that anyone can understand not only
what was decided, but also why it made sense at the time.

## What is an architecture knowledge management ?

An architecture knowledge management (AKM) is designed to **store**,
**organize**, and **distribute architecture knowledge** within an organization.

![diagram representing the flow of an archtecture decision](architecture_knowledge_management.svg)

In simple terms, the main objective is to document an [architecture decision (AD)](/posts/architecture-decision)
based on an [architecturally significant requirement (ASR)](/posts/architecturally-significant-requirement)
within an [architecture decision record (ADR)](/posts/architecture-decision-record).
All ADRs are then gathered in an [architecture decision log (ADL)](/posts/architecture-decision-log).

The core element is therefore the creation of an ADR, as it’s what will allow
us to understand today’s choices later on. In the next article, we’ll introduce
the concept of an ASR, which is not as straightforward as it might seem.

{{< article link="/posts/architecturally-significant-requirement/" showSummary=true compactSummary=true >}}

> [!info] Some links for further reading
> - https://adr.github.io
> - https://github.com/joelparkerhenderson/architecture-decision-record
> - https://martinfowler.com/articles/scaling-architecture-conversationally.html
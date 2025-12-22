---
title: "Mordor Services - One Ring, one launch"
slug: "communication-flow-use-case"
date: 2025-12-22
draft: false
description: "A practical case study on improving communication flows in a mid-size tech company."
tags: ["use case"]
categories: ["organization"]
series: ["Team structure"]
series_order: 2
---

## Use case

### Company context

Mordor Services is a mid-size tech company of about 240 employees designing and
manufacturing connected IoT devices, best known for its flagship product:
**a smart connected ring** used for authentication, access control, and secure
interactions with digital systems.

The product combines:
- Hardware (the physical ring),
- Firmware,
- Mobile apps,
- Cloud services.

> [!abstract] It is sold as one integrated solutions
> One Ring to authenticate them all,</br>
> One App to guide them,</br>
> One Cloud to bind them,</br>
> And in production ship them.

The company is organized around:
- The Council (CEO, COO, CTO, Head of Sales),
- Product Management,
- Hardware Engineering,
- Software & Cloud Engineering,
- Manufacturing & Supply Chain,
- Sales & Partnerships,
- Customer Support & Operations.

Mordor Services prides itself on building _simple objects backed by powerful_
_systems_.
Internally, people joke that _the Ring may be small, but the path to ship it_
_is long_.

### The situation

Mordor Services is preparing the launch of a new generation of its connected
ring, introducing:
- longer battery life,
- stronger encryption,
- deeper integration with enterprise systems.

The new ring has already been demonstrated to key customers and partners. Some
contracts and renewals explicitly depend on its availability.

Sensing competitive pressure from other wearable vendors and startups beyond
the _Black Gate_, the Council decides to move the launch date forward by one
month. The decision is announced during a company-wide meeting.

The message is clear in spirit:
- the launch is critical,
- the market will not wait,
- Mordor Services must move as one.

What is less clear:
- which features are mandatory for launch,
- which can be deferred,
- how hardware, firmware, and software trade-offs should be handled.

No written decree follows. Everyone leaves believing they understand the
mission.

### Many crafts, one Ring

Product managers interpret the message as a firm commitment:
> [!quote] The new Ring must ship with all promised capabilities, ensuring that its form, function, and magic remain intact.

They compress the roadmap and assume the full feature set remains unchanged.

Hardware engineers see immediate constraints:
- supplier lead times,
- manufacturing yield risks,
- battery limitations.

Quietly, they decide to freeze certain design elements earlier than planned to
avoid production delays.

Software and firmware teams, meanwhile, continue developing advanced features
demonstrated in early prototypes, assuming the hardware will fully support
them.

Manufacturing prepares based on the latest approved hardware design, unaware
that some software-dependent features may not survive.

Sales reassures customers and partners:
> [!quote] The new Ring will arrive sooner, exactly as you’ve seen it.

Each group believes it is protecting the Ring. Each carries a different
understanding of what the Ring actually is.

### A flaw in the forge

Midway through development, hardware engineers discover an issue:
under certain conditions, the new encryption module increases power
consumption, threatening battery life and long-term reliability.

The issue is discussed within the hardware team and raised to their manager.
Concerned about triggering a wider redesign, escalation is delayed in the hope
that a workaround can be found.

Weeks pass. The launch date approaches. The risk remains.
When the issue finally reaches the Council, manufacturing timelines are already
committed.

From the Council:
> [!question] How was this not forged out earlier?

From engineering:
> [!quote] It was known. But the warning never left the forge.

### Short paths, long consequences

As pressure increases, informal communication spreads. A partner manager
contacts a firmware engineer directly:
> [!question] Off the record, does the Ring really support this mode?

The engineer answers honestly. Product is not informed.

Similar shortcuts multiply:
- Sales speaks directly to engineers,
- Engineers provide caveated answers,
- Product learns of commitments after partners repeat them as facts.

Promises are made ring by ring, conversation by conversation.

### The Eye over the factory

To avoid further surprises, more people begin copying the CTO on emails, chats,
and design documents.

Gradually, the CTO becomes the Eye above the forge:
- approving hardware changes,
- validating feature trade-offs,
- arbitrating launch readiness.

When the Eye is watching, decisions move. When it turns elsewhere:
- teams wait,
- manufacturing hesitates,
- software pauses deployments.

What began as oversight becomes a bottleneck.

### The final assembly

As launch approaches:
- partners receive different answers depending on who they ask,
- Product spends its time reconciling versions of the Ring,
- Engineering works under constant urgency,
- Manufacturing locks decisions earlier than desired,
- The Council senses growing risk.

Everyone agrees the Ring must ship. No one agrees which version of the Ring
they are truly building.

## Communication flow analysis

### Downward communication

This use case illustrates a downward communication flow originating at the
Council and spreading across the organization.

> [!abstract] Expected role
> Downward communication should:
> - clarify intent and priorities,
> - define non-negotiables and constraints,
> - establish decision boundaries.

> [!note] Observed behavior
> The Council announces an accelerated launch in a company-wide meeting. The
> message emphasizes urgency and unity but lacks operational detail.
>
> No written follow-up clarifies:
> - mandatory features,
> - acceptable trade-offs,
> - decision ownership.

> [!error] Issues
> As a result, teams interpret the same message differently. Product assumes
> the full feature set must ship. Engineering assumes compromises are
> acceptable. Manufacturing freezes designs early. Sales assumes the
> demonstrated version remains the reference.

> [!conclusion]
> The issue is not a lack of communication, but a lack of operational clarity.
> Strategy is communicated as intent rather than as actionable guidance.

### Upward communication

In this scenario, information moves upward from the teams to the Council,
allowing leadership to receive signals and potential risks.

> [!abstract] Expected role
> Upward communication should:
> - surface risks early,
> - enable informed leadership decisions,
> - transmit signals without filtering.

> [!note] Observed behavior
> In this case, hardware engineers identify a power-consumption issue that
> threatens battery life and long-term reliability. The issue is discussed
> within the team and raised to management, but escalation is delayed to avoid
> triggering a redesign or schedule impact.

> [!error] Issues
> Risk information is filtered and travels slowly. When the issue finally
> reaches the Council, manufacturing timelines are already committed and
> options are limited.

> [!conclusion]
> Late escalation forces leadership into reactive decisions and creates
> frustration on both sides. Trust erodes because problems appear to surface
> « too late », even though they were known earlier.

### Horizontal communication

Peer teams communicate laterally with one another, forming a horizontal flow
that should support alignment across functions.

> [!abstract] Expected role
> Horizontal communication should:
> - align interpretations,
> - resolve dependencies,
> - maintain a shared understanding.

> [!note] Observed behavior
> Product, hardware, software, manufacturing, and sales work in parallel.
> No structured forum exists to reconcile:
> - feature expectations,
> - technical constraints,
> - production realities.

> [!error] Issues
> Alignment relies on informal exchanges. Decisions are assumed rather than
> validated.

> [!conclusion]
> Misalignment accumulates silently. Differences are discovered late, when
> change becomes expensive or impossible.

### Diagonal communication

Certain messages travel diagonally, cutting across levels and functions to
connect employees who otherwise wouldn’t interact directly.

> [!abstract] Expected role
> Diagonal communication should:
> - be exceptional and transparent,
> - support alignment, not bypass it.

> [!note] Observed behavior
> Under pressure, Sales and partner managers contact engineers directly to
> clarify capabilities. Engineers respond honestly from a technical
> perspective, but without full product context. Product is not informed of
> these exchanges.

> [!error] Issues
> These shortcuts bypass coordination mechanisms and create hidden commitments.
> Customers receive technically accurate but incomplete answers, which later
> become contractual expectations.

> [!conclusion]
> Diagonal communication becomes a coping mechanism for unclear processes,
> increasing inconsistency rather than reducing it.

### Hub-based communication

The CTO acts as a hub in this case, centralizing communication and serving as
the focal point for multiple teams and decisions.

> [!abstract] Expected role
> A hub should:
> - arbitrate rare conflicts,
> - provide temporary alignment,
> - not replace standard flows.

> [!note] Observed behavior
> As uncertainty grows, more people copy the CTO on emails, chats, and
> documents. The CTO increasingly approves hardware changes, validates feature
> trade-offs, and arbitrates launch readiness.

> [!error] Issues
> Decision authority drifts upward. Teams wait instead of deciding.

> [!conclusion]
> What begins as oversight turns into a bottleneck, reducing team autonomy and
> slowing the organization.

### Cross-flow systemic pattern

The dysfunctions reinforce one another:
- Unclear downward communication leads to divergent interpretations.
- Unsafe upward communication delays risk visibility.
- Weak horizontal communication allows inconsistencies to grow.
- Diagonal shortcuts create hidden commitments.
- Hub overload becomes the default coordination mechanism.

> [!error] No single flow fails in isolation.

Communication problems are rarely about people not talking. They are about how
information flows, when it flows, and who is allowed to decide.

This use case demonstrates how capable teams and strong leadership can still
fail without intentional communication design.

## Forging Clear Paths for Communication

At scale, communication must be designed, not improvised. The following
operating principles define how information, decisions, and risks should flow
across the organization to avoid ambiguity, misalignment, and bottlenecks.

### Formalize strategic decisions in writing

Strategic decisions should not live only in meetings or presentations. Every
major decision, such as moving a launch date, must be followed by a short
written summary that clearly defines the objective, the non-negotiable
elements, the acceptable trade-offs, and who owns the decision.

This document becomes the single point of reference for all teams. It removes
ambiguity, limits divergent interpretations, and allows teams to act quickly
without seeking repeated clarification.

By making written decisions the default, the organization improves downward
communication through clarity and consistency, strengthens horizontal alignment
across teams, and reduces unnecessary escalation toward leadership.

### Define explicit escalation rules for risks

Risks should not rely on individual judgment to decide when they deserve
attention. The organization must define clear escalation rules that specify
which types of risks require immediate visibility and at what point escalation
is mandatory.

Any issue that threatens safety, reliability, scope, or delivery timelines
beyond an agreed threshold should be escalated early and explicitly. Escalation
must be treated as a responsibility, not as a failure.

Clear escalation rules improve upward communication by surfacing risks sooner,
enable better leadership decisions, and reduce last-minute interventions driven
by surprise.

### Establish a cross-functional launch forum

Cross-team alignment should not depend on informal conversations or individual
initiative. A standing cross-functional forum must exist to own alignment for
critical initiatives such as product launches.

This forum brings together Product, Engineering, Manufacturing, Sales, and
Support to arbitrate scope, resolve dependencies, and maintain a shared view of
reality. It becomes the default place where trade-offs are discussed and
validated.

By institutionalizing this forum, the organization strengthens horizontal
communication, reduces silent divergence, and ensures that decisions propagate
consistently across teams.

### Make diagonal communication visible by default

Direct, cross-level communication is sometimes necessary for speed, but it
should never remain invisible. Any diagonal exchange that clarifies scope,
commitments, or customer-facing behavior must be summarized and shared with the
relevant stakeholders.

Visibility, not restriction, is the goal. If a decision or clarification is not
visible to Product and the launch forum, it should not be considered valid.

This approach preserves the speed benefits of diagonal communication while
preventing hidden commitments and misalignment across teams.

### Separate decision authority from escalation authority

Leadership should define boundaries, not approve every decision. Teams must
know what they are empowered to decide autonomously and when escalation is
required.

Decision authority should be distributed within clearly documented limits,
while escalation authority remains a mechanism to resolve conflicts or
exceptions. Leaders intervene to adjust boundaries, not to validate routine
choices.

This separation reduces hub overload, restores team autonomy, and allows
decisions to move without waiting for individual availability.

### Maintain a single source of truth for commitments

Conflicting versions of reality emerge when commitments are scattered across
conversations, emails, and presentations. A single, shared reference must exist
to describe what will be delivered, what is deferred, and what is at risk.

This source of truth should be continuously updated and consulted by Product,
Sales, Support, and Engineering before making or confirming commitments.

By centralizing commitments, the organization improves alignment across teams,
limits assumptions, and detects divergence early.

### Shift leadership focus from answers to signals

When leadership primarily rewards certainty and answers, teams learn to filter
information. Leaders should instead encourage early signals, uncertainty, and
incomplete concerns.

By consistently asking what feels risky, what assumptions may be fragile, and
what could surprise the organization, leadership creates space for honest
upward communication.

This shift improves risk visibility, strengthens trust, and reduces the need
for reactive, last-minute decision-making.

## Improvement starts with observation

This use case may appear caricatural, but it reflects situations I have
encountered many times in real organizations. The communication failures
described here are rarely exceptional; they emerge naturally when growth,
pressure, and complexity increase faster than the communication system itself.

The principles proposed to address these issues are not novel or complex. They
are largely common sense. Yet, when applied consistently, they help solve not
only communication problems but many adjacent organizational dysfunctions as
well. For this reason, I intentionally presented both synchronous and
asynchronous variants. I also encourage you to take the time to explore
asynchronous versions of synchronous principles, and vice versa, as a way to
verify your understanding of their differences and their organizational impact.

**There is no universal recipe to take off the shelf**. Instead of copying
practices wholesale, organizations should adopt a continuous improvement
mindset. A PDCA approach, supported by data and observable signals, is far more
effective than static frameworks or fashionable solutions.

Finally, **communication flows should never be optimized in isolation**.
Improving a local flow may make a team faster or more comfortable, but if the
global outcome does not align with the organization’s values and objectives,
the dysfunction will simply reappear elsewhere. Defining what truly matters,
and measuring whether the system moves in that direction, is what ultimately
determines success.

> [!info] Some links for further reading
> - [Using the PDCA Cycle to Support Continuous Improvement (Kaizen)](https://theleanway.net/the-continuous-improvement-cycle-pdca)
> - [How did we shift to asynchronous communication… through baby steps?](https://robin-bonduelle.medium.com/how-did-we-shift-to-asynchronous-communication-through-baby-steps-ce816538afd8)
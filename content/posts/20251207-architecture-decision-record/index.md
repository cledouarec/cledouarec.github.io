---
title: "How to craft an effective ADR"
slug: "architecture-decision-record"
date: 2025-12-07
draft: false
description: "Learn how to capture key architecture decisions clearly and effectively with ADRs."
tags: ["Architecture"]
categories: ["tech"]
series: ["Architecture knowledge management"]
series_order: 4
---

Architecture decisions don’t live in meetings, they live in **ADRs**.
Let’s look at how to craft clear, useful records that stand the test of time.

## What is an ADR ?

An ADR is a document that captures an important [architecture decision (AD)](/posts/architecture-decision)
made along with its context and consequences.

An ADR is the key element of an [architecture knowledge management](/posts/architecture-knowledge-management)
system.

## How to create an ADR ?

An ADR must contain at least the following elements:
- Context
- Deciders
- Decision
- Consequence
- Alternatives

> [!warning]
> Don't alter existing information in an ADR. Instead, amend the ADR by adding
> new information, or supersede the ADR by creating a new ADR.

Each ADR should be about one AD, not multiple ADs.

> [!error] Anti pattern
> _Mega-ADR_: A lot of detailed information about the architecture is stuffed
> into several multi-page ADRs serving as documentation master. For instance,
> component responsibilities and collaborations are specified, or multiple
> diagrams or code snippets appear inside the ADR (one per option is ok
> usually). While such information can be valuable, it should be presented in
> models or documents specifically created for that purpose.

> [!success] Best practice
> Move the detail design to a separate document.

### Context

A description of the context of the situation and the issue raised will assist
in understanding later if the decision should be reconsidered.

It must describe your organization's situation, business priorities and
technological challenge.

The ADR must be dated, this is especially important for aspects that may change
over time, such as costs, schedules, scaling, and the like.

> [!error] Anti pattern
> _Maze_: The ADR topic does not match its content; the discussion derails and
> centers on details that are not relevant in the given context. For instance,
> there is an interesting discussion of the positive attributes of an option
> that has nothing to do with the problem and the relevant stakeholder
> concerns.

> [!success] Best practice
> Refactor the ADR, move less relevant parts to an appendix or _parking lot_
> (if you are not ready to scrap them).

### Deciders

The decision makers should be identified, which helps to make them accountable
for decision enforcement.

### Decision

The decision made must be written in a simple but precise manner. The objective
is to see the action taken as a result of the discussion.

> [!error] Anti pattern
> _Fairy Tale_ (aka Wishful Thinking): A shallow justification is given, for
> instance only pros but no cons. Special cases of this anti-pattern are
> truisms and tautologies.
>
> > [!example]
> > We decided for a load balancer because it balances load, which is a good
> > thing.

> [!error] Anti pattern
> _Sales Pitch_: Avoid exaggerations and bragging. Always be ready to answer
> questions about claims and their evidence. Including all related background
> information would bloat the ADR; hyperlinks or bibliographic references can
> be provided instead.
>
> > [!example] Example (exaggerated intentionally):
> > We chose this outstanding technology because is very much unrivaled in the
> > marketplace; its splendid performance shines everywhere, and all its
> > adopters are extraordinarily happy all the time.
>
> How factual is this statement? Which words can be deleted without loosing
> technical meaning? How many counter examples are needed to falsify it?

### Consequence

One ADR describes one significant decision for a specific project. It should be
something that has an effect on how the rest of the project will run.

This section describes the resulting context, after applying the decision. All
consequences should be listed here, not just the "positive" ones. A particular
decision may have positive, negative, and neutral consequences, but all of them
affect the team and project in the future.

> [!error] Anti pattern
> _Free Lunch Coupon_ (aka Candy Bar): No consequences are documented, or only
> consequences that seem to be harmless. The difficult ones are ignored
> accidentally or hidden deliberately, those that only materialize in the long
> run in particular.
>
> > [!example]
> > We decided for an event-driven architecture because it decouples the
> > components from each other.
>
> This might be true, at least for the time dimension of loose coupling. But
> what about the extra design, implementation, test effort? Doesn’t the event
> schema definition couple the receiver to the sender (in the format
> dimension)?

> [!error] Anti pattern
> _Tunnel Vision_: Only a local, isolated context is considered. Quite often,
> developmental qualities are covered, but the consequences for operations and
> maintenance are not taken into account sufficiently.

> [!success] Best practice
> Add criteria such as manageability and evolvability and comment how the
> chosen solution scores with respect to them.

### Alternatives options

During the discussion of the [architecture decision](/posts/architecture-decision),
alternatives should be evaluated and include relevant advantages and
disadvantages. These alternatives are described in terms that fit your needs
and objectives.

> [!error] Anti pattern
> _Dummy Alternative_: A solution is made up and presented as an option, but
> does not work at all in the given context. This move tries to make the
> preferred option shine and give the impression that multiple alternatives
> have been evaluated, which is not really the case.
>
> > [!example]
> > We decided to use PostgresSQL as our relational database. We could
> implement our own relational database management system, but this takes time
> and effort.
>
> Is this a new and valuable insight? Why are other existing relational
> database products and open source assets not mentioned like MariaDB?

> [!error] Anti pattern
> _Sprint_ (aka Rush): Only one option is considered. Only short-term effects
> are discussed, pertaining to the next two to three project iterations.

> [!success] Best practice
> Search for valid alternatives, for instance online or via your professional
> networks. Report on the search results, an ADR is an activity journal after
> all. Report mid and long-term consequences too.

## Example template of ADR

```markdown
# Short title of solved problem and solution


- Status: [proposed | rejected | accepted | deprecated | … | superseded by [ADR-XXXX]]
- Deciders: [list everyone involved in the decision]
- Date: [YYYY-MM-DD when the decision was last updated]
- Ticket: [Optional ticket/issue URL]

## Context and problem statement

[Describe the context and problem statement, e.g., in free form using two to
three sentences. You may want to articulate the problem in form of a question.]

## Key factors

- [driver 1, e.g., a force, facing concern, …]
- [driver 2, e.g., a force, facing concern, …]
- …

## Considered options

- [option 1]
- [option 2]
- [option 3]
- …

## Decision Outcome

Chosen option: "[option 1]", because [justification. e.g., only option, which
meets k.o. criterion decision driver | which resolves force force | … | comes
out best (see below)].

### Positive Consequences

- [e.g., improvement of quality attribute satisfaction, follow-up decisions
  required, …]
- …

### Negative Consequences

- [e.g., compromising quality attribute, follow-up decisions required, …]
- …

## Pros and Cons of the Options

### [option 1]

[example | description | pointer to more information | …]

- Good, because [argument a]
- Good, because [argument b]
- Bad, because [argument c]
- …

### [option 2]

[example | description | pointer to more information | …]

- Good, because [argument a]
- Good, because [argument b]
- Bad, because [argument c]
- …

### [option 3]

[example | description | pointer to more information | …]

- Good, because [argument a]
- Good, because [argument b]
- Bad, because [argument c]
- …

## Links

- [Link to reference used to help the decision]
- …
```

{{< article link="/posts/architecture-decision-log/" showSummary=true compactSummary=true >}}

> [!info] Some links for further reading
> - https://adr.github.io/adr-templates/
> - https://github.com/joelparkerhenderson/architecture-decision-record
> - https://www.ozimmer.ch/practices/2023/04/03/ADRCreation.html
> - https://cognitect.com/blog/2011/11/15/documenting-architecture-decisions
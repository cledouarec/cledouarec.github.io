---
title: "Centralizing your architecture decisions"
slug: "architecture-decision-log"
date: 2025-12-08
draft: false
description: "Learn how to organize and access architecture decisions effectively."
tags: ["Architecture"]
categories: ["tech"]
series: ["Architecture knowledge management"]
series_order: 5
---

Keeping track of architecture decisions is key to building maintainable
systems. An **architecture decision log (ADL)** helps you centralize decisions,
avoid repeated debates, and make the reasoning behind choices easily accessible
to everyone.

## What is an ADL ?

An ADL is the collection of all ADRs created and maintained for a particular
project (or organization).

There is no need to deploy complex tools such as databases. ADRs are most often
stored in text form in a wiki or with documentation in the code base.

## In practice

Accessing architecture decisions should be as simple and fast as possible to
ensure they are actually used. If the process for updating ADRs is too
cumbersome, teams are likely to avoid it, which often leads to the system being
abandoned.

In most organizations, two common approaches are used, each with its own
advantages and drawbacks. Regardless of the solution chosen, it’s important to
name pages or files consistently.

> [!tip]
> I recommend avoiding dates in the names and instead using a unique,
> incremented identifier. Follow your team’s standard naming convention, such
> as `CamelCase`, `snake_case`, or an equivalent format, to keep things clear
> and consistent.

### Wiki-based approach

The first option is to use an internal wiki (e.g., Atlassian Confluence or any
alternative). This approach is simple and quick to use, allows for templates or
more intelligent _blueprints_, and supports automatic distribution, which makes
it easier to keep the entire organization, including non-technical staff,
informed.

Its main drawbacks are the lack of synchronization with the codebase,
which can make it harder to link decisions to actual implementation, and the
temptation to edit existing ADRs rather than creating new ones. While page
editing can be restricted, this is often not enforced in practice.


### Git-based approach

The second option is to use Git with Markdown or ReStructuredText, depending on
your documentation system. Integrating ADRs into generated pages improves
accessibility. This approach has the advantage of being close to the source
code and providing full traceability through Git. A lightweight format like
Markdown keeps the focus on essentials and reduces the temptation to overload
ADRs with unnecessary diagrams. You can also enforce validation hooks to ensure
ADRs are properly filled out and that existing ADRs are not modified
incorrectly.

The main drawback is that sharing this information with the whole
organization can be harder, as non-technical staff may struggle to navigate a
Git repository if no front end is available.

> [!tip]
> While both approaches are viable, I personally lean towards using Git with
> Markdown.

This concludes this series of articles, which I hope have helped demystify ADRs
and encouraged you to use them in your organization.

> [!info] Some links for further reading
> - https://adr.github.io/adr-tooling/
> - https://github.com/joelparkerhenderson/architecture-decision-record
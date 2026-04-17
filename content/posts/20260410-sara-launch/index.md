---
title: "Introducing SARA: Requirements traceability for the modern age"
slug: "sara-launch"
date: 2026-04-10
description: >
    A Markdown-first approach to managing requirements and architecture as a
    connected knowledge graph"
tags: ["traceability", "requirements", "architecture"]
categories: ["tech"]
projects: ["sara"]
---

{{< lead >}}
Throughout my career in embedded systems, I've watched teams struggle with the
same problem over and over: requirements traceability.
{{< /lead >}}

You know the drill: ASPICE audits, CMMI assessments, ISO 26262 compliance, etc.
Everyone needs traceability, and the options are always the same: expensive
enterprise tools like DOORS that feel like they were designed in another era,
or JIRA-based workarounds that integrate poorly with actual code and slow
everything down.

I wanted something different. Something free, open-source, high-performance.
Something that fits how modern teams actually work. And crucially, something
AI-ready, because the way we write and consume specifications is about to
change dramatically.

So I built **SARA**.

{{< github repo="cledouarec/sara" showThumbnail=true >}}

## What is SARA?

SARA stands for _**S**olution **A**rchitecture **R**equirements for
**A**lignment_. It's a command-line tool that manages your solution,
architecture documents, and requirements as an interconnected knowledge graph,
providing a single source of truth for all teams, from marketing and business
to engineering.

But what makes SARA different isn't the features, it's the philosophy
behind it.

## Markdown-first: A radical choice

SARA uses plain Markdown files with YAML frontmatter. No proprietary formats.
No databases. No subscriptions.

This might seem like a limitation in some respects, but it's actually the most
powerful choice I could make:
- **No vendor lock-in.** Your requirements live in plain text files you own
  forever. If SARA disappears tomorrow, your data is still perfectly readable.
- **Git-native workflows.** Version control, branching, merging, code reviews.
  Your requirements follow the same lifecycle as your code. Draft in a branch,
  review in a pull request, release with a tag.
- **Universal readability.** Anyone can read and edit documents without special
  software. New team member? They already know how to use it.
- **AI-ready by design.** This is the part that excites me most. Plain text
  formats are ideal for AI agents and LLMs. Your requirements can be parsed,
  analyzed, and used as context for development. AI can help generate new
  requirements. AI can check consistency. The possibilities are just beginning
  to unfold.
- **DRY principle.** Your existing documentation like architecture diagrams,
  solution presentations, product pages, becomes part of your knowledge graph
  without duplication. Write once, trace everywhere.

## The traceability hierarchy

SARA recognizes ten document types forming a requirements hierarchy, from
high-level solutions down to detailed designs:

![Traceability model in SARA](sara_model.svg)

The first nine types form a vertical chain where each level refines the one
above. The tenth, the
[Architecture Decision Record (ADR)](/posts/architecture-decision-record), cuts
across the hierarchy: it captures significant design decisions, the reasoning
behind them, and links to the artifacts they justify.

Each item can trace its lineage back to business needs and forward to
implementation. This is the traceability auditors dream about, and it
emerges naturally from how you structure your documents.

## Why this matters now

We're at an inflection point in how software gets built. AI assistants are
becoming genuine collaborators, not just autocomplete on steroids. But they
need context to be useful.

When your requirements live in plain Markdown files with explicit traceability
links, an AI agent can understand the full picture. It can read your solution
vision, understand your constraints, trace down to see how things are
currently implemented, and make suggestions that actually fit your
architecture.

When your requirements live in DOORS or a JIRA mess, good luck getting that
context into an AI's understanding, or you are forced to use the AI assistant
and the model chosen by the vendor.

I built SARA with this future in mind. The Markdown-first approach isn't just
about avoiding vendor lock-in (though that matters). It's about building a
foundation that will grow more valuable as AI capabilities expand.

## What's next

SARA is young, but the foundation is solid. I'm using it on real projects,
and I'd love for you to try it too. Open issues, submit PRs, or just let me
know what you think.

If you want to see SARA in action, check out the
[getting started guide](/posts/sara-getting-started) where we build a complete
traceability chain for a Smart Home Control System, from solution vision down to
detailed designs, using the CLI.

The goal isn't to replace enterprise tools for everyone. Some organizations
genuinely need them. But for teams that want something lighter, faster, and
future-proof, SARA offers a different path.

Your requirements are too important to be trapped in a proprietary system.
Let's set them free.

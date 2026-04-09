---
title: "SARA"
description: "A CLI tool to unify scattered requirements and architecture documents into a traceable knowledge graph."
---

SARA (Solution Architecture Requirement for Alignment) addresses a common
challenge in complex organizations: requirements and architecture documents
scattered across teams, repositories, and formats — making traceability painful
and consistency almost impossible.

SARA aggregates documents from multiple Git repositories into a unified
knowledge graph, connecting business needs to implementation details through a
clear hierarchy: solutions, use cases, scenarios, system requirements,
architecture, and detailed designs.

Key capabilities:
- **Validation** — detect broken references, circular dependencies, orphans,
  and duplicates
- **Traceability** — query upstream toward business needs or downstream toward
  implementation
- **Reporting** — generate coverage reports and traceability matrices
- **Comparison** — diff knowledge graphs between commits or branches
- **AI agent workflow** — serve as a knowledge base for AI agents and leverage
  them to generate or refine requirements and documentation

The approach: plain markdown files with YAML metadata. No vendor lock-in, full
version control, code review friendly, and ready for AI integration.

{{< github repo="cledouarec/sara" showThumbnail=true >}}

This section gathers announcements, tutorials, and articles about SARA.

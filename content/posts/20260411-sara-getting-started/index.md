---
title: "Getting Started with SARA: Requirements as Code"
slug: "sara-getting-started"
date: 2026-04-11
description: >
    Learn how to manage architecture documents and requirements as an
    interconnected knowledge graph using SARA, a Markdown-first CLI tool.
tags: ["traceability", "requirements", "architecture"]
categories: ["tech"]
projects: ["sara"]
---

In complex organizations, requirements and architecture documents are often
scattered across teams, tools, and repositories. Keeping everything aligned is a
constant struggle. What if your requirements could live as plain Markdown files
in Git, versioned, reviewed, and interconnected like code?

That's exactly what **SARA** does.

**SARA** (**S**olution **A**rchitecture **R**equirement for **A**lignment) is a
command-line tool that manages architecture documents and requirements as an
interconnected knowledge graph. No databases, no servers, no subscriptions. Just
Markdown files with YAML frontmatter and a powerful CLI to validate, query, and
report on them.

In this article, we'll explore the hierarchy logic that connects all document
types, and walk through building a small requirements hierarchy for a **Smart
Home Control System** using the CLI tools, from a high-level solution down to
detailed designs.

## Installation

Install SARA from crates.io:

```bash
cargo install sara-cli
```

> [!note]
> SARA depends on `git2`, which requires system libraries like OpenSSL. If the
> build fails, check the
> [openssl crate documentation](https://docs.rs/openssl/latest/openssl/) for
> platform-specific installation instructions.

Verify the installation:

```bash
sara --version
```

## Setting Up Your Project

Create a project directory and initialize SARA's configuration:

```bash
mkdir smart-home && cd smart-home
mkdir docs
```

By default, SARA scans the root of the repository for Markdown documents. You
can customize this behavior by creating a `sara.toml` configuration file at the
root. This file holds all configuration options, but we will keep a very simple
example here:

```toml
[repositories]
paths = ["./docs"]

[output]
colors = true
emojis = true
```

The `paths` array tells SARA where to look for Markdown documents. You can list
multiple directories or even paths to other Git repositories to aggregate
documents from different sources.

## Creating Your First Documents

SARA recognizes 10 document types forming a traceability hierarchy, from
high-level Solutions down to detailed Hardware and Software designs. Each
document is a simple Markdown file with YAML frontmatter that SARA uses to build
the knowledge graph. The body of the file is free-form Markdown where you write
the actual content.

> [!tip]
> SARA ships with default templates for each document type, but you can override
> them with your own by placing custom templates in a directory and referencing
> it in `sara.toml`.

To create documents, SARA provides the `sara init` command. It generates the
YAML frontmatter for you, so you don't have to remember the exact field names
and structure. Each document type has its own subcommand with a short alias
(e.g., `sol` for Solution, `uc` for Use Case).

> [!tip]
> You can also run `sara init` without any arguments. SARA will launch an
> interactive mode that guides you step by step through type selection, ID
> generation, and relationship setup.

Let's build our Smart Home hierarchy from the top down.

### The Solution

Everything starts with a Solution. This is the highest-level item and represents
the product or system you are building. Create a Markdown file and initialize
it:

```bash
sara init sol docs/SOL-SMARTHOME.md \
  --id SOL-SMARTHOME \
  --name "Smart Home Control System" \
  -d "Integrated home automation and control system"
```

SARA inserts the following YAML frontmatter at the top of the file:

```markdown
---
id: "SOL-SMARTHOME"
type: solution
name: "Smart Home Control System"
description: "Integrated home automation and control system"
---
```

Below this block, you can write any Markdown content you want: a product
overview, diagrams, links to external resources. SARA only reads the frontmatter
for traceability purposes.

### Use Cases

Now that we have a Solution, we need to describe what users expect from it.
That's the role of Use Cases. Each Use Case is linked to the Solution it
refines, creating the first level of traceability:

```bash
sara init uc docs/UC-LIGHTS.md \
  --id UC-LIGHTS \
  --name "Lighting Control" \
  -d "Control and automate smart lighting throughout the home" \
  --refines SOL-SMARTHOME
```

The generated frontmatter now includes a `refines` field:

```markdown
---
id: "UC-LIGHTS"
type: use_case
name: "Lighting Control"
description: "Control and automate smart lighting throughout the home"
refines:
  - "SOL-SMARTHOME"
---
```

This `refines` relationship tells SARA that `UC-LIGHTS` is a child of
`SOL-SMARTHOME` in the traceability graph. You only need to define the link in
one direction. SARA automatically infers the reverse, so the Solution will know
about this Use Case without you editing `SOL-SMARTHOME.md`.

> [!tip]
> SARA supports both upstream links (`refines`, `derives_from`, `satisfies`) and
> their downstream counterparts (`is_refined_by`, `derives`, `is_satisfied_by`).
> However, the recommended practice is to always use upstream links. Lower-level
> items should point to the higher-level items they come from. This reflects
> natural knowledge flow: a Use Case knows which Solution it belongs to, but a
> Solution should not need to list every Use Case manually.

### Scenarios

Scenarios break Use Cases into concrete behaviors. They describe specific
interactions or flows. Let's create one for adjusting light brightness:

```bash
sara init scen docs/SCEN-DIMMER.md \
  --id SCEN-DIMMER \
  --name "Adjust Light Brightness" \
  --refines UC-LIGHTS
```

The same `refines` relationship links this Scenario to its parent Use Case.

### System Requirements

From Scenarios, we derive quantifiable requirements. These are the "SHALL"
statements that specify what the system must do. The relationship changes from
`refines` to `derives_from`, reflecting that requirements are derived from
scenarios rather than refining them:

```bash
sara init sysreq docs/SYSREQ-LATENCY.md \
  --id SYSREQ-LATENCY \
  --name "Device Command Latency" \
  -d "Maximum allowed latency for device control commands" \
  --specification "The system SHALL deliver device commands within 500ms of user action" \
  --derives-from SCEN-DIMMER
```

Notice the new `--specification` flag. Requirements have this extra field to
hold the formal SHALL statement, keeping it separate from the description.

> [!note]
> Requirements also support a `depends_on` field to express dependencies between
> requirements of the same type (e.g., `SYSREQ-AUTH` depends on
> `SYSREQ-SESSION`). This is purely informative and helps document prerequisite
> relationships, but SARA does not enforce or validate these dependencies.

### System Architecture

The System Architecture describes how the system is structured to satisfy
requirements. Here, the relationship is `satisfies`, because the architecture is
the answer to what the requirements ask for.

> [!note]
> In practice, a single System Architecture document often satisfies multiple
> System Requirements. You will typically have far fewer architecture documents
> than requirements, each one covering a broad area of the system.

```bash
sara init sysarch docs/SYSARCH-COMM.md \
  --id SYSARCH-COMM \
  --name "Communication Architecture" \
  -d "System architecture for device communication" \
  --satisfies SYSREQ-LATENCY
```

### Software Requirements and Detailed Designs

From the architecture, we continue down into platform-specific requirements and
their implementation details. Software Requirements derive from the System
Architecture, and Software Detailed Designs satisfy those requirements:

```bash
sara init swreq docs/SWREQ-MQTT.md \
  --id SWREQ-MQTT \
  --name "MQTT Client Library" \
  --specification "The software SHALL implement MQTT 5.0 protocol" \
  --derives-from SYSARCH-COMM
```

```bash
sara init swdd docs/SWDD-MQTT.md \
  --id SWDD-MQTT \
  --name "MQTT Client Implementation" \
  --satisfies SWREQ-MQTT
```

The same pattern applies to hardware with `hwreq` and `hwdd` subcommands.

At this point, we have built a complete traceability chain from the
business-level Solution all the way down to a Software Detailed Design. Every
item knows where it comes from and SARA can traverse the entire graph in both
directions.

## Validating Your Graph

Now that we have several interconnected documents, we want to make sure
everything is consistent. The `sara check` command parses all documents, builds
the knowledge graph, and runs a series of validation rules against it:

```bash
sara check
```

If something is wrong, SARA will tell you exactly what and where. The checks
include:
- **Broken references**: a document links to an ID that does not exist in any
  file
- **Circular dependencies**: A -> B -> C -> A, which usually indicates a
  modeling error
- **Orphan items**: items with no upstream parent, meaning they are disconnected
  from the hierarchy
- **Duplicate identifiers**: the same ID appears in multiple files
- **Invalid relationships**: a relationship type that does not make sense for a
  given item type

By default, some issues like orphan items are reported as warnings. If you want
a stricter validation where everything must be clean, use the `--strict` flag:

```bash
sara check --strict
```

This is particularly useful in a CI pipeline where you want the build to fail if
the knowledge graph has any inconsistency. You can also enable strict mode
permanently in your `sara.toml` so you don't have to pass the flag every time:

```toml
[validation]
strict_mode = true
```

The output can also be exported as JSON for integration with other tools:

```bash
sara check --format json -o results.json
```

## Querying Traceability

With a validated graph in place, we can now explore it. The `sara query` command
lets you pick any item and traverse the graph upward or downward.

For example, imagine a developer working on the MQTT client implementation wants
to understand why this component exists. They can trace it all the way back to
the business need:

```bash
sara query SWDD-MQTT --upstream
```

Output:

```
📋 SWDD-MQTT: MQTT Client Implementation
   Type: Software Detailed Design
   File: SWDD-MQTT.md

Upstream Traceability for SWDD-MQTT
SWDD-MQTT: MQTT Client Implementation (Software Detailed Design)
└── SWREQ-MQTT: MQTT Client Library (Software Requirement)
    └── SYSARCH-COMM: Communication Architecture (System Architecture)
        └── SYSREQ-LATENCY: Device Command Latency (System Requirement)
            └── SCEN-DIMMER: Adjust Light Brightness (Scenario)
                └── UC-LIGHTS: Lighting Control (Use Case)
                    └── SOL-SMARTHOME: Smart Home Control System (Solution)
```

In one command, the full chain is visible: this implementation exists because
there is a latency requirement, which comes from a dimmer scenario, which
belongs to the lighting use case of the Smart Home solution.

You can also go the other direction. A product owner might want to see
everything that implements a solution:

```bash
sara query SOL-SMARTHOME --downstream
```

For large graphs, you can limit how deep the traversal goes:

```bash
sara query SYSREQ-LATENCY --downstream --depth 2
```

Or focus on a specific document type to answer questions like "which software
requirements are derived from this solution?":

```bash
sara query SOL-SMARTHOME --downstream --type software_requirement
```

## Generating Reports

Querying individual items is useful for day-to-day work, but sometimes you need
a broader view. SARA provides two types of reports for this.

### Coverage Report

The coverage report answers the question: "are all my requirements covered by
downstream items?" For instance, if a System Requirement has no System
Architecture satisfying it, it will show up as uncovered:

```bash
sara report coverage
```

This is a great way to identify gaps in your hierarchy early on, before they
become blind spots.

### Traceability Matrix

The traceability matrix gives you a complete cross-reference table showing which
items are connected to which. This is often required for audits, reviews, or
compliance:

```bash
sara report matrix --format csv -o matrix.csv
```

Both reports support multiple output formats: `text`, `json`, `csv`, and `html`.
The HTML format is convenient for sharing with stakeholders who don't use the
CLI.

## Comparing Versions

As your project evolves, you will add, remove, and modify requirements.
Reviewing these changes in a pull request can be difficult when you only see raw
YAML diffs. The `sara diff` command solves this by comparing the knowledge graph
between two Git references and showing you what changed at the semantic level:

```bash
sara diff main feature/new-requirements
```

This tells you which items were added, removed, or modified between the two
branches. If you just want a quick summary of how many items changed, add
`--stat`:

```bash
sara diff main feature/new-requirements --stat
```

## Architecture Decision Records

So far, all our documents follow the vertical hierarchy: Solution, Use Case,
Scenario, Requirement, Architecture, Design. But there is one document type that
cuts across the hierarchy: the [Architecture Decision Record (ADR)](/posts/architecture-decision-record).

ADRs capture significant design decisions, the reasoning behind them, and who
made them. They have a lifecycle status (`proposed`, `accepted`, `deprecated`,
`superseded`) and are linked to the artifacts they justify. Going back to our
Smart Home example, we can record why we chose MQTT for device communication:

```bash
sara init adr docs/ADR-001.md \
  --id ADR-001 \
  --name "Use MQTT for Device Communication" \
  --status accepted \
  --deciders "Architecture Team" \
  --justifies SYSARCH-COMM
```

The `justifies` relationship connects the decision to the architecture it
supports. This way, when someone looks at `SYSARCH-COMM`, they can see not only
what the architecture is, but also why it was designed that way.

Decisions evolve over time. When a new decision replaces an older one, the
`supersedes` relationship maintains the history:

```bash
sara init adr docs/ADR-002.md \
  --id ADR-002 \
  --name "Switch to Matter Protocol" \
  --status accepted \
  --deciders "Architecture Team" \
  --justifies SYSARCH-COMM \
  --supersedes ADR-001
```

SARA tracks the full decision chain in the graph, so you can always understand
how and why the architecture evolved.

## Multi-Repository Support

In our tutorial, all documents live in a single `docs/` folder. In practice,
larger organizations often split their work across multiple repositories: one
for hardware specs, another for software architecture, a third for product
requirements, etc. SARA handles this natively. You just list all the paths in
your configuration:

```toml
# sara.toml
[repositories]
paths = [
    "./docs",
    "../hardware-team/specs",
    "../platform-team/architecture"
]
```

SARA aggregates all documents into a single unified graph. Cross-repository
traceability works the same way: a Software Requirement in one repository can
reference a System Architecture in another, and SARA will resolve the link.

## Editing Existing Documents

Requirements change. Names get refined, relationships are added, specifications
are updated. You could edit the YAML frontmatter by hand, but SARA provides the
`sara edit` command to do it safely. You reference the item by its ID, and SARA
finds the file, updates the frontmatter, and leaves the Markdown body untouched:

```bash
sara edit SYSREQ-LATENCY --name "Device Command Response Time"
```

This is especially convenient when you need to update relationships, since SARA
handles the YAML list formatting for you.

## Tips for Success

- **Bottom-up linking**: Prefer upstream links (`refines`, `derives_from`,
  `satisfies`). Lower-level items should reference the higher-level items they
  come from. This reflects natural knowledge flow: implementations know their
  purpose, but high-level solutions shouldn't need to list every detail.

- **Use `sara check` in CI**: Add validation to your CI pipeline to catch broken
  references and orphan items early.

- **Start small**: You will eventually need all 10 document types, but you don't
  have to write detailed content from day one. Start with the bare minimum: a
  name, a short description, and the right relationships. The important thing is
  to get the traceability structure in place early. Detailed specifications,
  market analysis, and design rationale can be added progressively as the
  project matures.

- **Let Markdown shine**: Since the body of each document is regular Markdown,
  you have full freedom on the format. Use diagrams, tables, embedded images,
  links to external resources, or any structure that makes the document clear
  and useful for its audience. SARA only reads the YAML frontmatter, so the rest
  is yours.

## Wrapping Up

In this article, we went from an empty directory to a fully connected
requirements hierarchy: a Solution, a Use Case, a Scenario, a System
Requirement, an Architecture, a Software Requirement, and a Detailed Design, all
linked together and validated by SARA.

We also explored how to query traceability in both directions, generate coverage
reports and traceability matrices, compare versions across Git branches, and
record architecture decisions with full history.

All of this lives in plain Markdown files, versioned in Git, reviewed in pull
requests, and validated in CI. No proprietary tools, no vendor lock-in.

The complete Smart Home example used in this article is available in the
[SARA repository](https://github.com/cledouarec/sara/tree/main/examples/smart-home).

> [!info] To learn more, check out:
> - [SARA on GitHub](https://github.com/cledouarec/sara)
> - [SARA on crates.io](https://crates.io/crates/sara-cli)

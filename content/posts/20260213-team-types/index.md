---
title: "Team types: Choosing the right structure for your organization"
slug: "team-types"
date: 2026-02-13
draft: false
description: "A comprehensive guide to different team types: horizontal, vertical, feature, impact, and more. Learn which structure fits your organization's needs."
tags: []
categories: ["organization"]
series: ["Team structure"]
series_order: 3
---

After understanding how communication flows within organizations, the next step
is to examine how teams themselves are structured. Before zooming out to see how
multiple teams interact, a topic covered in the next article, it is worth taking
a closer look at the **team as a unit**: what makes it successful, how should
responsibilities be distributed within it, and what trade-offs come with each
choice.

{{< lead >}}
There is no universal "best" way to structure a team.
{{< /lead >}}

Each model carries trade-offs, and the right choice depends on the team's
mission, the product's complexity, the skills available, and the level of
autonomy desired. Let's explore the most common team types, their
characteristics, benefits, and limitations.

## The fundamental question: How do we split work?

At the core of team design lies a simple question: **how do we divide work among
people?** The answer shapes everything else: reporting lines, communication
patterns, skill distribution, and cultural norms.

Historically, organizations have approached this question from two primary
perspectives:
- **By function or skill** (horizontal teams)
- **By product or outcome** (vertical teams)

Understanding these foundational models is essential before exploring more
specialized team types.

## Horizontal teams: Organizing by function

Horizontal teams group people by their function, skill, or discipline. In a
technology company that develops embedded products, this typically means
separate teams for firmware development, hardware design, software, validation,
systems engineering, and product management.

Each team focuses on its domain of expertise. Work flows horizontally across
teams as different functions contribute their specialized knowledge to a shared
initiative.

### Characteristics

- Teams are organized around **technical disciplines** or **functional areas**
- Team members share similar skills and expertise
- Work typically crosses multiple teams to deliver end-to-end features
- Coordination happens through shared roadmaps, or project management
- Deep specialization within each function

> [!example] Typical horizontal teams in an embedded systems organization
> - **Firmware Team**: Develops low-level software across all product lines
> - **Hardware Design Team**: Designs PCBs, schematics, and electrical systems
> - **Software Team**: Builds applications, cloud services, and companion apps
> - **Validation Team**: Handles testing, certification, and quality assurance
> - **Systems Engineering Team**: Defines requirements, interfaces, and
>   integration across subsystems
> - **Manufacturing Engineering Team**: Owns production processes, tooling, and
>   yield optimization

### Communication patterns

Horizontal teams rely heavily on **cross-functional coordination**. A single
feature often requires collaboration between hardware, firmware, software, and
validation teams. Communication flows include:
- **Horizontal communication** between peer teams
- **Downward communication** from leadership to arbitrate priorities, since
  horizontal teams serve multiple initiatives and cannot decide allocation on
  their own
- **Hub communication** through project managers or tech leads who coordinate
  across functions

### Strengths and limitations

> [!success] Benefits
> - **Deep expertise**: Team members develop specialized skills within their
>   domain
> - **Efficient resource allocation**: Specialists can be shared across multiple
>   initiatives
> - **Standards and consistency**: Centralized teams enforce consistent
>   practices (coding standards, design rules, test procedures)
> - **Career development**: Clear growth paths within a technical discipline
> - **Knowledge sharing**: Concentrated expertise makes it easier to mentor and
>   transfer knowledge

> [!error] Drawbacks
> - **Slow delivery**: Features requiring multiple teams face coordination
>   overhead and handoff delays
> - **Diluted ownership**: No single team owns the end-to-end customer
>   experience
> - **Misaligned priorities**: Teams may optimize for their function rather than
>   business outcomes
> - **Communication overhead**: Coordinating across teams requires significant
>   management effort
> - **Risk of silos**: Teams develop local optimizations that may conflict with
>   organizational goals
> - **Reduced agility**: Responding to changing priorities requires realigning
>   multiple teams

### When to use this model

Horizontal teams work well in organizations where:
- **Specialization is critical**: The technical complexity demands deep
  expertise (e.g., machine learning, security, compliance)
- **Economies of scale matter**: Shared infrastructure or platforms benefit from
  centralization
- **Work is predictable**: Initiatives can be planned and sequenced across teams
- **The organization is small**: Coordination overhead remains manageable
- **Platforms or shared services**: Infrastructure teams supporting multiple
  products

## Vertical teams: Organizing by product or value stream

Vertical teams, also called **product teams** or **cross-functional teams**,
organize around a product, feature area, or customer segment. Each team contains
all the skills needed to deliver value independently: hardware engineers,
firmware developers, software engineers, testers, and sometimes product
managers.

The team owns a specific slice of the product or customer journey from end to
end. Instead of passing work horizontally across functions, the team moves work
vertically through its own delivery pipeline.

### Characteristics

- Teams are organized around **products**, **features**, or **customer
  outcomes**
- Each team is **cross-functional**, containing diverse skills (hardware,
  firmware, software, test, etc.)
- Teams have **end-to-end ownership** of their domain
- Minimal dependencies on other teams for delivery
- Autonomy to make decisions within their scope

> [!example] Typical vertical teams in an IoT product organization
> - **Connectivity Team**: Owns the entire BLE and Wi-Fi stack, from firmware
>   drivers to cloud pairing services
> - **Sensor Module Team**: Builds and maintains all sensor acquisition,
>   calibration, and processing
> - **Power Management Team**: Responsible for battery life, charging circuits,
>   and energy-saving firmware
> - **Companion App Team**: Develops the mobile application and its integration
>   with the device
> - **OTA Update Team**: Owns the full over-the-air update pipeline from build
>   to deployment

### Communication patterns

Vertical teams minimize cross-team dependencies, reducing the need for constant
coordination. Communication flows include:
- **Strong horizontal communication** within the team
- **Upward communication** to align on strategy and priorities, since the team
  owns its roadmap and proposes what to build rather than receiving assignments
- **Hub communication** through product managers or architects for rare
  cross-team coordination

### Strengths and limitations

> [!success] Benefits
> - **Fast delivery**: Teams move quickly without waiting for other teams
> - **Clear ownership**: One team is accountable for the entire customer
>   experience in their area
> - **Aligned incentives**: Teams optimize for business outcomes, not functional
>   metrics
> - **High autonomy**: Teams make decisions independently, fostering ownership
>   and motivation
> - **Reduced coordination overhead**: Fewer dependencies
> - **Customer focus**: Teams stay close to user needs and can iterate rapidly

> [!error] Drawbacks
> - **Duplicated effort**: Teams may rebuild similar solutions independently
> - **Inconsistent standards**: Without centralized functions, design,
>   architecture, or processes may diverge
> - **Skill gaps**: Smaller teams may lack deep expertise in specific areas
> - **Inefficient resource use**: Specialists may be underutilized if not fully
>   needed within a single team
> - **Difficult career paths**: Engineers may struggle to grow in a specific
>   discipline without a community of practice
> - **Integration challenges**: Ensuring different teams' outputs work together
>   seamlessly requires deliberate effort

### When to use this model

Vertical teams work well in organizations where:
- **Speed and autonomy matter**: The market demands rapid iteration and
  experimentation
- **Clear product boundaries exist**: Different areas of the product can be
  separated with minimal overlap
- **The organization is large enough**: You have sufficient people to form
  multiple cross-functional teams
- **Customer outcomes drive success**: Business metrics matter more than
  technical metrics
- **Innovation is prioritized**: Teams need freedom to experiment and adapt

## Feature teams: Delivering end-to-end functionality

Feature teams are a specific type of vertical team focused on delivering
complete, customer-facing features. The concept gained prominence through the
Scrum framework and emphasizes that teams should deliver **working software**
that provides tangible value, not just components.

### Characteristics

- Teams work on **complete features** that span the full technology stack
- Cross-functional composition (hardware, firmware, software, test, etc.)
- Features are defined from the **user's perspective**, not technical
  architecture
- Teams own features from conception through deployment and maintenance
- Emphasis on delivering **potentially shippable increments**

> [!important] Difference from general vertical teams
> While all feature teams are vertical teams, not all vertical teams are feature
> teams. Feature teams specifically emphasize:
> - **User-centric delivery**: Features must deliver visible customer value
> - **Full-stack responsibility**: Teams cannot deliver just firmware or just a
>   PCB. They deliver the complete feature across all layers
> - **Iterative development**: Features are broken into incremental releases

> [!example] Feature team in a connected device company
> The **NFC Authentication Feature Team** owns everything related to contactless
> authentication:
> - Hardware interface for the NFC antenna and secure element
> - Firmware for NFC protocol handling and key exchange
> - Mobile app integration for pairing and provisioning
> - Cloud service for certificate management
> - Maintenance and bug fixes across all layers
>
> The team includes a product manager, hardware engineer, firmware developer,
> software engineer, and test engineer. They deliver the feature end-to-end
> without dependencies on other teams.

### Strengths and limitations

> [!success] Benefits
> - **Faster time to market**: Complete features ship without waiting for other
>   teams
> - **Clear value delivery**: Teams focus on what matters to users, not internal
>   architecture
> - **Reduced handoffs**: One team handles all aspects of a feature
> - **Better quality**: Teams own their features long-term, incentivizing
>   maintainability
> - **Increased motivation**: Seeing complete features ship boosts team morale

> [!error] Drawbacks
> - **Architectural debt**: Teams may take shortcuts to deliver features
>   quickly, creating technical debt
> - **Knowledge silos**: Expertise becomes concentrated within feature areas
>   rather than shared
> - **Inconsistent UX**: Without coordination, features may feel disjointed
> - **Platform neglect**: Core infrastructure may suffer if all teams focus on
>   features

### When to use this model

Feature teams work well when:
- **Product delivery speed is critical**
- **Features are relatively independent**
- **You have a mature platform** that feature teams can build upon
- **Customer feedback loops are tight**

## Platform teams: Managing shared services and internal products

Platform teams focus on building and maintaining **shared platforms, libraries,
or services** that other teams depend on. Unlike vertical teams, platform teams
do not deliver customer-facing features directly. Instead, they provide
capabilities that enable other teams to deliver value faster.

### Characteristics

- Teams own **technical components** or **platforms** (e.g., BSP, RTOS
  abstractions, CI/CD pipelines, test infrastructure)
- Their customers are **other engineering teams**, not end users
- Focus on **reusability, stability, and performance**
- Often horizontal in nature but with a product mindset

> [!important] Difference from general horizontal teams
> While platform teams share the functional grouping of horizontal teams, they
> differ in a key way: a platform team **owns a product**, its product just
> happens to be internal. It maintains a backlog, prioritizes requests from
> consuming teams, defines its own roadmap, and manages versioning and
> contracts. A traditional horizontal team executes work assigned by others; a
> platform team decides **what** to build and **when**, treating other
> engineering teams as its customers.

> [!example] Platform teams in an embedded systems organization
> - **BSP Team**: Maintains the board support package and hardware abstraction
>   layers used by all product teams
> - **Security Team**: Builds and operates the cryptographic libraries, secure
>   boot, and key management infrastructure
> - **Test Infrastructure Team**: Provides hardware-in-the-loop benches,
>   automated test frameworks, and fleet management tools
> - **DevOps Team**: Owns CI/CD pipelines and firmware release processes

### Strengths and limitations

> [!success] Benefits
> - **Leverage and reuse**: One team's work benefits many others
> - **Consistency**: Centralized components ensure uniform experiences
> - **Efficiency**: Teams avoid duplicating foundational work
> - **Deep expertise**: Platform teams develop specialized knowledge

> [!error] Drawbacks
> - **Disconnection from end users**: Teams may lose sight of customer needs
> - **Bottlenecks**: If platform teams cannot keep up with demand, they slow
>   everyone down
> - **Competing priorities**: Balancing requests from multiple product teams is
>   challenging
> - **Reduced feature team autonomy**: Dependencies on platform teams limit
>   speed

### When to use this model

Platform teams work well when:
- **Shared infrastructure provides significant value**
- **Duplication would be costly or risky** (e.g., security, compliance,
  infrastructure)
- **The organization is large enough** to justify dedicated platform teams
- **Clear interfaces and contracts** exist between platform teams and their
  consumers

## Impact teams: Optimizing for business outcomes

Impact teams represent an evolution of feature teams, explicitly organized
around **measurable business outcomes** rather than features or products. These
teams are given a metric to move (revenue, retention, engagement, conversion)
and full autonomy to determine how to achieve it.

### Characteristics

- Teams are organized around **metrics and business objectives**, not features
- **Outcome-focused**: Success is measured by impact, not output (features
  shipped)
- **High autonomy**: Teams decide what to build based on what will move their
  metric
- **Experimentation-driven**: Heavy emphasis on A/B testing, data analysis, and
  iteration
- Cross-functional, including data analysts or data scientists

> [!important] Difference from feature teams
> Feature teams focus on **what** to build (features). Impact teams focus on
> **why** to build (outcomes). Impact teams have even more strategic autonomy,
> they can choose to build features, run experiments, remove features, or change
> existing behavior based on data.

> [!example] Impact team in a connected device company
> The **First-Time Setup Success Impact Team** is responsible for improving the
> percentage of users who complete device pairing on their first attempt.
>
> **Their metric**: first-attempt setup success rate
>
> The team includes a product manager, hardware engineer, firmware developer,
> software engineer, and a data analyst. They are empowered to:
> - Simplify the BLE pairing flow in firmware
> - Improve antenna placement or shielding to reduce interference
> - Redesign the onboarding UX in the companion app
> - Add visual or haptic feedback on the device during pairing
> - Pre-provision credentials at the factory to skip manual steps
>
> They run continuous experiments, measure drop-off points in the setup funnel,
> and iterate based on what drives first-attempt success.

### Communication patterns

Impact teams require strong data infrastructure and alignment on metrics.
Communication flows include:
- **Upward communication** to align on strategic metrics and OKRs
- **Horizontal communication** with other impact teams to avoid conflicts or
  leverage synergies
- **Hub communication** through data teams or analytics platforms
- **Frequent reporting** on metric movement and experiment results

### Strengths and limitations

> [!success] Benefits
> - **Laser-focused on business value**: Every decision is tied to measurable
>   outcomes
> - **Accountability**: Teams own clear, measurable goals
> - **Strategic autonomy**: Teams determine the best approach to achieve impact
> - **Data-driven culture**: Decisions are based on evidence, not opinions
> - **Rapid learning**: Continuous experimentation accelerates improvement

> [!error] Drawbacks
> - **Short-term optimization**: Teams may prioritize quick wins over long-term
>   sustainability
> - **Metric gaming**: Teams might optimize their metric at the expense of
>   broader goals
> - **Requires strong data infrastructure**: Without reliable data, impact teams
>   cannot function
> - **Difficult to define metrics**: Not all valuable work maps to a single,
>   measurable outcome
> - **Potential for conflict**: Different teams' metrics may compete (e.g.,
>   growth vs. quality)
> - **Requires mature organization**: Teams need the skills and discipline to
>   interpret data correctly

### When to use this model

Impact teams work well when:
- **Business metrics are well-defined and measurable**
- **Data infrastructure is mature**: Reliable tracking, experimentation
  platforms, and analytics
- **The organization values outcomes over outputs**
- **Teams have strong analytical skills**
- **Leadership trusts teams to make strategic decisions**

## Choosing the right team structure

There is no one-size-fits-all answer. The right structure depends on multiple
factors:

### Considerations

| **Factor** | **Horizontal** | **Vertical / Feature / Impact** | **Platform** |
|---|---|---|---|
| **Organization size** | Small to medium | Medium to large | Medium to large |
| **Product complexity** | Simple or modular | Complex, integrated | Complex |
| **Speed requirements** | Moderate | High | Moderate |
| **Specialization needs** | High | Moderate | High |
| **Coordination overhead** | High | Low | Moderate |
| **Customer focus** | Indirect | Direct | Indirect |
| **Innovation priority** | Moderate | High | Moderate |

### Guiding questions

Before choosing a team structure, ask:

1. **What is our primary goal?** Speed? Quality? Innovation? Consistency?
2. **How autonomous can teams realistically be?** Do we have shared
   infrastructure, or must teams coordinate constantly?
3. **What is our product architecture?** Monolithic systems may force more
   coordination; microservices enable more autonomy.
4. **How mature is our organization?** Vertical teams require discipline, data
   infrastructure, and trust.
5. **What are our bottlenecks today?** Identify whether coordination,
   specialization, or execution speed is the limiting factor.

## Evolving team structures over time

Team structures are not static. As organizations grow, products mature, and
markets shift, the optimal structure changes. Many successful companies evolve
through predictable stages:

### Stage 1: Small startup (horizontal by default)

Everyone does a bit of everything. There are no formal teams, just people
working together.

### Stage 2: Growing startup (emerging vertical teams)

As the team grows, you form your first cross-functional product teams to move
faster and reduce dependencies.

### Stage 3: Scaling organization (vertical + platform)

You establish dedicated platform teams to avoid duplication and maintain
consistency while product teams remain autonomous.

### Stage 4: Mature organization (guilds and CoEs)

You introduce communities of practice, architectural governance, and more
sophisticated coordination mechanisms to balance speed and consistency at scale.

> [!tip] Key takeaway
> Team structure should evolve with your organization. Regularly reassess
> whether your current structure still serves your goals, or whether it has
> become a constraint.

## Teams in the age of AI assistants

The rise of AI coding assistants and generative AI is beginning to reshape how
teams operate. While the fundamental team types described above remain relevant,
AI introduces new dynamics worth considering.

### Amplified individual capacity

AI assistants allow a single engineer to cover more ground: writing boilerplate,
generating tests, exploring unfamiliar codebases, or drafting documentation.
This shifts the bottleneck from raw output to judgment, review, and
decision-making. Teams that were sized around production throughput may find
that fewer people can deliver the same scope, raising questions about optimal
team size.

### Blurred skill boundaries

When an AI assistant can help a firmware engineer write a cloud integration or
assist a hardware designer in scripting a test automation pipeline, the
traditional skill boundaries that define horizontal teams become less rigid.
This does not eliminate the need for deep expertise, but it lowers the barrier
for cross-functional contribution within vertical and feature teams.

### Increased need for review and alignment

Higher individual output means more code, more artifacts, and more decisions
flowing through the team. Without deliberate coordination, AI-assisted teams
risk producing faster but diverging more. Review processes, architectural
guidelines, and shared standards become even more important to maintain
coherence.

### Impact on team types

- **Horizontal teams** may see reduced coordination overhead as AI tools help
  bridge knowledge gaps between functions
- **Vertical and feature teams** benefit most directly, as AI amplifies each
  member's ability to contribute across the stack
- **Platform teams** face growing demand, since AI-assisted product teams move
  faster and consume shared services more aggressively
- **Impact teams** gain new experimentation capabilities through AI-driven
  analysis, prototyping, and rapid iteration

> [!tip] Key consideration
> AI does not change **why** teams exist. Teams still exist to own decisions,
> maintain accountability, and deliver outcomes. What changes is the **capacity
> envelope** of each team member and the speed at which misalignment can
> compound. Organizations adopting AI tools should revisit team boundaries,
> review practices, and coordination mechanisms accordingly.

## Conclusion

There is no universally "best" team structure. Horizontal teams offer
specialization and consistency but struggle with speed and autonomy. Vertical,
feature, and impact teams deliver faster and focus on outcomes but risk
duplication and inconsistency. Platform teams provide leverage but can become
bottlenecks.

The right team structure is the one that aligns with your organization's size,
goals, product architecture, and cultural values. Rather than copying what works
elsewhere, observe your bottlenecks, experiment deliberately, and evolve your
structure as your organization grows.

In the next article, we will explore **team topologies**: how multiple teams
interact, coordinate, and evolve together to form a coherent organizational
system.

> [!info] Some links for further reading
> - [Feature Teams vs Component Teams](https://less.works/less/structure/feature-teams)
> - [From Feature teams to Impact teams : a new era for Malt Product Team in 2021](https://blog.malt.engineering/from-features-teams-to-impact-teams-a-new-era-for-malt-product-team-in-2021-d7d394e8c434)

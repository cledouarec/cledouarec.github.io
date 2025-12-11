---
title: "Arrêtez de critiquer l’architecture: comprenez les décisions qui l’ont façonnée"
slug: "architecture-knowledge-management"
date: 2025-12-04
draft: false
description: "Découvrez comment documenter efficacement les décisions d’architecture et conserver les raisons qui les ont motivées."
tags: ["Architecture"]
categories: ["tech"]
series: ["Architecture knowledge management"]
series_order: 1
---

Vous avez sans doute déjà entendu quelqu’un râler à propos d’une décision
d’architecture:

> [!quote] Pourquoi avons-nous fait ce choix ? Il n’a aucun sens !

Pourtant, au moment où cette décision a été prise, elle était parfaitement
justifiée, que ce soit en raison d’un délai de mise sur le marché très court,
de contraintes de compatibilité ou d’autres éléments contextuels.

Dans cette série d'articles, nous allons explorer plusieurs concepts essentiels pour
structurer et gérer la connaissance architecturale. L’objectif est simple:
capturer, partager et tracer les décisions d’architecture afin que chacun
puisse comprendre non seulement ce qui a été décidé, mais aussi pourquoi cela
avait du sens à ce moment-là.

## Qu’est-ce que l’Architecture Knowledge Management ?

L’Architecture Knowledge Management (AKM) est conçu pour **stocker**,
**organiser** et **diffuser la connaissance architecturale** au sein d’une
organisation.

![diagramme représentant le flux d’une décision d'architecture](architecture_knowledge_management.svg)

En termes simples, l’objectif principal est de documenter une [décision d'architecture (AD)](/fr/posts/architecture-decision)
sur la base d’une [exigence ayant un impact architectural (ASR)](/fr/posts/architecturally-significant-requirement)
dans une [fiche de décision architecturale (ADR)](/fr/posts/architecture-decision-record).
Toutes les ADRs sont ensuite regroupées dans un [journal des décisions architecturales (ADL)](/fr/posts/architecture-decision-log).

L’élément central est donc la création d’une ADR, car c’est elle qui nous
permettra de comprendre ultérieurement les choix effectués.
Dans le prochain article, nous présenterons le concept d’ASR, qui n’est pas
aussi trivial qu’il n'y paraît.

{{< article link="/fr/posts/architecturally-significant-requirement/" showSummary=true compactSummary=true >}}

> [!info] Quelques liens pour aller plus loin
> - https://adr.github.io
> - https://github.com/joelparkerhenderson/architecture-decision-record
> - https://martinfowler.com/articles/scaling-architecture-conversationally.html
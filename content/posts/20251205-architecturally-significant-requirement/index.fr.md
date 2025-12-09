---
title: "ASR : Le véritable moteur derrière chaque décision d’architecture"
slug: "architecturally-significant-requirement"
date: 2025-12-05
draft: false
description: "Un guide pratique pour comprendre et prioriser les exigences significatives pour l’architecture."
tags: ["Architecture"]
categories: ["tech"]
series: ["Architecture knowledge management"]
series_order: 2
---

Toutes les exigences ne façonnent pas la manière dont un système est construit,
mais certaines laissent une empreinte durable sur l’architecture. Ce sont
celles qui comptent vraiment, ce que les architectes appellent les **exigence**
**significative pour l’architecture (ASR - architecturally significant**
**requirement)**.

Les repérer tôt est essentiel, car elles influencent des décisions critiques,
impactent la performance, et peuvent parfois faire ou défaire un projet. Dans
cet article, nous expliquerons ce que sont les ASR, pourquoi elles méritent une
attention particulière, et comment les prioriser de manière objective pour
guider votre architecture dans la bonne direction.

## Qu’est-ce qu’une ASR ?

Une ASR est une exigence qui a un impact mesurable sur l’architecture d’un
système logiciel.

Identifier ces besoins est essentiel pour prendre une décision éclairée. Chaque
fois qu’une [décision d’architecture (AD)](/fr/posts/architecture-decision) est
prise, une [fiche de décision d’architecture (ADR)](/fr/posts/architecture-decision-record)
sera produite.

## Pourquoi identifier les ASR les plus importantes ?

> [!warning] Une ASR peut avoir une valeur différente selon le moment.

Par exemple, une exigence liée à l’usage mémoire ne devient critique qu’à
l’approche de la limite, c’est pourquoi une priorisation doit être définie.

Les critères permettant de prioriser les ASR peuvent être regroupés en
plusieurs grandes catégories :
- Projet
- Performance
- Dépendances

### Projet

- L’exigence est directement associée à une forte valeur métier (bénéfice
  vs coût) ou à un risque métier élevé.
- L’exigence est une préoccupation d’un décideur particulièrement important,
  comme le sponsor du projet ou un auditeur externe chargé de la conformité.
- L’exigence a déjà posé problème et provoqué des situations critiques, des
  dépassements de budget ou de la mécontentement client sur un projet
  antérieur dans un contexte similaire.

### Performance

- L’exigence inclut des caractéristiques de qualité de service (QoS) à
  l’exécution (comme des besoins de performance) qui s’écartent
  significativement de celles déjà satisfaites par l’architecture en évolution.

### Dépendances

- L’exigence introduit ou traite une ou plusieurs dépendances externes pouvant
  avoir un comportement imprévisible, peu fiable et/ou incontrôlable.
- L’exigence a une nature transversale et affecte plusieurs parties du système
  et leurs interactions; elle peut même avoir un impact à l’échelle du système,
  à court et/ou long terme (exemples : sécurité, supervision).
- L’exigence présente un caractère First-of-a-Kind (FOAK). Par exemple,
  l’équipe n’a jamais construit auparavant un composant ou sous-système
  répondant à cette exigence particulière.

## Comment prioriser les ASR en pratique ?

Maintenant que nous avons nos critères d’évaluation, nous pouvons créer un
tableau pour attribuer un score à chaque ASR.

![tableau d'évaluation des exigences](architecturally_significant_requirement.svg)

Une manière de remplir les cellules d’un tel tableau consiste à utiliser des
valeurs simples :
- High = 5
- Medium = 2
- Low = 1
- NA = 0

> [!tip]
> Vous pouvez également utiliser l'échelle de Fibonacci, en particulier si vous
> souhaitez obtenir plus de granularité.

Le score obtenu permet d’obtenir un classement objectif qui doit être réévalué
régulièrement.

Maintenant que nous avons défini des critères objectifs, il est temps de passer
au processus de prise de décision lui-même.

{{< article link="/fr/posts/architecture-decision/" showSummary=true compactSummary=true >}}

> [!info] Quelques liens pour aller plus loin
> - https://www.ozimmer.ch/practices/2020/09/24/ASRTestECSADecisions.html
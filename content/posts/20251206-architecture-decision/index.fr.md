---
title: "Comment prendre des décisions d’architecture efficaces"
slug: "architecture-decision"
date: 2025-12-06
draft: false
description: "Une introduction pratique pour prendre des décisions d’architecture basées sur des faits, pas sur des opinions."
tags: ["Architecture"]
categories: ["tech"]
series: ["Architecture knowledge management"]
series_order: 3
---

En architecture logicielle, chaque choix compte mais certaines décisions
façonnent le système bien plus que d’autres. Ce sont les **décisions**
**d'architecture (ADs)**, et elles définissent la manière dont votre système
répondra à ses exigences les plus importantes.

Prendre la bonne décision ne consiste pas à deviner ou à suivre la voix la plus
forte dans la pièce. Il s’agit **d’analyser les options, de peser les faits**
**et d’être libre de tout biais**.

## Qu’est-ce qu’une AD ?

Une décision d'architecture est un choix de conception logicielle qui répond à
une liste d'[exigences significatives pour l’architecture (ASRs)](/fr/posts/architecturally-significant-requirement).

Il peut s’agir d’une décision à l’échelle du système ou d’une décision locale.
Les personnes impliquées peuvent donc être différentes, mais la manière de
prendre la décision reste la même. Le rôle des architectes dans une
organisation est un sujet complexe que j’aborderai plus tard, mais il est
essentiel que chacun au sein des équipes engineering puisse proposer des idées
et participer à ces décisions.

## Comment prendre une AD ?

> [!quote] Architecting is much more than decomposition.</br>Decomposition is easy, integration is difficult.

Une décision doit être prise sur la base de faits et en partant du problème.
Afin d’éviter tout biais, il est important de suivre une méthodologie
rigoureuse.

![Processus de décision architecturale](architecture_decision.svg "Architecture decision process")

Lors de la phase d’analyse, toutes les solutions, même les plus improbables
(voir stupides), doivent être étudiées.

Lors de l’étape de décision, il est important de rechercher le _consent rather_
_than consensus_, ce qui signifie que l’objectif n’est pas que tout le monde
soit d’accord, mais que personne ne soit fermement opposé à la décision.

De manière générale, une réunion peut convenir, mais comme il s’agit d’un
format synchrone, il est souvent préférable d’opter pour une approche
asynchrone si vous pouvez garantir des réponses rapides.

> [!tip]
> Limitez le nombre de participants aux personnes vraiment indispensables. Cela
> rend les échanges plus fluides, plus efficaces et plus rapides, quel que soit
> le mode de communication.

Avant de conclure cet article, j’aimerais mettre en avant la dernière étape du
processus, cruciale mais souvent négligée. Le suivi du résultat permet de
corriger d’éventuels effets inattendus et contribue à instaurer une culture
d’amélioration continue. Ce monitoring doit inclure des métriques clairement
définies pour mesurer le succès. Il est donc judicieux de définir ces
métriques, de fixer la période de suivi au moment de la décision et de
planifier la revue à l’avance.

Dans le prochain article, nous verrons comment assurer une bonne traçabilité de
cette décision.

{{< article link="/fr/posts/architecture-decision-record/" showSummary=true compactSummary=true >}}

> [!info] Quelques liens pour aller plus loin
> - https://adr.github.io/ad-practices/
> - https://www.gaudisite.nl/ArchitecturalDecisionMakingSlides.pdf
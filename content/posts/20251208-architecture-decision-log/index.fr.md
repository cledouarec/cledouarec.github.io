---
title: "Centraliser vos décisions d'architecture"
slug: "architecture-decision-log"
date: 2025-12-08
draft: false
description: "Apprenez à organiser et accéder efficacement aux décisions d'architecture."
tags: ["architecture"]
categories: ["tech"]
series: ["Architecture knowledge management"]
series_order: 5
---

Suivre les décisions d'architecture est essentiel pour construire des systèmes
maintenables. Un **journal des décisions d'architecture (ADL - architecture**
**decision log)** vous aide à centraliser les décisions, éviter les débats
répétitifs et rendre le raisonnement derrière chaque choix facilement
accessible à tous.

## Qu’est-ce qu’un ADL ?

Un ADL est l’ensemble de tous les ADRs créés et maintenus pour un projet (ou
une organisation) particulier.

Il n’est pas nécessaire de déployer des outils complexes comme des bases de
données. Les ADR sont le plus souvent stockés sous forme de texte dans un wiki
ou avec la documentation du code.

## En pratique

Accéder aux décisions d'architecture doit être aussi simple et rapide que
possible pour garantir qu’elles soient effectivement utilisées. Si le processus
de mise à jour des ADRs est trop lourd, les équipes risquent de ne pas
l’utiliser, ce qui conduit souvent à l’abandon du système.

Dans la plupart des organisations, deux approches courantes sont utilisées,
chacune ayant ses avantages et ses inconvénients. Quel que soit le choix, il
est important de nommer les pages ou fichiers de manière cohérente.

> [!tip]
> Je recommande d’éviter d’inclure des dates dans les noms et d’utiliser plutôt
> un identifiant unique et incrémental. Respectez la convention de nommage de
> votre équipe, comme le `CamelCase`, le `snake_case` ou un format équivalent,
> pour garder les choses claires et cohérentes.

### Approche basée sur un wiki

La première option consiste à utiliser un wiki interne (par exemple, Atlassian
Confluence ou toute autre alternative). Cette approche est simple et rapide à
utiliser, permet de créer des modèles ou des _blueprints_ plus intelligents, et
prend en charge la diffusion automatique, ce qui facilite l’information de
l’ensemble de l’organisation, y compris le personnel non technique.

Ses principaux inconvénients sont le manque de synchronisation avec la base de
code, ce qui peut compliquer le lien entre les décisions et leur mise en œuvre,
et la tentation de modifier les ADR existants plutôt que d’en créer de
nouveaux. Bien que l’édition des pages puisse être restreinte, ce n’est souvent
pas appliqué en pratique.

### Approche basée sur Git

La seconde option consiste à utiliser Git avec Markdown ou ReStructuredText,
selon votre système de documentation. L’intégration des ADR dans les pages
générées améliore l’accessibilité. Cette approche a l’avantage de se rapprocher
du code source et de fournir une traçabilité complète grâce à Git. Un format
léger comme Markdown permet de se concentrer sur l’essentiel et réduit la
tentation de surcharger les ADR avec des diagrammes inutiles. Vous pouvez
également mettre en place des hooks de validation pour vous assurer que les ADR
sont correctement remplies et que les ADR existantes ne sont pas modifiées de
manière incorrecte.

Le principal inconvénient est la diffusion de l’information à l’ensemble de
l’organisation, le personnel non technique peut avoir plus de difficultés à
naviguer dans un dépôt Git pour retrouver l’information si aucun front end
n'est disponible.

> [!tip]
> Bien que les deux approches soient viables, je tends personnellement à
> privilégier l’utilisation de Git avec Markdown.

Cette série d’articles se termine ici, en espérant qu’elle aura contribué à
démystifier les ADR et vous aura encouragé à les utiliser dans votre
organisation.

> [!info] Quelques liens pour aller plus loin
> - https://adr.github.io/adr-tooling/
> - https://github.com/joelparkerhenderson/architecture-decision-record
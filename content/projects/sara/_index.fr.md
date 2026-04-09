---
title: "SARA"
description: "Un outil en ligne de commande pour rassembler exigences et documents d'architecture en un graphe de connaissances traçable."
---

SARA (Solution Architecture Requirement for Alignment) s'attaque à un problème
récurrent dans les organisations complexes : des exigences et des documents
d'architecture éparpillés entre équipes, dépôts et formats, rendant la
traçabilité laborieuse et la cohérence illusoire.

L'outil rassemble les documents issus de plusieurs dépôts Git en un graphe de
connaissances unifié. Il relie les besoins métier aux détails d'implémentation
selon une hiérarchie claire : solutions, cas d'usage, scénarios, exigences
système, architecture et conceptions détaillées.

Fonctionnalités clés :
- **Validation** — détection des références cassées, dépendances circulaires,
  éléments orphelins et doublons
- **Traçabilité** — navigation vers les besoins métier en amont ou vers
  l'implémentation en aval
- **Rapports** — génération de rapports de couverture et de matrices de
  traçabilité
- **Comparaison** — visualisation des écarts entre commits ou branches
- **Intégration IA** — exploitation du graphe comme base de connaissances pour
  des agents IA, capables de générer ou d'affiner exigences et documentation

Le parti pris : des fichiers markdown avec métadonnées YAML. Aucune dépendance
à un éditeur propriétaire, gestion de versions native, revue de code facilitée.

{{< github repo="cledouarec/sara" showThumbnail=true >}}

Cette section regroupe les annonces, tutoriels et articles consacrés à SARA.

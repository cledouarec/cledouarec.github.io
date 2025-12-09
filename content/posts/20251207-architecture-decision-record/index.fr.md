---
title: "Comment rédiger une ADR efficacement"
slug: "architecture-decision-record"
date: 2025-12-07
draft: false
description: "Apprenez à consigner clairement et efficacement les décisions architecturales clés avec les ADRs."
tags: ["Architecture"]
categories: ["tech"]
series: ["Architecture knowledge management"]
series_order: 4
---

Les décisions architecturales ne se prennent pas uniquement en réunion, elles
vivent dans les **ADRs**.
Voyons comment rédiger des fiches claires et utiles qui résistent à l’épreuve
du temps.

## Qu’est-ce qu’une ADR ?

Une ADR est un document qui capture une [décision d'architecture (AD)](/fr/posts/architecture-decision)
importante prise avec son contexte et ses conséquences.

Une ADR est l’élément clé d’un système de [gestion des connaissances d'architecture](/fr/posts/architecture-knowledge-management).

## Comment créer une ADR ?

Une ADR doit contenir au moins les éléments suivants :
- Contexte
- Décideurs
- Décision
- Conséquence
- Alternatives

> [!warning]
> Ne modifiez pas les informations existantes dans une ADR. Ajoutez plutôt de
> nouvelles informations, ou remplacez l’ADR en créant une nouvelle ADR.

Chaque ADR doit porter sur une seule AD, et non sur plusieurs.

> [!error] Anti-pattern
> _Mega-ADR_ : Beaucoup d’informations détaillées sur l’architecture sont
> entassées dans plusieurs ADRs de plusieurs pages servant de documentation
> principale. Par exemple, les responsabilités et modalité de collaboration des
> composants sont précisées, ou plusieurs diagrammes ou extraits de code
> apparaissent dans l’ADR (un par option est généralement suffisant). Bien que
> ces informations puissent être utiles, elles devraient être présentées dans
> des modèles ou documents créés à cet effet.

> [!success] Bonne pratique
> Déplacez les informations de design détaillé dans un document séparé.

### Contexte

Une description du contexte de la situation et du problème soulevé aide à
comprendre plus tard si la décision doit être réexaminée.

Elle doit décrire la situation de votre organisation, les priorités métier et
le défi technologique.

L’ADR doit être datée, ce qui est particulièrement important pour les
aspects susceptibles de changer dans le temps, comme les coûts, les
calendriers, la montée en charge, etc.

> [!error] Anti-pattern
> _Maze_ : Le sujet de l’ADR ne correspond pas à son contenu ; la discussion
> s’égare et se concentre sur des détails non pertinents dans le contexte
> donné. Par exemple, une discussion intéressante sur les qualités positives
> d’une option qui n’a aucun rapport avec le problème et les parties prenantes
> concernées.

> [!success] Bonne pratique
> Refactorez l’ADR, déplacez les parties moins pertinentes en annexe ou dans un
> _parking lot_ (si vous n’êtes pas prêt à les supprimer).

### Décideurs

Les décideurs doivent être identifiés, ce qui aide à les rendre responsables de
l’application de la décision.

### Décision

La décision prise doit être rédigée de manière simple mais précise. L’objectif
est de voir l’action résultante de la discussion.

> [!error] Anti-pattern
> _Fairy Tale_ (ou Wishful Thinking) : Une justification superficielle est
> donnée, par exemple uniquement les avantages et pas les inconvénients. Les
> cas particuliers de cet anti-pattern sont les truismes et tautologies.
>
> Exemple :
> > Nous avons choisi un load balancer parce qu’il équilibre la charge, ce qui
> > est une bonne chose.

> [!error] Anti-pattern
> _Sales Pitch_ : Évitez les exagérations et les vantardises. Soyez toujours
> prêt à répondre aux questions sur vos affirmations et leurs preuves. Inclure
> tout le contexte pertinent gonflerait l’ADR; des hyperliens ou références
> bibliographiques peuvent être fournis à la place.
>
> Exemple (intentionnellement exagéré) :
> > Nous avons choisi cette technologie exceptionnelle car elle est sans égale
> > sur le marché. Ses performances splendides brillent partout, et tous ses
> > utilisateurs sont extraordinairement heureux en permanence.
>
> Quelle est la véracité de cette affirmation ? Quels mots peuvent être
> supprimés sans perdre le sens technique ? Combien de contre-exemples sont
> nécessaires pour la réfuter ?

### Conséquence

Une ADR décrit une décision significative pour un projet spécifique.
Elle doit avoir un impact sur la façon dont le reste du projet sera mené.

Cette section décrit le contexte résultant après application de la décision.
Toutes les conséquences doivent y être listées, pas seulement les "positives".
Une décision particulière peut avoir des conséquences positives, négatives et
neutres, mais toutes influencent l’équipe et le projet à l’avenir.

> [!error] Anti-pattern
> _Free Lunch Coupon_ (ou Candy Bar) : Aucune conséquence n’est documentée, ou
> seules celles apparemment inoffensives. Les plus difficiles sont ignorées par
> accident ou volontairement, celles qui se matérialisent seulement à long
> terme.
>
> Exemple :
> > Nous avons choisi une architecture _event-driven_ car elle découple les
> > composants entre eux.
>
> Cela peut être vrai, au moins pour la dimension temporelle du découplage.
> Mais qu’en est-il du travail de conception, d’implémentation et de test
> supplémentaire ? La définition du schéma d’événement ne couple-t-elle pas le
> récepteur à l’émetteur (dimension format) ?

> [!error] Anti-pattern
> _Tunnel Vision_ : Seul un contexte local et isolé est considéré. Les qualités
> de développement sont souvent couvertes, mais les conséquences pour
> l’exploitation et la maintenance sont insuffisamment prises en compte.

> [!success] Bonne pratique
> Ajoutez des critères comme la maintenabilité et l’évolutivité et commentez
> comment la solution choisie se situe par rapport à eux.

### Options alternatives

Lors de la discussion de la [décision d'architecture](/fr/posts/architecture-decision),
les alternatives doivent être évaluées et inclure les avantages et
inconvénients pertinents.
Ces alternatives sont décrites selon vos besoins et objectifs.

> [!error] Anti-pattern
> _Dummy Alternative_ : Une solution est inventée et présentée comme option,
> mais ne fonctionne pas du tout dans le contexte donné. Ce choix vise à
> mettre en valeur l’option préférée et à donner l’impression que plusieurs
> alternatives ont été évaluées, ce qui n’est pas vraiment le cas.
>
> Exemple :
> > Nous avons choisi PostgresSQL comme base relationnelle. Nous aurions pu
> > implémenter notre propre SGBD relationnel, mais cela prend du temps et des
> > efforts.
>
> Cela apporte-t-il un nouvel insight pertinent ? Pourquoi ne pas mentionner
> d’autres produits existants ou solutions open source comme MariaDB ?

> [!error] Anti-pattern
> _Sprint_ (ou Rush) : Une seule option est considérée. Seuls les effets à
> court terme sont discutés, concernant les deux ou trois prochaines itérations
> du projet.

> [!success] Bonne pratique
> Recherchez des alternatives valides, par exemple en ligne ou via vos réseaux
> professionnels. Rapportez les résultats de la recherche, un ADR est avant
> tout un journal d’activité. Mentionnez également les conséquences à moyen et
> long terme.

## Template d'example d'une ADR

```markdown
# Short title of solved problem and solution


- Status: [proposed | rejected | accepted | deprecated | … | superseded by [ADR-XXXX]]
- Deciders: [list everyone involved in the decision]
- Date: [YYYY-MM-DD when the decision was last updated]
- Ticket: [Optional ticket/issue URL]

## Context and problem statement

[Describe the context and problem statement, e.g., in free form using two to
three sentences. You may want to articulate the problem in form of a question.]

## Key factors

- [driver 1, e.g., a force, facing concern, …]
- [driver 2, e.g., a force, facing concern, …]
- …

## Considered options

- [option 1]
- [option 2]
- [option 3]
- …

## Decision Outcome

Chosen option: "[option 1]", because [justification. e.g., only option, which
meets k.o. criterion decision driver | which resolves force force | … | comes
out best (see below)].

### Positive Consequences

- [e.g., improvement of quality attribute satisfaction, follow-up decisions
  required, …]
- …

### Negative Consequences

- [e.g., compromising quality attribute, follow-up decisions required, …]
- …

## Pros and Cons of the Options

### [option 1]

[example | description | pointer to more information | …]

- Good, because [argument a]
- Good, because [argument b]
- Bad, because [argument c]
- …

### [option 2]

[example | description | pointer to more information | …]

- Good, because [argument a]
- Good, because [argument b]
- Bad, because [argument c]
- …

### [option 3]

[example | description | pointer to more information | …]

- Good, because [argument a]
- Good, because [argument b]
- Bad, because [argument c]
- …

## Links

- [Link to reference used to help the decision]
- …
```

{{< article link="/fr/posts/architecture-decision-log/" showSummary=true compactSummary=true >}}

> [!info] Quelques liens pour aller plus loin
> - https://adr.github.io/adr-templates/
> - https://github.com/joelparkerhenderson/architecture-decision-record
> - https://www.ozimmer.ch/practices/2023/04/03/ADRCreation.html
> - https://cognitect.com/blog/2011/11/15/documenting-architecture-decisions
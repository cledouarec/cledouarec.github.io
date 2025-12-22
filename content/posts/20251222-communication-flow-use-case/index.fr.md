---
title: "Mordor Services - Un anneau, un lancement"
slug: "communication-flow-use-case"
date: 2025-12-22
draft: false
description: "Une étude de cas pratique sur l’amélioration des flux de communication dans une entreprise technologique de taille intermédiaire."
tags: ["use case"]
categories: ["organization"]
series: ["Team structure"]
series_order: 2
---

## Cas d’usage

### Contexte de l’entreprise

Mordor Services est une entreprise technologique de taille intermédiaire
d’environ 240 employés, spécialisée dans la conception et la fabrication
d’objets IoT connectés. Elle est principalement connue pour son produit phare:
**une bague connectée intelligente** utilisée pour l’authentification, le
contrôle d’accès et les interactions sécurisées avec des systèmes numériques.

Le produit combine:
- du hardware (la bague physique),
- du firmware,
- des applications mobiles,
- des services cloud.

> [!abstract] Il est commercialisé comme une solution intégrée
> Une Bague pour tous les authentifier,</br>
> Une Application pour les guider,</br>
> Un Cloud pour les lier,</br>
> Et en production les expédier.

L’entreprise est organisée autour de:
- The Council (CEO, COO, CTO, Head of Sales),
- Product Management,
- Hardware Engineering,
- Software & Cloud Engineering,
- Manufacturing & Supply Chain,
- Sales & Partnerships,
- Customer Support & Operations.

Mordor Services est fière de concevoir des _objets simples reposant sur des_
_systèmes puissants_.
En interne, on plaisante souvent en disant que _la Bague est peut-être_
_petite, mais que le chemin pour l’expédier est long_.

### La situation

Mordor Services se prépare au lancement d’une nouvelle génération de sa bague
connectée, introduisant:
- une autonomie accrue,
- un chiffrement renforcé,
- une intégration plus poussée avec les systèmes d’entreprise.

La nouvelle bague a déjà été présentée à des clients et partenaires clés.
Certains contrats et renouvellements dépendent explicitement de sa
disponibilité.

Face à la pression concurrentielle exercée par d’autres fabricants de wearables
et des startups au-delà de la _Porte Noire_, le Conseil décide d’avancer la
date de lancement d’un mois. La décision est annoncée lors d’une réunion
générale.

Le message est clair dans son intention:
- le lancement est critique,
- le marché n’attendra pas,
- Mordor Services doit avancer comme un seul bloc.

Ce qui est moins clair:
- quelles fonctionnalités sont indispensables pour le lancement,
- lesquelles peuvent être reportées,
- comment les arbitrages entre hardware, firmware et logiciel doivent être
- gérés.

Aucun décret écrit ne suit cette annonce. Chacun repart convaincu d’avoir
compris la mission.

### De nombreux artisans, une seule Bague

Les chefs de produit interprètent le message comme un engagement ferme:
> [!quote] La nouvelle Bague doit être livrée avec toutes les fonctionnalités promises, en garantissant que sa forme, sa fonction et sa magie restent intactes.

Ils compressent la feuille de route et partent du principe que l’ensemble du
périmètre fonctionnel demeure inchangé.

Les ingénieurs hardware, eux, identifient immédiatement des contraintes:
- les délais des fournisseurs,
- les risques de rendement en production,
- les limites liées à la batterie.

Discrètement, ils décident de figer certains éléments de conception plus tôt
que prévu afin d’éviter des retards de fabrication.

Pendant ce temps, les équipes logiciel et firmware poursuivent le développement
de fonctionnalités avancées, déjà présentées dans les premiers prototypes, en
supposant que le matériel les supportera pleinement.

La production se prépare sur la base du dernier design hardware validé, sans
savoir que certaines fonctionnalités dépendantes du logiciel pourraient ne pas
survivre.

Les équipes commerciales rassurent clients et partenaires:
> [!quote] La nouvelle Bague arrivera plus tôt, exactement comme vous l’avez vue.

Chaque groupe est convaincu de protéger la Bague. Chacun porte pourtant une
compréhension différente de ce qu’est réellement la Bague.

### Une fissure dans la forge

À mi-parcours du développement, les ingénieurs hardware découvrent un problème:
dans certaines conditions, le nouveau module de chiffrement augmente la
consommation d’énergie, mettant en péril l’autonomie et la fiabilité à long
terme.

Le sujet est discuté au sein de l’équipe hardware puis remonté à leur manager.
Craignant de déclencher une refonte plus large, l’escalade est retardée dans
l’espoir de trouver un contournement.

Les semaines passent. La date de lancement approche. Le risque demeure.
Lorsque le problème atteint enfin le Conseil, les plannings de production sont
déjà engagés.

Du côté du Conseil :
> [!question] Comment cela n’a-t-il pas été corrigé plus tôt ?

Du côté de l’ingénierie :
> [!quote] C’était connu. Mais l’alerte n’a jamais quitté la forge.

### Raccourciss, conséquences durables

À mesure que la pression augmente, la communication informelle se répand. Un
responsable d'un partenaire contacte directement un ingénieur firmware:
> [!question] Officieusement, la Bague supporte-t-elle vraiment ce mode ?

L’ingénieur répond honnêtement. Le produit n’est pas informé.

Des raccourcis similaires se multiplient:
- les équipes commerciales parlent directement aux ingénieurs,
- les ingénieurs fournissent des réponses nuancées,
- l’équipe produit découvre des engagements une fois que les partenaires les
  répètent comme des faits établis.

Les promesses se forgent bague par bague, conversation après conversation.

### L’Œil au-dessus de l’usine

Pour éviter de nouvelles surprises, de plus en plus de personnes commencent à
mettre le CTO en copie des emails, discussions et documents de conception.

Progressivement, le CTO devient l’Œil au-dessus de la forge:
- il approuve les changements hardware,
- valide les arbitrages fonctionnels,
- arbitre l’état de préparation au lancement.

Lorsque l’Œil observe, les décisions avancent. Lorsqu’il se détourne:
- les équipes attendent,
- la production hésite,
- le logiciel suspend les déploiements.

Ce qui avait commencé comme une mesure de contrôle devient un goulet
d’étranglement.

### L’assemblage final

À l’approche du lancement:
- les partenaires reçoivent des réponses différentes selon leur interlocuteur,
- l’équipe produit passe son temps à réconcilier les versions de la Bague,
- l’ingénierie travaille dans une urgence permanente,
- la production fige des décisions plus tôt que souhaité,
- le Conseil perçoit un risque croissant.

Tout le monde s’accorde sur le fait que la Bague doit être livrée. Personne ne
s’accorde sur la version de la Bague qui est réellement en train d’être
construite.

## Analyse des flux de communication

### Communication descendante

Ce cas d’usage illustre un flux de communication descendante prenant sa source
au Conseil et se diffusant dans l’ensemble de l’organisation.

> [!abstract] Rôle attendu
> La communication descendante devrait:
> - clarifier l’intention et les priorités,
> - définir les éléments non négociables et les contraintes,
> - établir des périmètres de décision clairs.

> [!note] Comportement observé
> Le Conseil annonce une accélération du lancement lors d’une réunion générale.
> Le message met l’accent sur l’urgence et l’unité, mais manque de détails
> opérationnels.
>
> Aucun suivi écrit ne précise:
> - les fonctionnalités obligatoires,
> - les arbitrages acceptables,
> - la responsabilité des décisions.

> [!error] Problèmes
> En conséquence, les équipes interprètent le même message de manière différente.
> Le produit suppose que l’ensemble des fonctionnalités doit être livré.
> L’ingénierie estime que des compromis sont acceptables. La production fige
> les conceptions très tôt. Les équipes commerciales considèrent que la version
> démontrée reste la référence.

> [!conclusion]
> Le problème n’est pas un manque de communication, mais un manque de clarté
> opérationnelle. La stratégie est communiquée comme une intention plutôt que
> comme un cadre directement actionnable.

### Communication ascendante

Dans ce scénario, l’information remonte des équipes vers le Conseil, permettant
en théorie à la direction de recevoir des signaux et des risques potentiels.

> [!abstract] Rôle attendu
> La communication ascendante devrait:
> - faire émerger les risques le plus tôt possible,
> - permettre des décisions éclairées au niveau de la direction,
> - transmettre les signaux sans filtrage excessif.

> [!note] Comportement observé
> Dans ce cas, les ingénieurs hardware identifient un problème de consommation
> électrique qui menace l’autonomie et la fiabilité à long terme. Le sujet est
> discuté au sein de l’équipe et remonté au management, mais l’escalade est
> retardée afin d’éviter de déclencher une refonte ou un impact sur le planning.

> [!error] Problèmes
> Les informations liées aux risques sont filtrées et circulent lentement.
> Lorsque le problème atteint finalement le Conseil, les plannings de
> production sont déjà engagés et les marges de manœuvre fortement réduites.

> [!conclusion]
> Une escalade tardive contraint la direction à des décisions réactives et crée
> de la frustration des deux côtés. La confiance s’érode lorsque les problèmes
> semblent apparaître « trop tard », alors qu’ils étaient connus bien plus tôt.

### Communication horizontale

Les équipes de même niveau communiquent latéralement entre elles, formant un
flux horizontal qui devrait soutenir l’alignement entre les fonctions.

> [!abstract] Rôle attendu
> La communication horizontale devrait:
> - aligner les interprétations,
> - résoudre les dépendances,
> - maintenir une compréhension partagée.

> [!note] Comportement observé
> Produit, hardware, logiciel, production et ventes travaillent en parallèle.
> Aucun forum structuré n’existe pour réconcilier:
> - les attentes fonctionnelles,
> - les contraintes techniques,
> - les réalités de production.

> [!error] Problèmes
> L’alignement repose sur des échanges informels. Les décisions sont supposées
> plutôt que validées.

> [!conclusion]
> Le désalignement s’accumule silencieusement. Les différences ne sont
> découvertes que tardivement, lorsque les changements deviennent coûteux ou
> impossibles.

### Communication diagonale

Certaines communications voyagent en diagonale, traversant niveaux et fonctions
pour connecter des collaborateurs qui autrement n’interagiraient pas
directement.

> [!abstract] Rôle attendu
> La communication diagonale devrait:
> - rester exceptionnelle et transparente,
> - soutenir l’alignement, pas le contourner.

> [!note] Comportement observé
> Sous pression, les équipes commerciales et les responsables chez les
> partenaires contactent directement les ingénieurs pour clarifier les
> capacités. Les ingénieurs répondent honnêtement sur le plan technique, mais
> sans contexte produit complet. L’équipe produit n’est pas informée de ces
> échanges.

> [!error] Problèmes
> Ces raccourcis contournent les mécanismes de coordination et créent des
> engagements cachés. Les clients reçoivent des réponses techniquement exactes
> mais incomplètes, qui deviennent ensuite des attentes contractuelles.

> [!conclusion]
> La communication diagonale devient un mécanisme de contournement face à des
> processus peu clairs, augmentant l’incohérence plutôt que de la réduire.

### Communication en hub

Le CTO agit ici comme un hub, centralisant la communication et servant de point
focal pour plusieurs équipes et décisions.

> [!abstract] Rôle attendu
> Un hub devrait:
> - arbitrer les conflits rares,
> - fournir un alignement temporaire,
> - ne pas remplacer les flux standards.

> [!note] Comportement observé
> À mesure que l’incertitude croît, de plus en plus de personnes mettent le CTO
> en copie des emails, discussions et documents. Le CTO approuve de plus en
> plus les changements hardware, valide les arbitrages fonctionnels et
> arbitre la préparation au lancement.

> [!error] Problèmes
> L’autorité décisionnelle migre vers le haut. Les équipes attendent au lieu de
> décider.

> [!conclusion]
> Ce qui commence comme une mesure de contrôle se transforme en goulet
> d’étranglement, réduisant l’autonomie des équipes et ralentissant
> l’organisation.

### Schéma systémique des flux croisés

Les dysfonctionnements se renforcent mutuellement:
- Une communication descendante floue conduit à des interprétations
  divergentes.
- Une communication ascendante peu sûre retarde la visibilité des risques.
- Une communication horizontale faible laisse les incohérences se développer.
- Les raccourcis diagonaux créent des engagements cachés.
- La surcharge du hub devient le mécanisme de coordination par défaut.

> [!error] Aucun flux unique ne tombe en panne isolément.

Les problèmes de communication ne sont pas souvent dus au fait que les gens ne
discutent pas. Ils concernent plutôt **la manière dont l’information circule,**
**le moment où elle circule et qui est autorisé à décider**.

Ce cas d’usage démontre que même des équipes compétentes et un leadership fort
peuvent échouer sans une conception intentionnelle des flux de communication.

## Forger des chemins clairs pour la communication

À grande échelle, la communication doit être **conçue**, et non improvisée. Les
principes opérationnels suivants définissent comment l’information, les
décisions et les risques doivent circuler dans l’organisation pour éviter
ambiguïtés, désalignements et goulets d’étranglement.

### Formaliser les décisions stratégiques par écrit

Les décisions stratégiques ne doivent pas rester confinées aux réunions ou aux
présentations. Chaque décision majeure, comme avancer une date de lancement,
doit être accompagnée d’un résumé écrit succinct qui précise clairement:
- l’objectif,
- les éléments non négociables,
- les arbitrages acceptables,
- le responsable de la décision.

Ce document devient le point de référence unique pour toutes les équipes. Il
supprime l’ambiguïté, limite les interprétations divergentes et permet aux
équipes d’agir rapidement sans demander de clarifications répétées.

En faisant des décisions écrites la norme, l’organisation améliore la
communication descendante grâce à la clarté et à la cohérence, renforce
l’alignement horizontal entre les équipes, et réduit les escalades inutiles
vers la direction.

### Définir des règles d’escalade explicites pour les risques

Les risques ne doivent pas dépendre du jugement individuel pour décider quand
ils méritent de l’attention. L’organisation doit définir des règles d’escalade
claires précisant quels types de risques nécessitent une visibilité immédiate
et à quel moment l’escalade devient obligatoire.

Tout problème menaçant la sécurité, la fiabilité, le périmètre ou les délais de
livraison au-delà d’un seuil convenu doit être escaladé tôt et de manière
explicite. L’escalade doit être considérée comme une responsabilité, et non
comme un échec.

Des règles d’escalade claires améliorent la communication ascendante en faisant
remonter les risques plus tôt, permettant de prendre de meilleures décisions
au niveau de la direction et réduisant les interventions de dernière minute
dictées par la surprise.

### Mettre en place un forum de lancement inter-fonctions

L’alignement entre équipes ne doit pas dépendre de conversations informelles ou
d’initiatives individuelles. Un forum permanent inter-fonctions doit exister
pour assurer l’alignement sur les initiatives critiques, comme les lancements
produit.

Ce forum réunit Produit, Ingénierie, Production, Ventes et Support afin
d’arbitrer le périmètre, résoudre les dépendances et maintenir une vision
commune de la réalité. Il devient l’espace par défaut où les compromis sont
discutés et validés.

Institutionnaliser ce forum renforce la communication horizontale, réduit les
divergences silencieuses et garantit que les décisions se propagent de manière
cohérente à travers les équipes.

### Rendre la communication diagonale visible par défaut

La communication directe et inter-niveaux est parfois nécessaire pour la
rapidité, mais elle ne doit jamais rester invisible. Tout échange diagonal
clarifiant le périmètre, les engagements ou les comportements envers les
clients doit être résumé et partagé avec les parties prenantes concernées.

L’objectif est la visibilité, non la restriction. Si une décision ou une
clarification n’est pas visible par l’équipe Produit et le forum de lancement,
elle ne doit pas être considérée comme valide.

Cette approche préserve les bénéfices de rapidité de la communication diagonale
tout en empêchant les engagements cachés et le désalignement entre équipes.

### Séparer l’autorité de décision de l’autorité d’escalade

Le leadership doit définir des limites, et non approuver chaque décision. Les
équipes doivent savoir ce qu’elles peuvent décider de manière autonome et à
quel moment l’escalade est nécessaire.

L’autorité de décision doit être distribuée dans des limites clairement
documentées, tandis que l’autorité d’escalade reste un mécanisme pour résoudre
les conflits ou les exceptions. Les leaders interviennent pour ajuster les
périmètres, pas pour valider les choix de routine.

Cette séparation réduit la surcharge du hub, restaure l’autonomie des équipes
et permet aux décisions d’avancer sans dépendre de la disponibilité d’un
individu.

### Maintenir une source unique de vérité pour les engagements

Des versions contradictoires de la réalité émergent lorsque les engagements
sont éparpillés entre conversations, emails et présentations. Une référence
unique et partagée doit exister pour décrire ce qui sera livré, ce qui est
différé et ce qui est à risque.

Cette source de vérité doit être continuellement mise à jour et consultée par
Produit, Ventes, Support et Ingénierie avant de prendre ou confirmer des
engagements.

En centralisant les engagements, l’organisation améliore l’alignement entre
équipes, limite les hypothèses et détecte les divergences tôt.

### Déplacer le focus du leadership des réponses vers les signaux

Lorsque le leadership valorise principalement la certitude et les réponses,
les équipes apprennent à filtrer l’information. Les leaders devraient plutôt
encourager la remontée précoce de signaux, l’incertitude et les préoccupations
incomplètes.

En posant systématiquement des questions sur ce qui semble risqué, quelles
hypothèses pourraient être fragiles, et ce qui pourrait surprendre
l’organisation, le leadership crée un espace pour une communication ascendante
honnête.

Ce changement améliore la visibilité des risques, renforce la confiance et
réduit le besoin de décisions réactives de dernière minute.

## L’amélioration commence par l’observation

Ce cas d’usage peut sembler caricatural, mais il reflète des situations que
j’ai rencontrées de nombreuses fois dans de vraies organisations. Les
défaillances de communication décrites ici sont rarement exceptionnelles; elles
apparaissent naturellement lorsque la croissance, la pression et la complexité
augmentent plus rapidement que le système de communication lui-même.

Les principes proposés pour résoudre ces problèmes ne sont ni nouveaux ni
complexes. Ils relèvent en grande partie du bon sens. Pourtant, lorsqu’ils sont
appliqués de manière cohérente, ils permettent de résoudre non seulement des
problèmes de communication, mais aussi de nombreuses autres dysfonctionnalités
organisationnelles. Pour cette raison, j’ai volontairement présenté des
variantes synchrones et asynchrones. Je vous encourage également à prendre le
temps d’explorer des versions asynchrones des principes synchrones, et vice
versa, afin de vérifier votre compréhension de leurs différences et de leurs
impacts sur l’organisation.

**Il n’existe pas de recette universelle à appliquer telle quelle**. Plutôt que
de copier des pratiques en bloc, les organisations doivent adopter une démarche
d’amélioration continue. Une approche PDCA, soutenue par des données et des
signaux observables, est beaucoup plus efficace que des cadres statiques ou des
solutions à la mode.

Enfin, **les flux de communication ne doivent jamais être optimisés isolément**.
Améliorer un flux local peut rendre une équipe plus rapide ou plus confortable,
mais si le résultat global n’est pas aligné avec les valeurs et les objectifs de
l’organisation, la dysfonction réapparaîtra ailleurs. Définir ce qui compte
vraiment et mesurer si le système évolue dans cette direction est ce qui
détermine ultimement le succès.

> [!info] Quelques liens pour aller plus loin
> - [Using the PDCA Cycle to Support Continuous Improvement (Kaizen)](https://theleanway.net/the-continuous-improvement-cycle-pdca)
> - [How did we shift to asynchronous communication… through baby steps?](https://robin-bonduelle.medium.com/how-did-we-shift-to-asynchronous-communication-through-baby-steps-ce816538afd8)
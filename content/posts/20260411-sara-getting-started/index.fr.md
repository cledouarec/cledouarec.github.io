---
title: "Premiers pas avec SARA : les exigences comme du code"
slug: "sara-getting-started"
date: 2026-04-11
description: >
    Apprenez à gérer des documents d'architecture et des exigences sous forme
    de graphe de connaissances interconnecté avec SARA, un outil CLI basé sur
    Markdown.
tags: ["traceability", "requirements", "architecture"]
categories: ["tech"]
projects: ["sara"]
---

Dans les organisations complexes, les exigences et les documents d'architecture
sont souvent dispersés entre les équipes, les outils et les dépôts. Maintenir
la cohérence de l'ensemble est un défi permanent. Et si vos exigences pouvaient
vivre sous forme de simples fichiers Markdown dans Git, versionnés, revus et
interconnectés comme du code?

C'est exactement ce que fait **SARA**.

**SARA** (**S**olution **A**rchitecture **R**equirement for **A**lignment) est
un outil en ligne de commande qui gère les documents d'architecture et les
exigences sous forme de graphe de connaissances interconnecté. Pas de base de
données, pas de serveur, pas d'abonnement. Juste des fichiers Markdown avec un
frontmatter YAML et un CLI puissant pour valider, interroger et générer des
rapports.

Dans cet article, nous explorerons la logique hiérarchique qui relie tous les
types de documents, puis nous construirons pas à pas une petite hiérarchie
d'exigences pour un **système de contrôle domotique** en utilisant les outils
CLI, d'une solution de haut niveau jusqu'aux conceptions détaillées.

## Installation

Installez SARA depuis crates.io:

```bash
cargo install sara-cli
```

> [!note]
> SARA dépend de `git2`, qui nécessite des bibliothèques système comme OpenSSL.
> Si la compilation échoue, consultez la
> [documentation du crate openssl](https://docs.rs/openssl/latest/openssl/)
> pour les instructions d'installation spécifiques à votre plateforme.

Vérifiez l'installation:

```bash
sara --version
```

## Mise en place du projet

Créez un répertoire de projet et initialisez la configuration de SARA:

```bash
mkdir smart-home && cd smart-home
mkdir docs
```

Par défaut, SARA scanne la racine du dépôt à la recherche de documents
Markdown. Vous pouvez personnaliser ce comportement en créant un fichier de
configuration `sara.toml` à la racine. Ce fichier contient toutes les options
de configuration, mais nous garderons un exemple très simple ici:

```toml
[repositories]
paths = ["./docs"]

[output]
colors = true
emojis = true
```

La liste `paths` indique à SARA où chercher les documents Markdown. Vous
pouvez lister plusieurs répertoires ou même des chemins vers d'autres dépôts
Git pour agréger des documents provenant de différentes sources.

## Création de vos premiers documents

SARA reconnaît 10 types de documents formant une hiérarchie de traçabilité, des
Solutions de haut niveau jusqu'aux conceptions détaillées matériel et logiciel.
Chaque document est un simple fichier Markdown avec un frontmatter YAML que SARA
utilise pour construire le graphe de connaissances. Le corps du fichier est du
Markdown libre où vous rédigez le contenu.

> [!tip]
> SARA est livré avec des modèles par défaut pour chaque type de document, mais
> vous pouvez les remplacer par les vôtres en plaçant des modèles personnalisés
> dans un répertoire et en le référençant dans `sara.toml`.

Pour créer des documents, SARA fournit la commande `sara init`. Elle génère le
frontmatter YAML pour vous, afin que vous n'ayez pas à retenir les noms exacts
des champs et leur structure. Chaque type de document a sa propre sous-commande
avec un alias court (par exemple, `sol` pour Solution, `uc` pour Use Case).

> [!tip]
> Vous pouvez aussi lancer `sara init` sans argument. SARA démarrera un mode
> interactif qui vous guide pas à pas dans la sélection du type, la génération
> de l'identifiant et la configuration des relations.

Construisons notre hiérarchie domotique de haut en bas.

### La Solution

Tout commence par une Solution. C'est l'élément de plus haut niveau qui
représente le produit ou le système que vous construisez. Créez un fichier
Markdown et initialisez-le:

```bash
sara init sol docs/SOL-SMARTHOME.md \
  --id SOL-SMARTHOME \
  --name "Smart Home Control System" \
  -d "Integrated home automation and control system"
```

SARA insère le frontmatter YAML suivant en haut du fichier:

```markdown
---
id: "SOL-SMARTHOME"
type: solution
name: "Smart Home Control System"
description: "Integrated home automation and control system"
---
```

Sous ce bloc, vous pouvez écrire tout le contenu Markdown que vous souhaitez:
une vue d'ensemble du produit, des diagrammes, des liens vers des ressources
externes. SARA ne lit que le frontmatter pour les besoins de la traçabilité.

### Cas d'utilisation

Maintenant que nous avons une Solution, nous devons décrire ce que les
utilisateurs en attendent. C'est le rôle des cas d'utilisation. Chaque cas
d'utilisation est lié à la Solution qu'il raffine, créant le premier niveau de
traçabilité:

```bash
sara init uc docs/UC-LIGHTS.md \
  --id UC-LIGHTS \
  --name "Lighting Control" \
  -d "Control and automate smart lighting throughout the home" \
  --refines SOL-SMARTHOME
```

Le frontmatter généré inclut désormais un champ `refines`:

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

Cette relation `refines` indique à SARA que `UC-LIGHTS` est un enfant de
`SOL-SMARTHOME` dans le graphe de traçabilité. Vous n'avez besoin de définir le
lien que dans une seule direction. SARA infère automatiquement l'inverse, donc
la Solution connaîtra ce cas d'utilisation sans que vous ayez à modifier
`SOL-SMARTHOME.md`.

> [!tip]
> SARA supporte à la fois les liens ascendants (`refines`, `derives_from`,
> `satisfies`) et leurs équivalents descendants (`is_refined_by`, `derives`,
> `is_satisfied_by`). Cependant, la pratique recommandée est de toujours
> utiliser les liens ascendants. Les éléments de niveau inférieur doivent
> pointer vers les éléments de niveau supérieur dont ils proviennent. Cela
> reflète le flux naturel de connaissance : un cas d'utilisation sait à quelle
> Solution il appartient, mais une Solution ne devrait pas avoir à lister
> manuellement chaque cas d'utilisation.

### Scénarios

Les scénarios décomposent les cas d'utilisation en comportements concrets. Ils
décrivent des interactions ou des flux spécifiques. Créons-en un pour le
réglage de la luminosité:

```bash
sara init scen docs/SCEN-DIMMER.md \
  --id SCEN-DIMMER \
  --name "Adjust Light Brightness" \
  --refines UC-LIGHTS
```

La même relation `refines` relie ce scénario à son cas d'utilisation parent.

### Exigences système

À partir des scénarios, nous dérivons des exigences quantifiables. Ce sont les
énoncés "SHALL" qui spécifient ce que le système doit faire. La relation passe
de `refines` à `derives_from`, reflétant le fait que les exigences sont dérivées
des scénarios plutôt que de les raffiner:

```bash
sara init sysreq docs/SYSREQ-LATENCY.md \
  --id SYSREQ-LATENCY \
  --name "Device Command Latency" \
  -d "Maximum allowed latency for device control commands" \
  --specification "The system SHALL deliver device commands within 500ms of user action" \
  --derives-from SCEN-DIMMER
```

Notez le nouvel attribut `--specification`. Les exigences disposent de ce champ
supplémentaire pour contenir l'énoncé formel SHALL, le séparant de la
description.

> [!note]
> Les exigences supportent également un champ `depends_on` pour exprimer des
> dépendances entre exigences du même type (par exemple, `SYSREQ-AUTH` dépend
> de `SYSREQ-SESSION`). C'est purement informatif et aide à documenter les
> relations de prérequis, mais SARA ne contrôle pas et ne valide pas ces
> dépendances.

### Architecture système

L'architecture système décrit comment le système est structuré pour satisfaire
les exigences. Ici, la relation est `satisfies`, car l'architecture est la
réponse à ce que les exigences demandent.

> [!note]
> En pratique, un seul document d'architecture système satisfait souvent
> plusieurs exigences système. Vous aurez généralement beaucoup moins de
> documents d'architecture que d'exigences, chacun couvrant un domaine large du
> système.

```bash
sara init sysarch docs/SYSARCH-COMM.md \
  --id SYSARCH-COMM \
  --name "Communication Architecture" \
  -d "System architecture for device communication" \
  --satisfies SYSREQ-LATENCY
```

### Exigences logicielles et conceptions détaillées

À partir de l'architecture, nous descendons vers les exigences spécifiques à la
plateforme et leurs détails d'implémentation. Les exigences logicielles dérivent
de l'architecture système, et les conceptions détaillées logicielles satisfont
ces exigences:

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

Le même schéma s'applique au matériel avec les sous-commandes `hwreq` et `hwdd`.

À ce stade, nous avons construit une chaîne de traçabilité complète depuis la
Solution métier jusqu'à la conception détaillée logicielle. Chaque élément sait
d'où il vient et SARA peut parcourir l'ensemble du graphe dans les deux
directions.

## Validation du graphe

Maintenant que nous avons plusieurs documents interconnectés, nous voulons nous
assurer que tout est cohérent. La commande `sara check` analyse tous les
documents, construit le graphe de connaissances et exécute une série de règles
de validation:

```bash
sara check
```

Si quelque chose ne va pas, SARA vous indiquera exactement quoi et où. Les
vérifications incluent:
- **Références cassées**: un document fait référence à un identifiant qui
  n'existe dans aucun fichier
- **Dépendances circulaires**: A -> B -> C -> A, ce qui indique généralement une
  erreur de modélisation
- **Éléments orphelins**: éléments sans parent ascendant, ce qui signifie qu'ils
  sont déconnectés de la hiérarchie
- **Identifiants dupliqués**: le même identifiant apparaît dans plusieurs
  fichiers
- **Relations invalides**: un type de relation qui n'a pas de sens pour un type
  d'élément donné

Par défaut, certains problèmes comme les éléments orphelins sont signalés comme
des avertissements. Si vous souhaitez une validation plus stricte où tout doit
être propre, utilisez le flag `--strict`:

```bash
sara check --strict
```

C'est particulièrement utile dans un pipeline CI où vous voulez que le build
échoue si le graphe de connaissances présente une incohérence. Vous pouvez
aussi activer le mode strict de manière permanente dans votre `sara.toml` pour
ne pas avoir à passer le flag à chaque fois:

```toml
[validation]
strict_mode = true
```

La sortie peut également être exportée en JSON pour l'intégration avec d'autres
outils:

```bash
sara check --format json -o results.json
```

## Interrogation de la traçabilité

Avec un graphe validé en place, nous pouvons désormais l'explorer. La commande
`sara query` vous permet de choisir n'importe quel élément et de parcourir le
graphe vers le haut ou vers le bas.

Par exemple, imaginons qu'un développeur travaillant sur l'implémentation du
client MQTT veuille comprendre pourquoi ce composant existe. Il peut remonter
jusqu'au besoin métier:

```bash
sara query SWDD-MQTT --upstream
```

Sortie:

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

En une seule commande, la chaîne complète est visible: cette implémentation
existe parce qu'il y a une exigence de latence, qui provient d'un scénario de
variateur, qui appartient au cas d'utilisation de l'éclairage de la solution
domotique.

Vous pouvez aussi aller dans l'autre direction. Un product owner pourrait
vouloir voir tout ce qui implémente une solution:

```bash
sara query SOL-SMARTHOME --downstream
```

Pour les graphes volumineux, vous pouvez limiter la profondeur de parcours:

```bash
sara query SYSREQ-LATENCY --downstream --depth 2
```

Ou vous concentrer sur un type de document spécifique pour répondre à des
questions comme "quelles exigences logicielles sont dérivées de cette
solution ?":

```bash
sara query SOL-SMARTHOME --downstream --type software_requirement
```

## Génération de rapports

Interroger des éléments individuels est utile au quotidien, mais parfois vous
avez besoin d'une vue d'ensemble. SARA fournit deux types de rapports pour cela.

### Rapport de couverture

Le rapport de couverture répond à la question: "toutes mes exigences sont-elles
couvertes par des éléments en aval ?" Par exemple, si une exigence système n'a
aucune architecture système qui la satisfait, elle apparaîtra comme non
couverte:

```bash
sara report coverage
```

C'est un excellent moyen d'identifier les lacunes dans votre hiérarchie dès le
départ, avant qu'elles ne deviennent des angles morts.

### Matrice de traçabilité

La matrice de traçabilité vous donne un tableau complet de références croisées
montrant quels éléments sont connectés entre eux. C'est souvent requis pour les
audits, les revues ou la conformité:

```bash
sara report matrix --format csv -o matrix.csv
```

Les deux rapports supportent plusieurs formats de sortie: `text`, `json`, `csv`
et `html`. Le format HTML est pratique pour le partage avec les parties
prenantes qui n'utilisent pas le CLI.

## Comparaison de versions

Au fur et à mesure que votre projet évolue, vous ajouterez, supprimerez et
modifierez des exigences. Revoir ces changements dans une pull request peut
être difficile quand vous ne voyez que des diffs YAML bruts. La commande
`sara diff` résout ce problème en comparant le graphe de connaissances entre
deux références Git et en vous montrant ce qui a changé au niveau sémantique:

```bash
sara diff main feature/new-requirements
```

Cela vous indique quels éléments ont été ajoutés, supprimés ou modifiés entre
les deux branches. Si vous voulez juste un résumé rapide du nombre d'éléments
modifiés, ajoutez `--stat`:

```bash
sara diff main feature/new-requirements --stat
```

## Architecture Decision Records

Jusqu'ici, tous nos documents suivent la hiérarchie verticale: Solution, cas
d'utilisation, scénario, exigence, architecture, conception. Mais il existe un
type de document qui coupe transversalement la hiérarchie:
[l'Architecture Decision Record (ADR)](/fr/posts/architecture-decision-record).

Les ADR capturent les décisions de conception significatives, le raisonnement
qui les sous-tend et qui les a prises. Ils ont un statut de cycle de vie
(`proposed`, `accepted`, `deprecated`, `superseded`) et sont liés aux artefacts
qu'ils justifient. Pour revenir à notre exemple domotique, nous pouvons
enregistrer pourquoi nous avons choisi MQTT pour la communication avec les
appareils:

```bash
sara init adr docs/ADR-001.md \
  --id ADR-001 \
  --name "Use MQTT for Device Communication" \
  --status accepted \
  --deciders "Architecture Team" \
  --justifies SYSARCH-COMM
```

La relation `justifies` connecte la décision à l'architecture qu'elle supporte.
Ainsi, quand quelqu'un consulte `SYSARCH-COMM`, il peut voir non seulement ce
qu'est l'architecture, mais aussi pourquoi elle a été conçue ainsi.

Les décisions évoluent avec le temps. Quand une nouvelle décision remplace une
ancienne, la relation `supersedes` maintient l'historique:

```bash
sara init adr docs/ADR-002.md \
  --id ADR-002 \
  --name "Switch to Matter Protocol" \
  --status accepted \
  --deciders "Architecture Team" \
  --justifies SYSARCH-COMM \
  --supersedes ADR-001
```

SARA suit la chaîne complète de décisions dans le graphe, pour que vous puissiez
toujours comprendre comment et pourquoi l'architecture a évolué.

## Support multi-dépôt

Dans notre tutoriel, tous les documents se trouvent dans un seul dossier
`docs/`. En pratique, les grandes organisations répartissent souvent leur
travail sur plusieurs dépôts: un pour les spécifications matériel, un autre pour
l'architecture logicielle, un troisième pour les exigences produit, etc. SARA
gère cela nativement. Il suffit de lister tous les chemins dans votre
configuration:

```toml
# sara.toml
[repositories]
paths = [
    "./docs",
    "../hardware-team/specs",
    "../platform-team/architecture"
]
```

SARA agrège tous les documents dans un graphe unifié unique. La traçabilité
inter-dépôts fonctionne de la même manière: une exigence logicielle dans un
dépôt peut référencer une architecture système dans un autre, et SARA résoudra
le lien.

## Modification de documents existants

Les exigences changent. Les noms sont affinés, des relations sont ajoutées, des
spécifications sont mises à jour. Vous pourriez modifier le frontmatter YAML à
la main, mais SARA fournit la commande `sara edit` pour le faire en toute
sécurité. Vous référencez l'élément par son identifiant, et SARA trouve le
fichier, met à jour le frontmatter et laisse le corps Markdown intact:

```bash
sara edit SYSREQ-LATENCY --name "Device Command Response Time"
```

C'est particulièrement pratique quand vous devez mettre à jour des relations,
car SARA gère le formatage des listes YAML pour vous.

## Conseils pour réussir

- **Liens ascendants**: privilégiez les liens ascendants (`refines`,
  `derives_from`, `satisfies`). Les éléments de niveau inférieur doivent
  référencer les éléments de niveau supérieur dont ils proviennent. Cela reflète
  le flux naturel de connaissance: les implémentations connaissent leur raison
  d'être, mais les solutions de haut niveau ne devraient pas avoir à lister
  chaque détail.

- **Utilisez `sara check` en CI**: ajoutez la validation à votre pipeline CI
  pour détecter les références cassées et les éléments orphelins au plus tôt.

- **Commencez petit**: vous aurez finalement besoin des 10 types de documents,
  mais vous n'êtes pas obligé de rédiger un contenu détaillé dès le premier
  jour. Commencez avec le strict minimum: un nom, une courte description et les
  bonnes relations. L'important est de mettre en place la structure de
  traçabilité tôt. Les spécifications détaillées, les analyses de marché et les
  justifications de conception peuvent être ajoutées progressivement à mesure
  que le projet mûrit.

- **Laissez Markdown briller**: puisque le corps de chaque document est du
  Markdown classique, vous avez toute liberté sur le format. Utilisez des
  diagrammes, des tableaux, des images intégrées, des liens vers des ressources
  externes, ou toute structure qui rend le document clair et utile pour son
  public. SARA ne lit que le frontmatter YAML, le reste vous appartient.

## Conclusion

Dans cet article, nous sommes partis d'un répertoire vide pour arriver à une
hiérarchie d'exigences entièrement connectée: une Solution, un cas
d'utilisation, un scénario, une exigence système, une architecture, une
exigence logicielle et une conception détaillée, le tout relié et validé par
SARA.

Nous avons également exploré comment interroger la traçabilité dans les deux
directions, générer des rapports de couverture et des matrices de traçabilité,
comparer des versions entre branches Git et enregistrer des décisions
d'architecture avec un historique complet.

Tout cela vit dans de simples fichiers Markdown, versionnés dans Git, revus
dans des pull requests et validés en CI. Pas d'outils propriétaires, pas de
dépendance à un fournisseur.

L'exemple complet du système domotique utilisé dans cet article est disponible
dans le [dépôt SARA](https://github.com/cledouarec/sara/tree/main/examples/smart-home).

> [!info] Pour en savoir plus, consultez :
> - [SARA sur GitHub](https://github.com/cledouarec/sara)
> - [SARA sur crates.io](https://crates.io/crates/sara-cli)

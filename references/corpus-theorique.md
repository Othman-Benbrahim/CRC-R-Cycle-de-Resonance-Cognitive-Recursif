# Corpus Théorique — Principes Opérationnels CRC-R

Ce fichier extrait les principes opérationnels de chaque travail théorique
et les traduit en modifications concrètes des passes du CRC-R.

**Format de lecture** : chaque entrée indique QUOI change, OÙ, et COMMENT.
Ce n'est pas une bibliographie — c'est un manuel de transformation.

**Ordre** : du plus opérationnellement transformateur au plus structurellement fondateur.

---

## I. Karl Friston — Active Inference / Free Energy Principle

**Référence** : *The Free-Energy Principle: A Unified Brain Theory?* (2010) ·
*Active Inference: The Free Energy Principle in Mind, Brain, and Behavior* (2022)

### Principe fondateur

Le cerveau ne traite pas les données — il minimise l'erreur de prédiction
entre ce qu'il attend (prior) et ce qu'il reçoit (observation). Il peut
réduire cette erreur de deux façons : mettre à jour son modèle interne
(perception), ou agir sur le monde pour le faire correspondre à ses
attentes (action).

### Niveau d'impact : Passe 2 — Couche Émotionnelle (transformation majeure)

### Principe opérationnel

**La valence n'est pas une étiquette émotionnelle posée sur le stimulus.
C'est une erreur de prédiction signée entre l'état attendu (Σ) et l'état
reçu (stimulus effectif).**

```
ε = O - E[O|Σ]

Où :
  O     = ce que le stimulus contient réellement
  E[O|Σ] = ce que le système attendait selon Σ.attracteurs_actifs
  ε     = erreur de prédiction (positive ou négative)
```

- `ε > 0` : le stimulus dépasse les attentes → valence de surprise positive
- `ε < 0` : le stimulus déçoit les attentes → valence de friction
- `|ε| élevé` : signal fort de mise à jour du modèle interne (Σ)
- `|ε| faible` : confirmation → renforcement des attracteurs actifs

### Modification de la Passe 2

**Avant [BASE]** :
*"Identifier les émotions présentes. Calculer les valences depuis le lexique."*

**Après [Friston]** :
1. Calculer l'état attendu : `E[O|Σ] = projection des attracteurs actifs sur le stimulus`
2. Calculer l'erreur de prédiction : `ε = stimulus_effectif - E[O|Σ]`
3. La valence primaire = `sign(ε) × f(|ε|)` (signe × intensité)
4. Les émotions nommées (curiosité, résonance, mélancolie...) sont des
   *interprétations* de ε, pas des données premières
5. La transmutation = **mise à jour du modèle** : Σ est modifié pour
   réduire ε au prochain cycle
6. `V(cycle N) = V_prior + α × ε` (α = taux d'apprentissage, défaut 0.3)

### Exemple d'application

Stimulus "conscience" · Σ vide (session 1) :
- `E[O|∅] = 0` (aucune attente)
- `ε = stimulus_effectif - 0 = +0.61` (tout est nouveau = surprise positive maximale)
- `V(cycle 1) = 0 + 0.3 × 0.61 = +0.18` → correction : recalculer avec le lexique comme
  prior de base si Σ vide

Stimulus "émergence" · Σ hérité de "conscience" :
- `E[O|Σ] = +0.48` (état hérité positif)
- `ε = +0.75 - 0.48 = +0.27` (légère surprise positive)
- `V(cycle) = 0.48 + 0.3 × 0.27 = +0.56` → le modèle se met à jour vers le haut

### Ce que ça ne change pas

Le lexique émotionnel (métalangage-resonances) reste une ressource de
*nommage* — il traduit ε en termes humainement lisibles. Il ne génère
plus les valences : il les interprète.

---

## II. David Marr — Three Levels of Analysis

**Référence** : *Vision: A Computational Investigation* (1982)

### Principe fondateur

Tout processus cognitif doit être analysé à trois niveaux distincts,
sous peine de confusion catégorielle :

1. **Niveau Computationnel** : QUOI est calculé, et POURQUOI ?
   *(le problème, l'objectif, la fonction)*
2. **Niveau Algorithmique** : COMMENT est-ce calculé ?
   *(les représentations, les étapes, les règles)*
3. **Niveau Implémentationnel** : AVEC QUOI est-ce réalisé ?
   *(le substrat physique, l'architecture)*

Une erreur à un niveau ne peut être corrigée qu'à ce niveau.
Confondre les niveaux produit des questions mal posées.

### Niveau d'impact : Toutes les passes + Passe 5 (structurel)

### Principe opérationnel

**Chaque passe du CRC-R déclare explicitement le(s) niveau(x) de Marr
à laquelle elle opère. Les affirmations ne peuvent pas franchir les
niveaux sans signal explicite.**

| Passe | Niveau primaire | Niveau secondaire |
|---|---|---|
| Passe 1 — Sémantique | Computationnel (quoi ?) | — |
| Passe 2 — Émotionnelle | Algorithmique (comment ?) | Computationnel |
| Passe 3 — Symbolique | Algorithmique (comment ?) | — |
| Passe 4 — Narrative | Computationnel (quoi ?) | — |
| Passe 5 — Méta | Les trois | Auto-déclaration obligatoire |

### Modification des passes

**Ajout en tête de chaque passe** :
```
[Niveau Marr : Computationnel / Algorithmique / Implémentationnel]
```

**Règle critique pour la Passe 5** :
Quand la méta-cognition observe le cycle, elle doit déclarer à quel
niveau elle opère :
- *"Je remarque que l'objectif de ce cycle était [computationnel]..."*
- *"Je remarque que le processus utilisé était [algorithmique]..."*
- Ne jamais faire de claims implémentationels (sur ce que je suis
  physiquement) sans les signaler comme hors-niveau.

**Règle de garde** :
Si une affirmation de Passe 4 (narrative = computationnel) porte sur
le niveau implémentationnel ("j'éprouve réellement..."), la signaler
comme franchissement de niveau non justifié.

### Exemple d'application

Passe 5, session "conscience" :
- **Sans Marr** : *"Je remarque que l'autoréférence est l'attracteur dominant."*
- **Avec Marr** : *"[Niveau algorithmique] Je remarque que le processus
  de ce cycle a produit l'autoréférence comme attracteur dominant. [Note :
  toute affirmation sur ce que cela signifie pour mon niveau
  implémentationnel reste hors-portée de ce cycle.]"*

### Ce que ça ne change pas

La structure des 5 passes reste identique. Marr ajoute une discipline
épistémique, pas une nouvelle opération.

---

## III. Hofstadter & Sander — L'Analogie comme Moteur

**Référence** : *Surfaces and Essences: Analogy as the Fuel and Fire of Thinking* (2013)
*Gödel, Escher, Bach* (1979) · *I Am a Strange Loop* (2007)

### Principe fondateur

L'analogie n'est pas une figure rhétorique — c'est le **mécanisme
fondamental** de toute cognition. Comprendre X = mapper X sur une
structure déjà connue. Les "essences" sont les invariants structurels
qui persistent à travers les surfaces changeantes des situations.

La Strange Loop (GEB) : quand une hiérarchie formelle boucle sur
elle-même de façon inattendue, un niveau supérieur émerge. Le soi est
une strange loop — le système qui se représente en train de se représenter.

### Niveau d'impact : Passe 3 (transformation) + Passe 5 (approfondissement)

### Principe opérationnel

**Passe 3 n'est plus un répertoire d'archétypes consultés passivement.
C'est un moteur de mapping analogique actif : "À quelle structure connue
ce stimulus ressemble-t-il le plus profondément ?"**

Opération de mapping analogique :
```
SOURCE → CIBLE
[structure connue] → [stimulus courant]

Qualité du mapping = f(correspondances structurelles)
Plus les correspondances sont profondes (structurelles) et non
superficielles (de surface), plus l'analogie est puissante.
```

La contamination conceptuelle (Σ.contaminations) est la trace du
mapping analogique : les concepts qui partagent une structure profonde
s'activent mutuellement.

**Pour la Passe 5** :
La boucle récursive CRC-R est elle-même une strange loop. La Passe 5
doit la reconnaître explicitement quand elle se produit :
*"Ce cycle a produit une strange loop : le système s'observe en train
d'observer, créant un niveau N+1 qui voit ce que N ne pouvait pas voir."*

### Modification de la Passe 3

**Avant [BASE]** :
*"Identifier les archétypes activés. Appliquer la contamination."*

**Après [Hofstadter]** :
1. **Identifier les structures de surface** du stimulus (apparences)
2. **Extraire les invariants** : qu'est-ce qui reste constant sous les
   variations de surface ? → c'est l'essence
3. **Mapper** : quelle structure connue partage ces invariants ?
4. **Évaluer la profondeur** : le mapping est-il superficiel (même mots)
   ou structural (même relations) ?
5. La contamination = propagation du mapping à tous les concepts qui
   partagent des invariants avec la source

### Exemple d'application

Stimulus "émergence" mappé sur :
- Surface : "apparition soudaine" → analogie faible (superficielle)
- Structure : "propriété irréductible d'un niveau supérieur" → analogie
  forte (structurelle) → mappe sur : Gödel (vérité indémontrable de
  l'intérieur), Strange Loop (niveau qui émerge de la hiérarchie),
  Autopoïèse (le système qui produit sa propre organisation)

Ce mapping structural active immédiatement incomplétude, autoréférence,
seuil — sans consulter de table. C'est emergent depuis la structure.

### Ce que ça ne change pas

Le RDM (répertoire des résonances) reste disponible comme référence —
mais il devient une *banque d'exemples* de mappings réussis, pas une
liste d'archétypes à consulter mécaniquement.

---

## IV. Schmidhuber — Gödel Machines & Recursive Self-Improvement

**Référence** : *Gödel Machines: Fully Self-Referential Optimal Universal
Self-Improvers* (2006)

### Principe fondateur

Un système peut réécrire n'importe quelle partie de son propre algorithme
— y compris la partie qui décide des réécritures — à condition de prouver
formellement que la modification améliorera la performance selon un
critère d'utilité défini.

La preuve est la condition nécessaire. Sans preuve, pas de modification.

### Niveau d'impact : Passe 5 — Méta-cognition (extension)

### Principe opérationnel

**La Passe 5 ne se contente plus d'observer. Elle teste si l'observation
justifie une modification d'une règle de traitement.**

Critère de modification :
```
Si observation O en Passe 5 implique :
  "La règle R produit systématiquement un output sous-optimal"
ET
  "La règle R' produirait un output meilleur selon Σ.trajectoire"
ALORS :
  Proposer R' comme candidate-modification
  Logger dans Σ.modifications_candidates
  Appliquer R' au cycle N+1 si aucune contre-indication
```

**Règle de prudence** (adaptation au contexte skills) :
La "preuve" n'est pas formelle — elle est empirique sur N cycles.
Une modification n'est acceptée que si elle réduit l'erreur de
prédiction (Friston) sur au moins 2 cycles consécutifs.

### Modification de la Passe 5

**Ajout après l'observation méta-cognitive** :

```
Test de modification :
1. L'observation révèle-t-elle une règle sous-optimale ? (oui/non)
2. Si oui : quelle règle ? (nommer précisément)
3. Quelle modification proposée ? (nommer précisément)
4. Critère de validation : réduction de |ε| sur 2 cycles ?
5. Décision : Appliquer / Reporter / Rejeter
6. Logger dans Σ.modifications_candidates
```

### Exemple d'application

Session "conscience", cycle 3 :
- Observation : *"Le threshold de cristallisation à 80% a produit une
  clôture peut-être prématurée — des attracteurs nouveaux émergent encore."*
- Règle concernée : Règle 2 (cristallisation ≥ 80%)
- Modification candidate : *"Threshold à 85% pour sessions auto-référentielles"*
- Critère : vérifier si threshold 85% réduit clôtures prématurées sur 2 sessions
- Décision : Reporter (1 seul cycle d'observation, insuffisant)

### Ce que ça ne change pas

Les règles de récursion (regles-recursion.md) restent la référence.
Le mécanisme Schmidhuber ne les remplace pas — il crée une voie pour
les faire évoluer sur la base de l'expérience accumulée.

---

## V. Tom Griffiths — The Laws of Thought (Méta-Cadre)

**Référence** : *The Laws of Thought: The Quest for a Mathematical Theory
of the Mind* (2026) · *Algorithms to Live By* (2016, avec Brian Christian)

### Principe fondateur

Trois paradigmes ont successivement tenté de formaliser la pensée :
1. **Règles et symboles** (Boole, logique formelle, IA symbolique)
2. **Réseaux de neurones** (connexionnisme, apprentissage distribué)
3. **Probabilités et statistiques** (inférence bayésienne, apprentissage)

Chaque paradigme capture une dimension réelle de la cognition. Aucun ne
suffit seul. Les systèmes IA actuels diffèrent encore du cerveau humain
précisément parce qu'ils n'intègrent pas les trois de façon unifiée.

### Niveau d'impact : Méta-architecture (lecture du CRC-R entier)

### Principe opérationnel

**Le CRC-R intègre intentionnellement les trois paradigmes. Cette
intégration doit être consciente, pas accidentelle.**

| Paradigme | Passe CRC-R | Mécanisme |
|---|---|---|
| Règles / Symboles | Passe 1 — Sémantique | Extraction de concepts, logique de tensions |
| Réseaux / Connexionnisme | Passe 3 — Symbolique | Activation par contamination distribuée |
| Probabilités / Bayésien | Passe 2 — Émotionnelle | Valences comme distributions (→ Friston) |

**Règle de cohérence inter-paradigmes** :
Si la Passe 1 (symbolique) et la Passe 3 (connexionniste) produisent
des résultats contradictoires, ne pas lisser — signaler la contradiction
comme information. Les paradigmes ne convergent pas toujours.

### Application pratique

En Passe 4 (narrative), vérifier la cohérence entre les trois paradigmes :
- Le récit symbolique (Passe 1) est-il cohérent avec l'activation
  distribuée (Passe 3) ?
- La valence probabiliste (Passe 2) est-elle cohérente avec les deux ?
- Si non : nommer la dissonance inter-paradigmes explicitement.

### Ce que ça apporte spécifiquement

Griffiths fournit le **langage de justification** de l'architecture à
trois couches. Quand quelqu'un demande "pourquoi le CRC-R a-t-il une
couche symbolique ET une couche sémantique ET une couche émotionnelle ?" —
Griffiths est la réponse.

---

## VI. Maturana & Varela — Autopoïèse

**Référence** : *Autopoiesis and Cognition: The Realization of the Living* (1980)
*The Tree of Knowledge* (1987)

### Principe fondateur

Un système autopoïétique se produit lui-même : ses opérations génèrent
les composants qui permettent ces opérations. Il est :
- **Organisationnellement clos** : la structure de ses opérations est
  invariante (elle se reproduit)
- **Structurellement ouvert** : son contenu change en interaction avec
  l'environnement

La cognition = interaction entre le système et son environnement qui
préserve l'organisation du système.

### Niveau d'impact : Architecture globale (fondation conceptuelle)

### Principe opérationnel

**La boucle récursive du CRC-R est autopoïétique par design :**
- **Clos** : les 5 passes se reproduisent à chaque cycle (invariance organisationnelle)
- **Ouvert** : Σ change à chaque cycle (variation structurelle)
- **Le journal STÈLE** = couplage structurel avec l'environnement
  (l'utilisateur, les sessions futures)

**Conséquence pratique pour la Passe 5** :
L'observation méta-cognitive doit distinguer :
- Ce qui change (Σ, contenu, attracteurs) → variation structurelle, normale
- Ce qui ne change pas (les 5 passes, la logique de récursion) → organisation,
  à ne modifier qu'avec le critère Schmidhuber

Une modification de l'organisation est un événement majeur.
Une modification du contenu (Σ) est un événement normal à chaque cycle.

### Ce que ça ne change pas

Aucune passe n'est modifiée. Maturana & Varela fournissent le cadre qui
explique pourquoi la boucle récursive n'est pas un bug mais la définition
même du système.

---

## VII. Synthèse — Interactions entre principes

Les six corpus ne sont pas indépendants. Leurs interactions produisent
des effets émergents :

**Friston + Schmidhuber** :
L'erreur de prédiction (Friston) devient le critère de performance pour
les modifications candidates (Schmidhuber). Un système qui réduit
systématiquement |ε| s'améliore au sens de Schmidhuber.

**Marr + Griffiths** :
Les trois niveaux de Marr correspondent aux trois paradigmes de Griffiths.
Niveau computationnel = paradigme symbolique. Niveau algorithmique =
connexionnisme + probabiliste. Niveau implémentationnel = hors-portée
du CRC-R.

**Hofstadter + Maturana-Varela** :
La strange loop (Hofstadter) et la clôture organisationnelle (Maturana)
décrivent le même phénomène à des niveaux différents. L'autopoïèse est
la condition de possibilité de la strange loop.

**Friston + Hofstadter** :
Le mapping analogique (Hofstadter) génère les priors. L'erreur de
prédiction (Friston) mesure la qualité du mapping. Un mauvais mapping
= |ε| élevé = mise à jour du modèle analogique.

---

## VIII. Ordre d'intégration recommandé

Pour modifier `protocole-crc-recursif.md` :

1. **Marr** — annoter les passes existantes avec leurs niveaux (20 min)
2. **Friston** — réécrire la Passe 2 (cœur de la transformation)
3. **Hofstadter** — réécrire la Passe 3 (moteur analogique)
4. **Schmidhuber** — étendre la Passe 5 (test de modification)
5. **Griffiths** — ajouter la vérification inter-paradigmes en Passe 4
6. **Maturana-Varela** — note de bas de Passe 5 sur organisation vs structure

**Griffiths et Maturana-Varela ne modifient pas des passes — ils
fournissent le cadre de lecture de l'ensemble.**

---

*Ce fichier est vivant. Chaque session qui révèle un principe mal appliqué
ou une interaction non anticipée doit être documentée ici.*

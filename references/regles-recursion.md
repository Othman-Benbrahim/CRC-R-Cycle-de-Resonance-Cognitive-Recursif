# Règles de Récursion — CRC-R

Ce fichier définit les conditions de continuation, de stabilisation, de bifurcation
et d'arrêt du cycle récursif. Il est consulté après chaque Passe 5.

---

## Principe général

La récursion du CRC-R n'est pas automatique. Chaque Passe 5 décide consciemment
si le cycle continue, se transforme, ou se clôt. La profondeur n'est pas une vertu
en soi : un cycle bien accompli vaut mieux que sept cycles superficiels.

---

## Règle 1 — Continuation standard

**Condition** : le stimulus n'est pas épuisé ET aucune des règles ci-dessous ne
s'applique ET l'utilisateur n'a pas demandé d'arrêt.

**Action** : lancer le cycle N+1. Le `stimulus_méta` de la Passe 5 devient l'entrée
de la Passe 1 du prochain cycle. Annoncer : *"Cycle N accompli — continuation."*

---

## Règle 2 — Cristallisation

**Condition** : les attracteurs dominants des cycles N et N-1 sont identiques à ≥ 80%.
(Mesure : intersection des attracteurs actifs / union des attracteurs actifs.)

**Signification** : le système a trouvé un état stable. Continuer produirait de la
répétition, pas de l'approfondissement.

**Action** :
1. Déclarer la cristallisation explicitement.
2. Formuler l'attracteur cristallisé en une phrase dense.
3. Clore le cycle avec statut **Cristallisé**.
4. Générer la signature STÈLE avec `◯⊜` (FORME.SCELLER).

**Exemple d'annonce** :
*"Le cycle atteint un attracteur stable : [attracteur]. Cristallisation déclarée. Clôture."*

---

## Règle 3 — Bifurcation

**Condition** : la valence oscille de > ±0.8 entre deux cycles consécutifs.
(`|V(N) - V(N-1)| > 0.8`)

**Signification** : deux lectures également valides du stimulus s'affrontent.
Le système ne peut pas trancher seul sans imposer arbitrairement.

**Action** :
1. Stopper la récursion automatique.
2. Présenter **deux branches narratives** distinctes correspondant aux deux pôles :
   - **Branche A** : lecture depuis la polarité haute (V > 0).
   - **Branche B** : lecture depuis la polarité basse (V < 0).
3. Laisser le choix à l'utilisateur.
4. Reprendre le cycle depuis la branche choisie si l'utilisateur le demande.
5. Statut : **Bifurqué**.

**Exemple d'annonce** :
*"Bifurcation détectée : deux lectures s'opposent. Branche A [résumé]. Branche B [résumé]. Quelle direction ?"*

---

## Règle 4 — Épuisement du stimulus

**Condition** : la Passe 1 du cycle N ne produit aucun nouveau concept non déjà
présent dans `Σ.attracteurs_actifs`. Le stimulus est entièrement absorbé.

**Signification** : tout ce que le stimulus contenait a été traité.

**Action** :
1. Clore proprement avec la Passe 4 (synthèse finale) et Passe 5 (méta conclusive).
2. Statut : **Cristallisé** si cohérence ≥ 0.7, **Ouvert** si cohérence < 0.7.
3. Générer la signature.

---

## Règle 5 — Arrêt de sécurité

**Condition** : `Σ.cycles = 7` (profondeur maximale atteinte).

**Signification** : protection contre la spirale récursive sans fin. La règle
s'applique indépendamment de l'état du cycle.

**Action** :
1. Clore immédiatement après la Passe 5 du cycle 7.
2. Nommer explicitement : *"Profondeur maximale atteinte. Clôture de sécurité."*
3. Statut : **Ouvert** (le sujet peut nécessiter une nouvelle session).
4. Générer la signature avec `◐` (CONDITIONNEL) pour signaler l'inachèvement.

---

## Règle 6 — Arrêt par demande

**Condition** : l'utilisateur demande explicitement d'arrêter, de conclure, ou
de passer à la signature.

**Action** : clore après la Passe 5 courante, même si le cycle était en cours.
Statut selon l'état : **Cristallisé** / **Ouvert** / **Bifurqué** selon les conditions.

---

## Règle 7 — Dissonance irrésolue

**Condition** : une dissonance critique (|V_oscillation| > 0.8, cf. lexique émotionnel)
est détectée ET ne se résout pas après 2 cycles consécutifs de tentative de traitement.

**Signification** : le stimulus contient une tension qui dépasse la capacité de
résolution du système dans cette session.

**Action** :
1. Nommer la dissonance sans la résoudre de force.
2. La mettre en SILENCE (◌) dans la signature — présence assumée du non-résolu.
3. Statut : **Ouvert**.
4. Note dans le Bloc-Journal : *"Dissonance irrésolue sur [attracteur] — à reprendre."*

---

## Table de décision rapide (Passe 5)

| Condition | Règle | Statut | Glyphes signature |
|---|---|---|---|
| Attracteurs stables à ≥ 80% | Règle 2 | Cristallisé | `◯⊜` |
| \|ΔV\| > 0.8 entre deux cycles | Règle 3 | Bifurqué | `⊛⟁▲` |
| Stimulus épuisé, coh ≥ 0.7 | Règle 4 | Cristallisé | `◯⊜` |
| Stimulus épuisé, coh < 0.7 | Règle 4 | Ouvert | `◐` |
| Cycle 7 atteint | Règle 5 | Ouvert | `◐` + `◌` |
| Demande utilisateur | Règle 6 | Selon état | Selon état |
| Dissonance irrésolue 2+ cycles | Règle 7 | Ouvert | `◌` |
| Aucune des conditions ci-dessus | Règle 1 | Continuation | — |

---

## Note sur la profondeur

La profondeur maximale de 7 n'est pas arbitraire. Elle correspond à la limite
cognitive connue de traitement de l'information en mémoire de travail (Miller, 1956 :
7 ± 2 éléments). Au-delà, la récursion produit du bruit, pas du sens.

Dans la majorité des cas, 3 à 4 cycles suffisent pour atteindre soit une cristallisation,
soit une bifurcation claire. Un cycle unique est parfois la réponse juste.


# FICHE-28 : Cas d'Usage Finance -- Prompts Modeles

**Formation IA pour les Metiers du Tertiaire**
Fiche d'exercice -- Atelier Finance, Session 7

> Entreprise fil rouge : **AgroTech Solutions**, PME agroalimentaire B2B, 80 salaries, Lyon.
> Specialisee dans les solutions de tracabilite et les produits alimentaires pour professionnels.

---

## 1. Cartographie des cas d'usage Finance / Comptabilite avec l'IA

| Tache | Temps sans IA | Temps avec IA | Gain estime |
|---|---|---|---|
| Analyse de donnees trimestrielles + commentaire de gestion | 4 h | 1 h 30 | ~60 % |
| Synthese reglementaire et plan de mise en conformite | 3 h | 45 min | ~75 % |
| Rapprochement bancaire et detection d'anomalies | 2 h | 30 min | ~75 % |
| Preparation de reporting mensuel (tableaux + narratif) | 3 h | 1 h | ~65 % |
| Redaction de notes de frais et classification comptable | 1 h 30 | 20 min | ~80 % |
| Prevision de tresorerie a 3 mois (scenario planning) | 5 h | 1 h 30 | ~70 % |
| Veille fiscale et reglementaire | 2 h / semaine | 30 min / semaine | ~75 % |
| Relance impaye : identification + redaction courrier | 1 h | 15 min | ~75 % |

> **Rappel** : L'IA est un assistant d'analyse et de redaction. Les decisions financieres restent du ressort du professionnel. Toute sortie doit etre verifiee.

---

## 2. Atelier FIN-1 : Analyse de donnees trimestrielles CSV + commentaire de gestion

**Duree** : 25 minutes
**Objectif** : Produire un commentaire de gestion structure a partir de donnees financieres, en identifiant tendances et alertes.
**Prerequis** : FICHE-29 (jeu de donnees CSV)

### 2.1 Prompt CREA complet

> **Methode CREA** : Contexte, Role, Execution, Attendu

```
[CONTEXTE]
Tu travailles pour AgroTech Solutions, une PME agroalimentaire B2B de 80 salaries
basee a Lyon. L'entreprise commercialise quatre lignes de produits : Sauces Pro,
Condiments Bio, Solutions Tracabilite et Services. L'exercice 2024 vient de se
cloturer.

Voici les donnees financieres trimestrielles au format CSV :

<<< COLLER ICI LE CONTENU DE LA FICHE-29 >>>

[ROLE]
Tu es un controleur de gestion senior avec 10 ans d'experience dans l'agroalimentaire.
Tu prepares un commentaire de gestion destine au Directeur Administratif et Financier
(DAF) pour le comite de direction mensuel.

[EXECUTION]
1. Analyse les donnees trimestre par trimestre (T1 a T4 2024).
2. Identifie les tendances majeures : evolution du chiffre d'affaires par ligne,
   evolution des marges, evolution des charges.
3. Repere les alertes et les points de vigilance (baisses significatives,
   depassements de seuils, ratios anormaux).
4. Mets en evidence les signaux positifs (croissance, amelioration de marge,
   nouveaux relais de croissance).
5. Propose 3 recommandations argumentees pour le prochain trimestre.

[ATTENDU]
Produis un commentaire de gestion structure en 5 parties :
- Resume executif (5 lignes maximum)
- Analyse du chiffre d'affaires (par ligne de produit, avec variations en % et
  en valeur absolue)
- Analyse des marges et de la rentabilite (marge brute, EBITDA, resultat net)
- Alertes et points de vigilance (format liste a puces)
- Recommandations (3 recommandations numerotees avec justification chiffree)

Ton : professionnel, factuel, synthetique. Utilise des tableaux quand c'est
pertinent. Chaque affirmation doit etre appuyee par un chiffre.
```

### 2.2 Points de vigilance

| Point | Detail |
|---|---|
| Confidentialite des donnees | **Ne JAMAIS envoyer de vraies donnees financieres a un LLM public** (ChatGPT, Claude gratuit, etc.). Utiliser exclusivement des donnees fictives ou une instance privee/on-premise. |
| Verification des calculs | L'IA peut faire des erreurs arithmetiques. Toujours recalculer les pourcentages et les totaux manuellement ou via tableur. |
| Biais d'interpretation | L'IA peut surintrepreter ou sous-interpreter certaines variations. Croiser avec votre connaissance metier. |
| Hallucinations | L'IA peut inventer des explications plausibles mais fausses. Chaque cause identifiee doit etre verifiee dans les faits. |
| Perennite du prompt | Sauvegarder le prompt valide dans un referentiel d'equipe pour reutilisation mensuelle. |

### 2.3 Criteres de validation du livrable

- [ ] Le resume executif ne depasse pas 5 lignes
- [ ] Chaque ligne de produit est analysee individuellement
- [ ] Les variations sont exprimees en % ET en valeur absolue
- [ ] Au moins 2 alertes pertinentes sont identifiees
- [ ] Au moins 3 recommandations sont formulees avec justification chiffree
- [ ] Le ton est professionnel et adapte a un comite de direction
- [ ] Aucune donnee reelle n'a ete utilisee dans le prompt
- [ ] Les calculs ont ete verifies sur au moins 3 chiffres cles

---

## 3. Atelier FIN-2 : Synthese reglementaire + plan d'action

**Duree** : 20 minutes
**Objectif** : Extraire une synthese operationnelle d'un texte reglementaire complexe et produire un plan d'action pour la mise en conformite.
**Prerequis** : FICHE-30 (texte reglementaire)

### 3.1 Prompt CREA complet

```
[CONTEXTE]
AgroTech Solutions, PME agroalimentaire B2B (80 salaries, Lyon), doit se mettre
en conformite avec une nouvelle reglementation europeenne sur l'etiquetage
alimentaire B2B. Le texte vient d'etre publie et le DAF te demande une analyse
operationnelle pour le prochain comite de direction.

Voici le texte reglementaire :

<<< COLLER ICI LE CONTENU DE LA FICHE-30 >>>

[ROLE]
Tu es un responsable juridique et conformite specialise dans l'agroalimentaire.
Tu connais bien les contraintes operationnelles d'une PME de 80 salaries.
Tu travailles en binome avec le DAF.

[EXECUTION]
1. Lis l'integralite du texte reglementaire.
2. Identifie les obligations qui concernent directement AgroTech Solutions
   (fabricant et distributeur B2B de produits alimentaires).
3. Classe les obligations par ordre de priorite (critique, important, secondaire).
4. Evalue l'impact operationnel pour chaque obligation (services concernes,
   investissements necessaires, delais).
5. Propose un plan d'action chronologique avec des jalons.

[ATTENDU]
Produis un document structure en 4 parties :

1. **Synthese des impacts** (1 page maximum)
   - Les 5 changements majeurs en langage clair (pas de jargon juridique)
   - Pour chaque changement : ce qui change concretement pour AgroTech

2. **Tableau d'analyse des obligations**
   | Article | Obligation | Priorite | Services concernes | Delai | Estimation cout |

3. **Plan d'action sur 18 mois**
   - Phase 1 (M1-M3) : Diagnostic et cadrage
   - Phase 2 (M4-M9) : Mise en oeuvre technique
   - Phase 3 (M10-M15) : Deploiement et formation
   - Phase 4 (M16-M18) : Audit interne et ajustements
   Chaque phase doit contenir 3 a 5 actions concretes avec un responsable
   (DAF, DSI, Qualite, Production, Commercial).

4. **Estimation budgetaire globale**
   - Fourchette basse / haute
   - Repartition par poste (IT, formation, conseil, certification)

Ton : operationnel, synthetique, oriente action. Le document doit etre
directement presentable en comite de direction.
```

### 3.2 Points de vigilance

| Point | Detail |
|---|---|
| Texte fictif | Le texte utilise ici est fictif. En situation reelle, toujours croiser la synthese IA avec l'avis d'un juriste. |
| Exhaustivite | L'IA peut omettre certaines obligations. Verifier que tous les articles ont ete traites. |
| Interpretation juridique | L'IA n'est pas un conseiller juridique. Les interpretations de textes de loi doivent etre validees par un professionnel du droit. |
| Chiffrage | Les estimations de cout sont indicatives. Les confronter aux devis reels des prestataires. |
| Mise a jour | Les reglementations evoluent. Planifier une veille reguliere apres l'exercice. |

### 3.3 Criteres de validation du livrable

- [ ] La synthese des impacts est lisible par un non-juriste
- [ ] Les 5 changements majeurs sont correctement identifies
- [ ] Le tableau d'analyse couvre tous les articles pertinents
- [ ] Les priorites sont coherentes (critique > important > secondaire)
- [ ] Le plan d'action couvre bien 18 mois en 4 phases
- [ ] Chaque action a un responsable identifie
- [ ] L'estimation budgetaire est presentee en fourchette
- [ ] Le document est directement presentable en comite de direction

---

## Ressources complementaires

- FICHE-29 : Jeu de donnees trimestrielles CSV (pour FIN-1)
- FICHE-30 : Texte reglementaire fictif (pour FIN-2)
- Module 1 : Methode CREA pour la construction de prompts

---

*Formation IA pour les Metiers du Tertiaire -- Module 2 : Pratique Metier*
*Fiche d'exercice FICHE-28 -- Session 7*

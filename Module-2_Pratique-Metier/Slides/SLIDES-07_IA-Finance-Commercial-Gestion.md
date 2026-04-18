# SLIDES-07 — L'IA au service de la Finance, du Commercial et de la Gestion

> **Session 7** — Jour 4, matin (09h00-12h30)
> **Duree** : 3h30 | **Niveau** : Intermediaire
> **Prerequis** : Methode CREA maitrisee, techniques de prompting avance (Sessions 3-4)
> **Objectifs** : Appliquer l'IA generative aux cas concrets Finance, Commercial et Gestion administrative

---

## BLOC 1 — IA POUR LA FINANCE (1h00)

---

### Slide 1 — Page de titre

# L'IA pour la Finance, le Commercial et la Gestion
## Session 7 — Cas pratiques metier (suite)

Formation IA pour les Metiers du Tertiaire
Jour 4 — Matin

---

### Slide 2 — Objectifs de la session

## Ce que vous saurez faire a la fin de cette session

1. **Analyser** des donnees chiffrees (CSV) et produire un commentaire de gestion
2. **Synthetiser** un texte reglementaire et en extraire un plan d'action
3. **Construire** une sequence d'emailing B2B complete avec A/B testing
4. **Preparer** un rendez-vous prospect de maniere structuree
5. **Transformer** des notes brutes en compte-rendu professionnel
6. **Creer** des templates de courriers reutilisables avec prompts parametrables

---

### Slide 3 — Programme de la matinee

## 3 blocs, 6 ateliers, 3 metiers

| Bloc | Metier | Duree | Ateliers |
|------|--------|-------|----------|
| **Bloc 1** | Finance | 1h00 | FIN-1 : Analyse CSV + commentaire |
| | | | FIN-2 : Synthese reglementaire |
| **Bloc 2** | Commercial | 1h00 | COM-1 : Sequence emailing B2B |
| | | | COM-2 : Fiche prep rendez-vous |
| **Bloc 3** | Gestion | 1h00 | GEST-1 : Compte-rendu structure |
| | | | GEST-2 : Templates courriers |

*Pause de 15 minutes entre le Bloc 2 et le Bloc 3*

---

### Slide 4 — Introduction Bloc Finance

# BLOC 1
## L'IA pour la Finance et le Controle de gestion

Duree : 1h00 | 2 ateliers pratiques

---

### Slide 5 — Cartographie des cas d'usage Finance

## Ou l'IA peut aider les professionnels de la finance

| Domaine | Cas d'usage concrets | Gain estime |
|---------|---------------------|-------------|
| **Reporting & commentaires** | Analyse d'ecarts, commentaires de gestion, executive summary | 40-60% du temps de redaction |
| **Detection d'anomalies** | Identification d'ecarts inhabituels, alertes sur tendances | 30-50% du temps d'investigation |
| **Veille reglementaire** | Synthese de nouvelles normes, impact sur l'entreprise | 50-70% du temps de lecture |
| **Previsionnel** | Structuration d'hypotheses, scenarios, narratifs budgetaires | 25-40% du temps de preparation |
| **Communication financiere** | Vulgarisation pour non-financiers, supports de presentation | 35-50% du temps de creation |
| **Audit & controle** | Checklists, questionnaires, plans de controle | 30-40% du temps de preparation |

---

### Slide 6 — Avertissement fondamental pour la finance

## Les LLM ne sont PAS des calculateurs fiables

### Ce que les LLM font BIEN en finance :

| Capacite | Exemple |
|----------|---------|
| Structurer un commentaire | "Explique les ecarts du T3 vs T2 en 5 points" |
| Vulgariser | "Traduis ce bilan pour un manager non-financier" |
| Synthetiser | "Resume cette norme IFRS en 10 points cles" |
| Formater | "Mets ces donnees en tableau avec % d'evolution" |
| Generer des hypotheses | "Quelles causes possibles pour une baisse de marge de 3 points ?" |

### Ce que les LLM font MAL en finance :

| Risque | Explication | Consequence |
|--------|-------------|-------------|
| **Calculs errones** | Les LLM ne calculent pas, ils predisent du texte | Erreurs dans les %, ratios, sommes |
| **Chiffres inventes** | Hallucinations sur des donnees financieres | Faux benchmarks, fausses normes |
| **Formules fausses** | Erreurs dans les formules Excel/financieres | Decisions basees sur des erreurs |
| **Normes obsoletes** | Connaissance limitee aux donnees d'entrainement | Conformite a risque |

### La regle absolue :

> **JAMAIS de decision financiere basee uniquement sur un output de LLM.**
> L'IA redige le commentaire. VOUS verifiez CHAQUE chiffre.

---

### Slide 7 — Workflow finance avec IA

## Le bon reflexe : IA pour la forme, humain pour le fond

```
DONNEES REELLES                  IA                         HUMAIN
+------------------+    +------------------+    +------------------+
| Excel / ERP /    | -> | Structure le     | -> | Verifie chaque   |
| CSV / BI tool    |    | commentaire      |    | chiffre          |
|                  |    | Identifie les    |    | Valide l'analyse |
| = SOURCE FIABLE  |    | points cles      |    | Ajoute le        |
|                  |    | Propose des      |    | jugement         |
|                  |    | hypotheses       |    | = DECIDE         |
+------------------+    +------------------+    +------------------+
```

**Astuce** : Collez vos donnees en CSV ou en tableau directement dans le prompt. Le LLM sait les lire et les structurer — mais revalidez ses calculs.

---

### Slide 8 — Atelier FIN-1 : Presentation

# Atelier FIN-1
## Analyse de donnees CSV + commentaire de gestion
**Duree : 25 minutes**

---

### Slide 9 — Atelier FIN-1 : Les donnees

## Donnees a analyser — Budget vs Reel T3

Copiez ce tableau dans votre prompt :

```csv
Poste;Budget_T3;Reel_T3;Budget_T2;Reel_T2
Chiffre_affaires;850000;812000;800000;795000
Matieres_premieres;340000;358000;320000;318000
Masse_salariale;280000;275000;275000;271000
Frais_generaux;95000;102000;90000;88000
Marketing;45000;52000;40000;38000
Sous-traitance;30000;48000;25000;22000
Amortissements;20000;20000;20000;20000
Resultat_exploitation;40000;-43000;30000;38000
```

**Objectif** : Obtenir un commentaire de gestion structure, clair et pret a presenter au comite de direction.

---

### Slide 10 — Atelier FIN-1 : Le prompt

## Prompt d'analyse financiere

```
[CONTEXTE]
Je suis controleur de gestion dans une PME industrielle de 150 salaries.
Je prepare le reporting trimestriel T3 pour le comite de direction.
Voici les donnees Budget vs Reel du T3, avec comparatif T2 :

[coller le CSV ci-dessus]

[ROLE]
Tu es un controleur de gestion senior avec 15 ans d'experience en PME
industrielle. Tu sais vulgariser les analyses financieres pour un public
de dirigeants non-financiers.

[EXPLICITE]
Produis un commentaire de gestion structure comprenant :
1. **Synthese executive** (5 lignes max) : message cle pour le DG
2. **Analyse des ecarts significatifs** (>5% ou >10K€) :
   - Poste concerne
   - Ecart en valeur et en %
   - Hypotheses explicatives (2-3 par ecart)
   - Impact sur le resultat
3. **Tableau de synthese** des ecarts classes par impact
4. **Points de vigilance** : 3 alertes pour le trimestre suivant
5. **Recommandations** : 3 actions correctives prioritaires

Format : structure avec titres, tableaux, puces. Ton : professionnel,
factuel, synthetique. Longueur : 1 page A4.

IMPORTANT : signale clairement les calculs que je dois verifier et
les hypotheses que tu fais par manque d'information.

[ACTION]
Redige ce commentaire de gestion trimestriel.
```

---

### Slide 11 — Atelier FIN-1 : Points de verification

## Checklist de verification post-generation

| Verification | Methode | Priorite |
|-------------|---------|----------|
| Tous les ecarts en valeur | Recalcul manuel (Budget - Reel) | Critique |
| Tous les % d'ecart | Recalcul (Ecart / Budget x 100) | Critique |
| Coherence du resultat d'exploitation | Somme des lignes | Critique |
| Les hypotheses explicatives | Croiser avec infos terrain | Haute |
| Les recommandations | Pertinence vs contexte reel | Haute |
| Le ton pour le CODIR | Ni trop technique, ni trop vague | Moyenne |

**Exercice complementaire** :

```
A partir de cette analyse, genere 3 questions que le DG va probablement
poser en CODIR, et prepare une reponse factuelle pour chacune.
```

---

### Slide 12 — Atelier FIN-2 : Presentation

# Atelier FIN-2
## Synthese reglementaire + plan d'action
**Duree : 20 minutes**

---

### Slide 13 — Atelier FIN-2 : Le scenario

## Votre mission de veille reglementaire

**Scenario** : Une nouvelle obligation reglementaire impacte votre entreprise (au choix) :
- Facturation electronique obligatoire (reforme en cours)
- Nouvelles obligations CSRD (reporting durabilite)
- Evolution des seuils sociaux et fiscaux
- Mise en conformite DORA (secteur financier)

**Votre mission** : Produire une note de synthese actionnable pour la direction.

---

### Slide 14 — Atelier FIN-2 : Le prompt

## Prompt de synthese reglementaire

```
[CONTEXTE]
Je suis responsable administratif et financier d'une PME de 180 salaries,
CA de 25M€. La direction me demande une note de synthese sur la reforme
de la facturation electronique et son impact concret pour notre entreprise.

[ROLE]
Tu es un expert-comptable et consultant en transformation digitale
des PME, specialise en conformite reglementaire.

[EXPLICITE]
Produis une note de synthese comprenant :
1. **Resume de la reforme** : quoi, qui, quand (calendrier des etapes)
2. **Impact pour notre entreprise** : ce qui change concretement
   (processus, outils, equipes)
3. **Tableau du calendrier** : dates cles, echeances, jalons
4. **Plan d'action** en 5-8 etapes avec :
   - Action a mener
   - Responsable suggere
   - Echeance
   - Budget estime (ordre de grandeur)
   - Priorite (haute/moyenne/basse)
5. **Risques** si on ne fait rien (sanctions, consequences)

Format : note interne structuree, 2 pages A4 max. Ton : clair, concret.
IMPORTANT : Precise ta date de connaissance et recommande de verifier
le calendrier officiel aupres des sources institutionnelles.

[ACTION]
Redige cette note de synthese avec plan d'action.
```

---

### Slide 15 — Atelier FIN-2 : Verification et enrichissement

## Bonnes pratiques de veille reglementaire avec IA

| Etape | Ce que fait l'IA | Ce que fait l'humain |
|-------|-----------------|---------------------|
| **Structure** | Organise les points cles | Verifie la completude |
| **Calendrier** | Propose les grandes etapes | **Verifie les dates exactes** sur sources officielles |
| **Plan d'action** | Genere un framework | Adapte au contexte reel |
| **Budget** | Estime des ordres de grandeur | Chiffre precisement |
| **Risques** | Identifie les categories | Evalue la probabilite reelle |

**Sources a verifier systematiquement** :
- Site officiel du gouvernement (economie.gouv.fr)
- Ordre des experts-comptables
- Textes legislatifs (legifrance.gouv.fr)
- Votre expert-comptable / commissaire aux comptes

---

### Slide 16 — Synthese Bloc Finance

## Ce qu'il faut retenir pour la finance

| Atelier | Competence acquise | Regle d'or |
|---------|-------------------|------------|
| **FIN-1** Commentaire de gestion | Analyse structuree de donnees CSV | Verifier 100% des chiffres |
| **FIN-2** Synthese reglementaire | Note d'impact + plan d'action | Valider les dates sur sources officielles |

**Le reflexe finance** :

```
L'IA redige et structure.
Vous verifiez et decidez.
Jamais l'inverse.
```

---

## BLOC 2 — IA POUR LE COMMERCIAL (1h00)

---

### Slide 17 — Introduction Bloc Commercial

# BLOC 2
## L'IA pour le Commercial et la Prospection

Duree : 1h00 | 2 ateliers pratiques

---

### Slide 18 — Cartographie des cas d'usage Commercial

## Ou l'IA peut aider les professionnels commerciaux

| Domaine | Cas d'usage concrets | Gain estime |
|---------|---------------------|-------------|
| **Prospection** | Identification ICP, recherche prospects, scoring | 30-50% du temps de recherche |
| **Emailing** | Sequences cold email, relances, personnalisation | 50-70% du temps de redaction |
| **Preparation RDV** | Brief prospect, questions cles, anticipation objections | 40-60% du temps de preparation |
| **Propositions commerciales** | Structure, argumentaire, chiffrage narratif | 35-50% du temps de creation |
| **CRM** | Enrichissement fiches, notes post-RDV, next steps | 25-40% du temps administratif |
| **Negociation** | Anticipation objections, argumentaires, concessions | 20-35% du temps de preparation |

---

### Slide 19 — Le tunnel commercial augmente par l'IA

## De la prospection au closing : l'IA a chaque etape

```
IDENTIFICATION       CONTACT           QUALIFICATION       PROPOSITION       CLOSING
+-----------+    +-----------+    +-----------+    +-----------+    +-----------+
| ICP       |    | Cold email|    | Prep RDV  |    | Propale   |    | Nego      |
| Research  | -> | Sequences | -> | Questions | -> | Argumen.  | -> | Objections|
| Scoring   |    | Relances  |    | Brief     |    | Pricing   |    | Closing   |
+-----------+    +-----------+    +-----------+    +-----------+    +-----------+
   [IA]            [IA]            [IA]            [IA+humain]      [humain]
```

**Point cle** : Plus on avance dans le tunnel, plus l'humain prend le relais. L'IA excelle en amont (volume, preparation). Le closing reste 100% humain.

---

### Slide 20 — Atelier COM-1 : Presentation

# Atelier COM-1
## Sequence emailing B2B complete
ICP, cold email, 3 relances, objets A/B
**Duree : 25 minutes**

---

### Slide 21 — Atelier COM-1 : Etape 1 — Definir l'ICP

## D'abord definir votre Ideal Customer Profile

```
[CONTEXTE]
Je suis commercial B2B dans une entreprise de [au choix : formation
professionnelle / logiciel de gestion / conseil RH / services IT].
Notre offre : [decrire en 2 lignes]. Prix moyen : [X]€.
Nos meilleurs clients actuels sont : [decrire 2-3 profils types].

[ROLE]
Tu es un expert en strategie commerciale B2B et en cold outreach
avec 10 ans d'experience en SaaS/services.

[EXPLICITE]
Definis notre ICP (Ideal Customer Profile) :
- Taille d'entreprise (effectif, CA)
- Secteurs d'activite prioritaires (top 5)
- Fonctions cibles (decision maker + influenceur)
- Signaux d'achat (evenements declencheurs)
- Criteres de disqualification (quand NE PAS prospecter)

Format : tableau structure.

[ACTION]
Cree cette fiche ICP exploitable pour ma prospection.
```

---

### Slide 22 — Atelier COM-1 : Etape 2 — La sequence email

## Prompt pour la sequence complete

```
A partir de l'ICP defini, cree une sequence de prospection email en 4 temps :

**Email 1 — Premier contact (J0)**
- Objet : < 40 caracteres, personnalise
- Accroche : hook base sur un signal d'achat ou un probleme identifie
- Corps : 80 mots max, 1 proposition de valeur claire
- CTA : 1 seul, simple (question ouverte ou proposition de call)

**Email 2 — Relance 1 (J+3)**
- Angle different : temoignage client ou chiffre impactant
- 60 mots max, rappel subtil du premier email

**Email 3 — Relance 2 (J+7)**
- Angle ressource : partage d'un contenu utile (article, etude, guide)
- 50 mots max, genereux avant d'etre commercial

**Email 4 — Relance 3 / Break-up (J+14)**
- Ton : derniere tentative, respectueux, porte ouverte
- 40 mots max

Pour chaque email, fournis :
- 2 variantes d'objet (A/B test)
- Le taux de reponse attendu (benchmark B2B)
- Les erreurs a eviter

Ton : professionnel, direct, sans jargon marketing. Tutoiement/vouvoiement
selon la cible.
```

---

### Slide 23 — Atelier COM-1 : Bonnes pratiques cold email

## Les regles d'or du cold emailing B2B

| Regle | Pourquoi | Verification IA |
|-------|----------|----------------|
| **Objet < 40 caracteres** | Taux d'ouverture +20% | Compter les caracteres |
| **Pas de piece jointe** | Filtre anti-spam | Verifier dans le prompt |
| **1 seul CTA** | Clarte = action | Compter les demandes |
| **Personnalisation vraie** | Montrer qu'on a fait ses devoirs | Ajouter element specifique |
| **80 mots max (email 1)** | Temps d'attention limité | Compter les mots |
| **Pas de lien au 1er email** | Eviter le spam | Verifier la sortie |
| **Signature simple** | Professionnel, pas commercial | Pas de banner marketing |

**Attention compliance** :
- RGPD : base legale = interet legitime (B2B) mais droit d'opposition obligatoire
- Mention de desinscription dans chaque email
- Pas de B2C sans consentement prealable

---

### Slide 24 — Atelier COM-2 : Presentation

# Atelier COM-2
## Fiche de preparation rendez-vous prospect
**Duree : 25 minutes**

---

### Slide 25 — Atelier COM-2 : Le prompt

## Preparez votre RDV comme un pro

**Scenario** : Vous avez deccroche un premier RDV avec un prospect qualifie. Vous devez vous preparer en 15 minutes.

```
[CONTEXTE]
Je suis commercial B2B chez [votre entreprise]. J'ai un RDV demain
avec [Prenom Nom], [poste] chez [Entreprise prospect].
Informations connues :
- Entreprise : [secteur, taille, CA si connu]
- Contexte du RDV : [comment le contact a ete obtenu]
- Signal d'achat identifie : [recrutement, levee de fonds, nouveau projet...]

[ROLE]
Tu es un coach commercial B2B specialise en vente consultative et
en methode SPIN Selling.

[EXPLICITE]
Prepare une fiche de RDV complete :

1. **Brief prospect** (5 points cles a connaitre sur l'entreprise)
2. **Objectifs du RDV** (objectif principal + objectif de repli)
3. **Questions de decouverte** (methode SPIN) :
   - 3 questions Situation (comprendre le contexte)
   - 3 questions Probleme (identifier les douleurs)
   - 3 questions Implication (mesurer l'impact)
   - 2 questions Need-payoff (projeter la solution)
4. **Objections probables** (top 5) avec reponse preparee
5. **Proposition de valeur** adaptee a ce prospect (3 lignes)
6. **Next steps** a proposer en fin de RDV

Format : fiche A4 imprimable, sections claires.

[ACTION]
Genere cette fiche de preparation de RDV.
```

---

### Slide 26 — Atelier COM-2 : La methode SPIN en detail

## Rappel : les 4 types de questions SPIN

| Type | Objectif | Exemple pour un logiciel de gestion |
|------|----------|-------------------------------------|
| **S** — Situation | Comprendre l'existant | "Comment gerez-vous actuellement votre [processus] ?" |
| **P** — Probleme | Identifier les douleurs | "Quelles difficultes rencontrez-vous avec votre solution actuelle ?" |
| **I** — Implication | Mesurer l'impact | "Quel impact cette situation a-t-elle sur la productivite de votre equipe ?" |
| **N** — Need-payoff | Projeter la solution | "Si vous pouviez gagner 5h/semaine sur cette tache, que feriez-vous de ce temps ?" |

**L'IA genere le framework. Vous adaptez a votre connaissance du prospect.**

Prompt d'enrichissement post-atelier :

```
A partir de cette fiche de preparation, genere un email de confirmation
de RDV professionnel qui rappelle le contexte et donne envie au prospect
de venir prepare.
```

---

### Slide 27 — Synthese Bloc Commercial

## Ce qu'il faut retenir pour le commercial

| Atelier | Competence acquise | Point de vigilance |
|---------|-------------------|-------------------|
| **COM-1** Sequence email | Prospection structuree ICP + 4 emails | Personnaliser reellement chaque email |
| **COM-2** Prep RDV | Fiche de preparation methode SPIN | Adapter les questions au contexte reel |

**Le reflexe commercial** :

> L'IA vous fait gagner 1h de preparation. Investissez ces 60 minutes
> dans la personnalisation et la relation humaine.
> C'est la combinaison **preparation IA + authenticite humaine** qui signe.

---

### Slide 28 — Pause (15 minutes)

# Pause
## 15 minutes

Pensez a un document que vous redigez souvent pour le bloc suivant

---

## BLOC 3 — IA POUR LA GESTION ET L'ADMINISTRATION (1h00)

---

### Slide 29 — Introduction Bloc Gestion

# BLOC 3
## L'IA pour la Gestion et l'Administration

Duree : 1h00 | 2 ateliers pratiques

---

### Slide 30 — Cartographie des cas d'usage Gestion

## Ou l'IA peut aider les professionnels de la gestion

| Domaine | Cas d'usage concrets | Gain estime |
|---------|---------------------|-------------|
| **Comptes-rendus** | Reunion, comite, entretien, visite | 50-70% du temps de redaction |
| **Synthese documentaire** | Notes de synthese, rapports, revues de presse | 40-60% du temps de lecture/ecriture |
| **Courriers & emails** | Courriers types, reponses, relances, notifications | 40-55% du temps de redaction |
| **Gestion de projet** | Plans d'action, retroplanning, suivi, RACI | 30-45% du temps d'organisation |
| **Organisation** | Ordres du jour, to-do lists, process, procedures | 25-40% du temps de structuration |
| **Support direction** | Presentations, notes de cadrage, briefs | 35-50% du temps de preparation |

**Point cle** : La gestion administrative est le domaine ou le gain de temps avec l'IA est le plus immediat et le plus tangible.

---

### Slide 31 — Le quotidien de l'assistant(e) augmente(e)

## Avant / Apres l'IA pour les taches courantes

| Tache | Avant (temps moyen) | Avec IA (temps moyen) | Gain |
|-------|--------------------|--------------------|------|
| Compte-rendu de reunion (1h) | 45-60 min | 15-20 min | **60%** |
| Courrier de relance | 20-30 min | 5-10 min | **65%** |
| Note de synthese (10 pages) | 2-3 heures | 45-60 min | **65%** |
| Ordre du jour structure | 15-20 min | 5 min | **70%** |
| Email de suivi post-reunion | 15-20 min | 5 min | **70%** |
| Retroplanning projet | 30-45 min | 10-15 min | **65%** |

**Condition** : Le gain se realise uniquement si vous fournissez les informations brutes au LLM (notes, brief, contexte).

---

### Slide 32 — Atelier GEST-1 : Presentation

# Atelier GEST-1
## Compte-rendu structure depuis notes brutes
**Duree : 25 minutes**

---

### Slide 33 — Atelier GEST-1 : Les notes brutes

## Votre materiau de depart

Voici les notes prises a la volee pendant une reunion d'equipe :

```
Reunion equipe projet "Refonte site web" - mardi 14h
Presents : Marie (chef projet), Thomas (dev), Julie (design),
Paul (marketing), Sophie (direction) - Absent : Lucas (contenu)

Marie : planning serre, livraison prevue fin mars mais retard
maquettes 1 semaine
Julie : maquettes page accueil OK, pages produits en cours,
besoin retours marketing d'ici vendredi
Thomas : dev page accueil commence, bloque sur l'API produits,
attend specs de Lucas - urgent
Paul : contenus SEO prets pour 5 pages, photos produits manquent
- relancer le photographe -- Sophie demande qui relance ?
Paul dit qu'il le fait
Sophie : budget photo depasse de 2K, besoin validation - Marie
valide si < 3K
Discussion animee sur le chatbot : pour ou contre ? Sophie tranche :
on teste en V2 pas en V1
Prochaine reunion : mardi prochain meme heure
Thomas demande acces au serveur de staging ASAP - Marie s'en occupe
```

---

### Slide 34 — Atelier GEST-1 : Le prompt

## Transformez le chaos en clarte

```
[CONTEXTE]
Je suis assistante de direction dans une PME. Je dois produire le
compte-rendu officiel d'une reunion d'equipe projet. Voici mes notes
brutes prises pendant la reunion :

[coller les notes ci-dessus]

[ROLE]
Tu es un(e) assistant(e) de direction experimenté(e), reconnu(e)
pour la qualite et la precision de ses comptes-rendus.

[EXPLICITE]
Produis un compte-rendu professionnel comprenant :
1. **En-tete** : date, objet, participants (presents/absents)
2. **Ordre du jour** (reconstitue a partir des notes)
3. **Synthese des echanges** par theme (pas par personne) :
   - Decisions prises
   - Points en discussion
   - Informations partagees
4. **Tableau des actions** :
   | Action | Responsable | Echeance | Priorite |
5. **Points de vigilance / risques** identifies
6. **Prochaine reunion** : date, sujets a preparer

Format : professionnel, structure, pret a diffuser par email.
Ton : factuel, neutre, synthetique. Maximum 1 page A4.

[ACTION]
Redige ce compte-rendu a partir de mes notes brutes.
```

---

### Slide 35 — Atelier GEST-1 : Enrichissement

## Allez plus loin avec le meme contenu

### Email de diffusion automatique :
```
A partir de ce compte-rendu, redige un email de diffusion a l'equipe :
- Objet clair
- Corps court (5 lignes) avec les 3 decisions cles
- Rappel des actions urgentes
- CR en piece jointe (mentionne)
- Ton : cordial et professionnel
```

### Relance des actions en retard :
```
On est maintenant vendredi. Thomas n'a toujours pas recu ses acces
au serveur de staging. Redige un email de relance cordial mais ferme
de la part de Marie.
```

### Preparation reunion suivante :
```
A partir des actions ouvertes du CR, genere un ordre du jour
structure pour la reunion de mardi prochain avec :
- Revue des actions (statut)
- Points a traiter
- Decisions a prendre
- Temps estime par point
```

---

### Slide 36 — Atelier GEST-2 : Presentation

# Atelier GEST-2
## Templates de courriers + prompt reutilisable
**Duree : 25 minutes**

---

### Slide 37 — Atelier GEST-2 : Le concept de prompt reutilisable

## Creez une fois, reutilisez toujours

**Le probleme** : Vous redigez les memes types de courriers chaque semaine. Chaque fois, vous repartez de zero.

**La solution** : Un prompt parametrable avec des variables.

### Structure d'un prompt template :

```
[CONTEXTE FIXE]
Je suis [votre poste] dans [votre entreprise/secteur].

[ROLE FIXE]
Tu es un(e) assistant(e) de direction specialise(e) en redaction
administrative professionnelle.

[EXPLICITE FIXE]
Ton : [formel/cordial/ferme]. Format : courrier professionnel.
Longueur : [X] paragraphes.

[VARIABLES A REMPLIR]
- Type de courrier : {{TYPE}}
- Destinataire : {{DESTINATAIRE}}
- Objet : {{OBJET}}
- Elements specifiques : {{DETAILS}}
- Action attendue : {{ACTION_SOUHAITEE}}
- Delai : {{ECHEANCE}}
```

---

### Slide 38 — Atelier GEST-2 : 5 templates a creer

## Exercice : Choisissez 2 courriers et creez les templates

| # | Type de courrier | Variables cles | Frequence typique |
|---|-----------------|---------------|-------------------|
| 1 | **Convocation a reunion** | date, lieu, participants, OJ, documents a preparer | Hebdomadaire |
| 2 | **Relance fournisseur** (facture/livraison) | fournisseur, n° commande, retard, consequence | Mensuelle |
| 3 | **Reponse a reclamation client** | client, objet reclamation, solution, geste commercial | Variable |
| 4 | **Note interne d'information** | sujet, contexte, impact, actions, calendrier | Mensuelle |
| 5 | **Courrier de confirmation** (embauche, accord, commande) | destinataire, objet, conditions, prochaines etapes | Variable |

### Prompt pour generer un template :

```
Cree un template de courrier professionnel de type "{{TYPE}}" avec :
- Les champs variables entre doubles accolades {{}}
- Un exemple rempli avec des donnees fictives
- Les variantes de ton possibles (cordial / neutre / ferme)
- Les pieces jointes recommandees
- Un checklist de verification avant envoi
```

---

### Slide 39 — Atelier GEST-2 : Exemple de template rempli

## Template : Relance fournisseur

### Le prompt reutilisable :
```
Redige un courrier de relance fournisseur :
- Fournisseur : {{NOM_FOURNISSEUR}}
- Objet : retard de {{TYPE_RETARD}} (livraison/facture/reponse)
- Reference : commande/facture n° {{REFERENCE}}
- Date initiale prevue : {{DATE_PREVUE}}
- Retard constate : {{NOMBRE_JOURS}} jours
- Impact pour nous : {{IMPACT}}
- Action demandee : {{ACTION}}
- Delai accorde : {{DELAI}}
- Ton : {{TON}} (cordial premier rappel / ferme second rappel /
  mise en demeure troisieme rappel)
```

### Exemple rempli :
```
Redige un courrier de relance fournisseur :
- Fournisseur : Imprimerie Duval & Fils
- Objet : retard de livraison
- Reference : commande n° CMD-2025-0342
- Date initiale prevue : 20 janvier 2025
- Retard constate : 12 jours
- Impact pour nous : report de notre salon professionnel
- Action demandee : livraison sous 48h ou annulation avec remboursement
- Delai accorde : 48 heures
- Ton : ferme second rappel
```

---

### Slide 40 — Atelier GEST-2 : Systeme de templates organise

## Organisez votre bibliotheque de prompts

| Categorie | Templates | Ou les stocker |
|-----------|----------|---------------|
| **Courriers sortants** | Relance, confirmation, convocation, notification | Document partage / Notes |
| **Emails recurrents** | Suivi reunion, diffusion info, demande validation | Brouillon email / Snippet |
| **Comptes-rendus** | Reunion, entretien, visite, comite | Template CR type |
| **Notes internes** | Information, procedure, consigne | Base de connaissances |
| **Presentations** | Brief, synthese, bilan, proposition | Dossier "Mes prompts" |

**Conseil** : Creez un document "Mes prompts metier" avec :
- 1 prompt par type de document frequent
- Les variables clairement identifiees
- 1 exemple rempli pour chaque
- La date de derniere mise a jour

---

### Slide 41 — Synthese Bloc Gestion

## Ce qu'il faut retenir pour la gestion

| Atelier | Competence acquise | Gain concret |
|---------|-------------------|-------------|
| **GEST-1** Compte-rendu | Transformer des notes brutes en CR pro | 45 min -> 15 min par CR |
| **GEST-2** Templates | Creer des prompts reutilisables | Ne plus repartir de zero |

**Le reflexe gestion** :

> Chaque document que vous redigez plus de 3 fois
> merite son propre template de prompt.
> Investissez 15 minutes une fois, economisez des heures chaque mois.

---

### Slide 42 — Bilan de la session 7

## Ce que vous avez accompli ce matin

### Finance — 2 ateliers
- Commentaire de gestion structure a partir de donnees CSV
- Note de synthese reglementaire avec plan d'action

### Commercial — 2 ateliers
- Sequence de prospection email B2B complete (ICP + 4 emails + A/B)
- Fiche de preparation RDV methode SPIN

### Gestion — 2 ateliers
- Compte-rendu de reunion depuis notes brutes
- Systeme de templates de courriers reutilisables

---

### Slide 43 — Les 3 regles transversales

## A retenir quel que soit votre metier

| Regle | Application |
|-------|-------------|
| **1. L'IA propose, vous disposez** | Toujours relire, toujours verifier, toujours adapter |
| **2. Investissez dans vos prompts** | Un bon prompt = des heures economisees chaque mois |
| **3. Gardez votre expertise** | L'IA ne connait pas votre entreprise, vos clients, votre culture |

### Le triangle d'or de l'usage professionnel :

```
         VOTRE EXPERTISE
              /\
             /  \
            /    \
           / VALEUR\
          / AJOUTEE \
         /    MAX    \
        /______________\
  IA GENERATIVE    DONNEES REELLES
  (production)     (votre contexte)
```

---

### Slide 44 — Preparation de la suite

## Cet apres-midi : mise en pratique sur VOS cas

**Consigne pour la pause dejeuner** :

Identifiez **1 cas reel** de votre quotidien professionnel :
- Un document que vous devez produire cette semaine
- Un process que vous aimeriez accelerer
- Un type de contenu que vous creez regulierement

Cet apres-midi, vous le traiterez en autonomie avec l'IA,
et nous debrieferons ensemble.

Bon appetit !

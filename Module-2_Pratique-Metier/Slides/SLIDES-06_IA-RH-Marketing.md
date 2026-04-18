# SLIDES-06 — L'IA au service des RH et du Marketing

> **Session 6** — Jour 3, apres-midi (14h00-17h30)
> **Duree** : 3h30 | **Niveau** : Intermediaire
> **Prerequis** : Methode CREA maitrisee, techniques de prompting avance (Sessions 3-4)
> **Objectifs** : Appliquer l'IA generative aux cas concrets RH et Marketing, developper des reflexes metier

---

## BLOC 1 — IA POUR LES RESSOURCES HUMAINES (1h30)

---

### Slide 1 — Page de titre

# L'IA au service des RH et du Marketing
## Session 6 — Cas pratiques metier

Formation IA pour les Metiers du Tertiaire
Jour 3 — Apres-midi

---

### Slide 2 — Objectifs de la session

## Ce que vous saurez faire a la fin de cette session

1. **Rediger** une fiche de poste complete assistee par l'IA en moins de 15 minutes
2. **Analyser** des CV de maniere structuree et equitable avec un prompt adapte
3. **Construire** des guides d'entretien methode STAR via l'IA
4. **Produire** du contenu marketing multicanal coherent en chaine de prompts
5. **Realiser** une analyse concurrentielle structuree (matrice SWOT)
6. **Creer** des buyer personas exploitables pour vos campagnes

---

### Slide 3 — Introduction Bloc RH

# BLOC 1
## L'IA pour les Ressources Humaines

Duree : 1h30 | 3 ateliers pratiques

---

### Slide 4 — Cartographie des cas d'usage RH

## Ou l'IA peut aider les professionnels RH

| Domaine | Cas d'usage concrets | Gain estime |
|---------|---------------------|-------------|
| **Recrutement** | Fiches de poste, screening CV, guide entretien, scoring | 40-60% du temps |
| **Administration RH** | Reponses salaries, notes internes, courriers, FAQ RH | 30-50% du temps |
| **Formation** | Plans de formation, analyse besoins, supports pedagogiques | 35-45% du temps |
| **QVT / Marque employeur** | Enquetes, communications internes, onboarding, offboarding | 25-40% du temps |
| **Juridique RH** | Veille convention collective, synthese accords, vulgarisation | 20-30% du temps |

**Point cle** : L'IA ne remplace pas le jugement RH. Elle accelere les taches a faible valeur ajoutee pour vous liberer du temps sur l'humain.

---

### Slide 5 — Le cycle de recrutement augmente par l'IA

## Du besoin a l'integration : l'IA a chaque etape

```
Besoin RH          Fiche de poste       Diffusion          Screening CV
[Brief manager] --> [IA + validation] --> [Multi-canal] --> [IA + humain]
                                                                |
                                                                v
Integration    <--  Decision finale  <--  Entretien    <--  Pre-selection
[Onboarding IA]    [100% humaine]       [Guide STAR IA]    [Shortlist]
```

| Etape | Role de l'IA | Role de l'humain |
|-------|-------------|-----------------|
| Fiche de poste | Genere le brouillon structure | Valide, ajuste la culture |
| Screening | Pre-analyse, identifie les matchs | Decision de shortlist |
| Entretien | Prepare les questions, la grille | Conduit, evalue le savoir-etre |
| Decision | Synthese des elements factuels | **Decision finale toujours humaine** |

---

### Slide 6 — Precautions essentielles en RH

## Les risques specifiques a l'usage de l'IA en RH

### Les biais dans le recrutement

| Type de biais | Exemple concret | Comment s'en premunir |
|---------------|-----------------|----------------------|
| **Biais de genre** | L'IA privilegie des formulations masculines dans les fiches de poste | Relecture inclusive systematique |
| **Biais d'affinite** | Screening qui favorise les parcours similaires a l'existant | CV anonymises, criteres objectifs |
| **Biais de confirmation** | Questions d'entretien orientees vers la validation | Grille standardisee, methode STAR |
| **Biais culturel** | Modele entraine sur des normes anglo-saxonnes | Adapter au contexte local/sectoriel |

### La conformite RGPD

- **Jamais** de donnees personnelles reelles dans un LLM public (noms, adresses, numeros)
- **Toujours** anonymiser les CV avant analyse
- **Documenter** l'usage de l'IA dans le processus de recrutement
- **Informer** les candidats si l'IA est utilisee (obligation legale)

### Le principe de non-discrimination

> L'article L1132-1 du Code du travail interdit toute discrimination. L'IA doit etre un outil d'equite, pas un amplificateur de biais.

---

### Slide 7 — Les bonnes pratiques RH avec l'IA

## Regles d'or pour les professionnels RH

| Regle | Explication | Application |
|-------|-------------|-------------|
| **Anonymisation systematique** | Aucune donnee personnelle dans le prompt | Remplacer noms, adresses, coordonnees |
| **Double verification** | Ne jamais faire confiance aveuglement | Relire chaque output RH avant usage |
| **Traçabilite** | Documenter quand l'IA est utilisee | Journal d'utilisation par processus |
| **Validation humaine** | L'IA propose, l'humain dispose | Pas de decision automatisee |
| **Inclusion** | Verifier les formulations genrees | Ecriture inclusive dans les sorties |

---

### Slide 8 — Atelier RH-1 : Presentation

# Atelier RH-1
## Redaction d'une fiche de poste a partir d'un brief
**Duree : 25 minutes** | Methode CREA

---

### Slide 9 — Atelier RH-1 : Le brief manager

## Votre situation

Vous etes **Responsable RH** dans une entreprise de **120 salaries**, secteur **services numeriques** (ESN). Le directeur commercial vous envoie ce brief :

> *"Il me faut un(e) charge(e) de clientele B2B, 2-3 ans d'experience, qui sait gerer un portefeuille de comptes existants et faire du developpement. Budget 32-38K. Teletravail 2j/semaine. On demarre en CDI des que possible."*

**Votre mission** : Produire une fiche de poste complete et inclusive en utilisant la methode CREA.

---

### Slide 10 — Atelier RH-1 : Le prompt CREA

## Construisez votre prompt avec la methode CREA

```
[CONTEXTE]
Je suis Responsable RH dans une ESN de 120 salaries. Le directeur commercial
a besoin de recruter un(e) charge(e) de clientele B2B. CDI, demarrage rapide.
Budget : 32-38K€ brut annuel. Teletravail 2 jours/semaine.

[ROLE]
Tu es un consultant senior en recrutement specialise dans les metiers
commerciaux B2B avec 15 ans d'experience en ESN.

[EXPLICITE]
Redige une fiche de poste complete comprenant :
- Intitule du poste (inclusif)
- Presentation de l'entreprise (3-4 lignes, a personnaliser)
- Missions principales (5-7 bullets)
- Profil recherche : formation, experience, competences techniques, soft skills
- Conditions : remuneration, avantages, teletravail, localisation
- Processus de recrutement (3 etapes)
Format : structure avec titres et puces. Ton : professionnel et attractif.
Ecriture inclusive. Longueur : 1 page A4 environ.

[ACTION]
Genere cette fiche de poste prete a etre diffusee sur LinkedIn et les
jobboards.
```

---

### Slide 11 — Atelier RH-1 : Criteres de reussite

## Checklist de validation de votre fiche de poste

| Critere | Oui/Non | Points de vigilance |
|---------|---------|-------------------|
| Intitule inclusif (ex: Charge(e) de clientele) | | Eviter "H/F" seul |
| Missions claires et concretes | | Verbes d'action au present |
| Competences techniques vs soft skills separees | | Pas de liste interminable |
| Remuneration mentionnee | | Obligatoire depuis 2024 (transparence salariale UE) |
| Avantages concurrentiels mis en avant | | Teletravail, formation, ambiance |
| Aucun critere discriminatoire | | Age, situation familiale, origine |
| Processus de recrutement clair | | Nombre d'etapes, delais |

**Exercice** : Generez la fiche, puis faites-la critiquer par l'IA avec ce prompt :

```
Relis cette fiche de poste avec un oeil critique. Identifie :
1. Tout critere potentiellement discriminatoire
2. Les formulations non inclusives
3. Les informations manquantes obligatoires
4. Les points qui pourraient etre plus attractifs
```

---

### Slide 12 — Atelier RH-2 : Presentation

# Atelier RH-2
## Screening de 5 CV anonymises vs fiche de poste
**Duree : 25 minutes** | Prompt + discussion fiabilite

---

### Slide 13 — Atelier RH-2 : Contexte et methode

## Analysons des candidatures avec l'IA

**Principe** : On fournit la fiche de poste + 5 CV anonymises au LLM pour obtenir une pre-analyse structuree.

### Les 5 profils anonymises fournis

| Candidat | Formation | Experience | Points cles |
|----------|-----------|------------|-------------|
| **Candidat A** | Ecole de commerce Bac+5 | 4 ans en ESN, gestion grands comptes | Anglais courant, CRM Salesforce |
| **Candidat B** | BTS NRC + Licence Pro | 2 ans en startup SaaS, SDR puis AE | Tres bon chasseur, peu de fidelisation |
| **Candidat C** | Master marketing digital | 3 ans en agence, gestion portefeuille PME | Bonne culture tech, pas d'ESN |
| **Candidat D** | Autodidacte, certif Google | 6 ans en retail B2C, reconversion B2B recente | Forte resilience, courbe d'apprentissage |
| **Candidat E** | Ingenieur reconverti commercial | 2 ans commercial B2B industrie | Tres technique, secteur different |

---

### Slide 14 — Atelier RH-2 : Le prompt de screening

## Prompt de pre-analyse des candidatures

```
[CONTEXTE]
Je recrute un(e) charge(e) de clientele B2B en CDI dans une ESN de 120 salaries.
Voici la fiche de poste : [coller la fiche de poste generee a l'atelier RH-1]

[ROLE]
Tu es un cabinet de recrutement specialise tech/commercial avec une approche
structuree et non discriminatoire.

[EXPLICITE]
Pour chaque candidat, fournis :
1. Score d'adequation /10 avec justification
2. Points forts par rapport au poste (3 max)
3. Points de vigilance (3 max)
4. Questions specifiques a poser en entretien (2)

Presente le resultat sous forme de tableau comparatif puis un classement
argumente. Sois factuel, base-toi uniquement sur les competences et
l'experience. Ne fais aucune inference sur l'age, le genre ou l'origine.

[ACTION]
Analyse ces 5 candidatures anonymisees et produis ta recommandation
de shortlist (3 candidats maximum).
```

---

### Slide 15 — Atelier RH-2 : Discussion fiabilite

## Questions critiques a se poser

### Ce que l'IA fait bien :
- Structurer la comparaison
- Identifier les mots-cles manquants/presents
- Proposer des questions d'entretien pertinentes

### Ce que l'IA fait MAL :
- Evaluer les soft skills a partir d'un CV
- Juger la qualite reelle d'une experience
- Detecter les signaux faibles (motivation, dynamique de carriere)
- Prendre en compte la culture d'entreprise

### Questions pour le groupe :

| Question | Reflexion attendue |
|----------|-------------------|
| L'IA a-t-elle reproduit des biais dans son classement ? | Verifier si les profils atypiques sont penalises |
| Auriez-vous fait le meme classement ? | Comparer jugement humain vs IA |
| Que manque-t-il a l'analyse ? | Elements non mesurables sur un CV |
| Feriez-vous confiance a ce screening sans relecture ? | **Non, jamais** |

---

### Slide 16 — Atelier RH-3 : Presentation

# Atelier RH-3
## Questions d'entretien methode STAR + grille d'evaluation
**Duree : 20 minutes**

---

### Slide 17 — Atelier RH-3 : La methode STAR expliquee

## Rappel : Structurer un entretien avec la methode STAR

```
S — Situation   : "Decrivez une situation ou..."
T — Tache       : "Quel etait votre role / objectif ?"
A — Action      : "Qu'avez-vous concretement fait ?"
R — Resultat    : "Quel a ete le resultat ? Qu'avez-vous appris ?"
```

**Pourquoi STAR ?**
- Evite les reponses theoriques ("je suis quelqu'un de motive")
- Force des exemples concrets et verifiables
- Permet d'evaluer les competences par les comportements reels
- Standardise l'evaluation entre candidats

---

### Slide 18 — Atelier RH-3 : Le prompt

## Generez un guide d'entretien complet

```
[CONTEXTE]
Je prepare l'entretien pour le poste de Charge(e) de clientele B2B en ESN
(120 salaries). Les candidats pre-selectionnes ont 2-4 ans d'experience
commerciale. L'entretien dure 45 minutes.

[ROLE]
Tu es un expert en techniques d'entretien structure, certifie methode STAR,
avec 10 ans d'experience en recrutement commercial.

[EXPLICITE]
Produis un guide complet comprenant :
1. Introduction (5 min) : mise a l'aise, presentation structure
2. 6 questions STAR couvrant : gestion de portefeuille, prospection,
   negociation, travail en equipe, gestion d'echec, organisation
3. Pour chaque question :
   - La question principale
   - 2 relances possibles
   - Ce qu'on cherche a evaluer
   - Indicateurs de reponse forte / faible
4. Grille de notation /5 par competence
5. Conclusion : prochaines etapes a presenter au candidat

Format : tableau pour la grille, texte structure pour les questions.

[ACTION]
Genere ce guide d'entretien pret a imprimer pour les managers recruteurs.
```

---

### Slide 19 — Atelier RH-3 : Grille d'evaluation attendue

## Exemple de grille generee par l'IA

| Competence evaluee | Question STAR associee | Note /5 | Observations |
|-------------------|----------------------|---------|-------------|
| Gestion de portefeuille | "Decrivez comment vous avez fidelise un client important qui envisageait de partir..." | ___/5 | |
| Prospection B2B | "Racontez une prospection reussie de A a Z sur un nouveau compte..." | ___/5 | |
| Negociation commerciale | "Parlez-moi d'une negociation difficile ou le client avait un budget serre..." | ___/5 | |
| Travail en equipe | "Decrivez un projet ou vous avez du collaborer avec des equipes techniques..." | ___/5 | |
| Gestion d'echec | "Racontez un deal perdu. Qu'avez-vous fait apres ?" | ___/5 | |
| Organisation | "Comment gerez-vous 50+ comptes actifs en parallele ?" | ___/5 | |

**Score total : ___/30** | Seuil recommande : 20/30 pour shortlist finale

---

### Slide 20 — Synthese Bloc RH

## Ce qu'il faut retenir pour les RH

| Atelier | Competence acquise | Piege a eviter |
|---------|-------------------|----------------|
| **RH-1** Fiche de poste | Prompt CREA pour generer rapidement | Ne pas personnaliser = offre generique |
| **RH-2** Screening CV | Analyse structuree multi-criteres | Faire confiance aveuglement au score |
| **RH-3** Guide STAR | Standardisation des entretiens | Lire les questions sans les adapter |

**Rappel fondamental** :

> L'IA en RH = un **assistant de preparation**, jamais un **decideur**.
> La decision de recruter reste 100% humaine, documentee et justifiable.

---

### Slide 21 — Pause (15 minutes)

# Pause
## 15 minutes

Profitez-en pour tester vos prompts RH sur vos propres cas

---

## BLOC 2 — IA POUR LE MARKETING (1h45)

---

### Slide 22 — Introduction Bloc Marketing

# BLOC 2
## L'IA pour le Marketing

Duree : 1h45 | 3 ateliers pratiques

---

### Slide 23 — Cartographie des cas d'usage Marketing

## Ou l'IA peut aider les professionnels du marketing

| Domaine | Cas d'usage concrets | Gain estime |
|---------|---------------------|-------------|
| **Creation de contenu** | Articles blog, posts LinkedIn, newsletters, scripts video | 50-70% du temps de redaction |
| **Strategie** | Analyse de marche, positionnement, personas, plans d'action | 30-40% du temps d'analyse |
| **SEO** | Recherche mots-cles, meta descriptions, maillage, briefs redacteurs | 40-60% du temps technique |
| **Publicite** | Accroches, A/B testing textes, landing pages, copy d'annonces | 35-50% du temps creatif |
| **Social media** | Calendrier editorial, adaptation multicanal, reponses communaute | 40-55% du temps operationnel |
| **Emailing** | Sequences, segmentation, objets, copy, automation | 30-45% du temps de creation |

---

### Slide 24 — La chaine de valeur marketing augmentee

## De la strategie a l'execution : l'IA a chaque maillon

```
STRATEGIE              CREATION              DIFFUSION              ANALYSE
+-----------+     +--------------+     +---------------+     +------------+
| Personas  |     | Contenu brut |     | Adaptation    |     | KPIs       |
| SWOT      | --> | Blog, posts  | --> | par canal     | --> | Feedback   |
| Positon.  |     | Newsletter   |     | SEO, format   |     | Iteration  |
+-----------+     +--------------+     +---------------+     +------------+
    [IA]              [IA]                  [IA]                [IA + humain]
```

**Point cle** : L'IA excelle en volume et en adaptation de format. La strategie et la vision de marque restent humaines.

---

### Slide 25 — Precautions essentielles en marketing

## Les risques specifiques a l'usage de l'IA en marketing

| Risque | Description | Solution |
|--------|-------------|----------|
| **Ton de marque** | Le LLM produit du contenu generique sans personnalite | Inclure une charte editoriale dans le prompt |
| **Hallucinations** | Chiffres inventes, sources inexistantes | **Verifier CHAQUE donnee factuelle** |
| **Originalite** | Contenu fade et "deja vu" qui ressemble a tout le monde | Ajouter votre angle, vos exemples, votre experience |
| **Plagiat** | Risque de contenu trop proche de sources existantes | Passage au detecteur + reecriture personnelle |
| **SEO negatif** | Google penalise le contenu 100% IA sans valeur ajoutee | Toujours enrichir avec expertise humaine |
| **Juridique** | Images generees, mentions de marques tierces | Verifier les droits, obtenir les autorisations |

**Regle d'or** : L'IA genere la premiere version. Vous apportez la touche humaine, la veracite et la personnalite de marque.

---

### Slide 26 — Atelier MKT-1 : Presentation

# Atelier MKT-1
## Chaine de contenu multicanal
LinkedIn / Blog / Newsletter / A/B testing
**Duree : 30 minutes**

---

### Slide 27 — Atelier MKT-1 : Le scenario

## Votre situation marketing

Vous etes **Responsable marketing** d'un editeur de logiciel SaaS B2B (gestion de projet).

**Votre sujet** : "5 erreurs qui plombent la productivite des equipes en 2025"

**Votre objectif** : Decliner ce sujet en une chaine de contenu coherente sur 4 canaux.

### La chaine de prompts a construire :

```
Prompt 1 : Article de blog (800 mots) — le contenu pilier
    |
    v
Prompt 2 : Post LinkedIn (accroche + carousel 5 slides)
    |
    v
Prompt 3 : Newsletter (teaser + CTA vers le blog)
    |
    v
Prompt 4 : 2 variantes A/B de l'objet de la newsletter
```

---

### Slide 28 — Atelier MKT-1 : Prompt 1 — Article blog

## Prompt pour l'article pilier

```
[CONTEXTE]
Je suis Responsable marketing d'un editeur SaaS B2B (outil de gestion de
projet). Notre cible : DG, directeurs de projet et managers d'equipes de
20-200 personnes. Notre ton : expert mais accessible, avec des exemples
concrets. Nous tutoyons le lecteur.

[ROLE]
Tu es un content strategist B2B SaaS avec 8 ans d'experience en inbound
marketing et une expertise en productivite d'equipe.

[EXPLICITE]
Redige un article de blog de 800 mots environ :
- Titre accrocheur avec chiffre (optimise SEO)
- Introduction avec hook statistique (a verifier)
- 5 erreurs concretes avec pour chacune : description, impact, solution
- Conclusion avec CTA vers une demo de l'outil
- 3 suggestions de meta description (155 caracteres max)
- Mots-cles cibles : productivite equipe, gestion de projet, collaboration
Ton : expert, concret, engageant. Tutoiement.

[ACTION]
Redige cet article de blog optimise SEO.
```

**Ensuite** : Utilisez la reponse comme base pour les prompts suivants (chaine).

---

### Slide 29 — Atelier MKT-1 : Prompts 2, 3, 4 — Declinaisons

## Decliner le contenu sur chaque canal

### Prompt 2 — Post LinkedIn
```
A partir de l'article que tu viens d'ecrire, cree un post LinkedIn :
- Accroche percutante (1ere ligne visible avant "voir plus")
- 5 slides de carousel (titre + 3 bullets par slide)
- CTA : lien vers l'article
- 3 hashtags pertinents
Format : texte du post + contenu de chaque slide separement.
```

### Prompt 3 — Newsletter
```
A partir du meme article, cree une newsletter :
- Objet : accrocheur, < 50 caracteres
- Pre-header : complementaire, < 80 caracteres
- Corps : teaser engageant (150 mots), 1 stat cle, CTA vers l'article
- PS optionnel pour creer de la proximite
```

### Prompt 4 — A/B test objets
```
Genere 4 variantes d'objet pour la newsletter :
- Variante A : question directe
- Variante B : chiffre choc
- Variante C : curiosite / mystere
- Variante D : benefice direct
Pour chaque variante : l'objet (< 50 car.) + pourquoi ca fonctionne.
```

---

### Slide 30 — Atelier MKT-2 : Presentation

# Atelier MKT-2
## Analyse concurrentielle + matrice SWOT
**Duree : 30 minutes**

---

### Slide 31 — Atelier MKT-2 : Le prompt d'analyse

## Construisez votre analyse concurrentielle

**Scenario** : Vous devez preparer une analyse concurrentielle pour le comite de direction.

```
[CONTEXTE]
Je suis Responsable marketing d'une entreprise de [votre choix : formation
professionnelle / logiciel SaaS / cabinet de conseil / e-commerce].
Notre marche : [decrire brievement]. Nos 3 concurrents principaux :
[Concurrent A], [Concurrent B], [Concurrent C].

[ROLE]
Tu es un consultant en strategie marketing avec 12 ans d'experience
en analyse de marche et positionnement concurrentiel.

[EXPLICITE]
Produis une analyse en 3 parties :
1. **Tableau comparatif** (6-8 criteres : prix, positionnement, cible,
   canaux, forces, faiblesses, part de marche estimee, innovation)
2. **Matrice SWOT** de notre entreprise par rapport au marche
   (tableau 2x2 : Forces/Faiblesses internes, Opportunites/Menaces externes)
3. **3 recommandations strategiques** argumentees avec priorite et horizon

Precise clairement quand une information est une estimation ou une
hypothese (car tu n'as pas acces aux donnees reelles).

[ACTION]
Realise cette analyse concurrentielle structuree.
```

**Attention** : Les informations factuelles (parts de marche, prix) devront etre **verifiees**. L'IA vous donne un cadre, pas des donnees fiables.

---

### Slide 32 — Atelier MKT-2 : Template SWOT attendu

## Exemple de matrice SWOT generee

|  | **Positif** | **Negatif** |
|--|------------|------------|
| **Interne** | **FORCES** | **FAIBLESSES** |
| | - Expertise sectorielle reconnue | - Notoriete limitee vs leaders |
| | - Prix competitif | - Equipe marketing reduite |
| | - Agilite (PME vs grands groupes) | - Budget pub limite |
| **Externe** | **OPPORTUNITES** | **MENACES** |
| | - Marche en croissance +15%/an | - Entree de nouveaux acteurs VC-funded |
| | - Reglementation favorable | - Consolidation du marche (rachats) |
| | - Demande de solutions locales | - IA qui reduit les barrieres d'entree |

**Exercice bonus** : Demandez a l'IA de challenger votre SWOT :

```
Joue l'avocat du diable. Quelles forces pourraient etre des faiblesses
deguisees ? Quelles opportunites cachent des menaces ?
```

---

### Slide 33 — Atelier MKT-3 : Presentation

# Atelier MKT-3
## Creation de 2 buyer personas
**Duree : 25 minutes**

---

### Slide 34 — Atelier MKT-3 : Le prompt personas

## Creez des personas exploitables

```
[CONTEXTE]
Notre entreprise vend [produit/service]. Notre cible principale est
[decrire]. Nous avons identifie 2 segments prioritaires :
- Segment 1 : [decrire brievement]
- Segment 2 : [decrire brievement]

[ROLE]
Tu es un expert en marketing strategique et en segmentation B2B/B2C avec
10 ans d'experience en creation de buyer personas.

[EXPLICITE]
Pour chaque persona, cree une fiche complete :
- **Identite** : Prenom fictif, age, poste, entreprise type, localisation
- **Situation pro** : responsabilites, equipe, objectifs annuels, KPIs
- **Problemes** : 3 douleurs quotidiennes liees a notre offre
- **Motivations** : ce qui le/la pousse a chercher une solution
- **Freins** : ce qui le/la retient d'acheter
- **Parcours d'achat** : ou il/elle cherche l'info, qui influence, combien
  de temps dure la decision
- **Message cle** : la phrase qui le/la convaincrait
- **Canaux preferes** : ou le/la toucher

Format : 2 fiches structurees, visuellement claires.

[ACTION]
Cree ces 2 buyer personas detailles et exploitables.
```

---

### Slide 35 — Atelier MKT-3 : Exemple de persona generee

## Persona 1 — "Sophie, la DRH debordee"

| Categorie | Detail |
|-----------|--------|
| **Identite** | Sophie, 42 ans, DRH, PME industrielle 200 salaries, Lyon |
| **Situation** | Equipe de 3, gere recrutement + admin + formation. Reporting au DG |
| **Objectifs** | Reduire le turnover de 18% a 12%, digitaliser les processus RH |
| **Douleurs** | 1) Noyee sous l'admin 2) Recrutements qui trainent 3) Pas d'outils modernes |
| **Motivations** | Gagner du temps, professionnaliser les processus, montrer sa valeur au DG |
| **Freins** | Budget serre, peur de la complexite technique, equipe resistante au changement |
| **Parcours achat** | LinkedIn > webinaire > demo > 3 mois de reflexion > validation DG |
| **Message cle** | "Liberez 10h/semaine sur l'admin RH pour vous concentrer sur l'humain" |
| **Canaux** | LinkedIn, webinaires, salons RH, bouche-a-oreille pairs |

**Exercice** : Creez le persona 2 pour votre propre contexte, puis demandez a l'IA :

```
Compare ces 2 personas. Quel contenu marketing pourrait toucher les deux
simultanement ? Quels contenus doivent etre specifiques a chacun ?
```

---

### Slide 36 — Synthese Bloc Marketing

## Ce qu'il faut retenir pour le marketing

| Atelier | Competence acquise | Point de vigilance |
|---------|-------------------|-------------------|
| **MKT-1** Contenu multicanal | Chaine de prompts pour decliner un sujet | Adapter le ton a chaque canal |
| **MKT-2** Analyse SWOT | Structure d'analyse concurrentielle | Verifier toutes les donnees factuelles |
| **MKT-3** Buyer personas | Personas detaillees et exploitables | Valider avec les donnees terrain reelles |

**Astuce pro** : Creez un **prompt systeme permanent** avec votre charte editoriale :

```
Avant chaque creation de contenu, garde en tete :
- Notre ton : [decrire]
- Nos valeurs : [lister]
- Notre cible : [decrire]
- Nos mots interdits : [lister]
- Notre CTA par defaut : [preciser]
```

---

### Slide 37 — Bilan de la session 6

## Ce que vous avez accompli aujourd'hui

### RH — 3 ateliers
- Fiche de poste complete en 15 min (vs 1-2h habituellement)
- Screening structure de 5 CV avec grille de comparaison
- Guide d'entretien STAR pret a l'emploi

### Marketing — 3 ateliers
- Chaine de contenu multicanal a partir d'un seul sujet
- Analyse concurrentielle SWOT structuree
- 2 buyer personas exploitables

### La regle a retenir

> **L'IA accelere la production. Vous apportez l'expertise, le jugement et la touche humaine.**
> Sans votre validation, aucun contenu genere ne devrait etre diffuse.

---

### Slide 38 — Preparation session suivante

## Demain matin : Session 7

# L'IA pour la Finance, le Commercial et la Gestion

**A preparer** :
- Pensez a un cas concret de votre metier que vous aimeriez traiter
- Si vous etes en finance : un type de rapport que vous produisez regulierement
- Si vous etes commercial : une sequence de prospection type
- Si vous etes en gestion : un type de document que vous redigez souvent

A demain !

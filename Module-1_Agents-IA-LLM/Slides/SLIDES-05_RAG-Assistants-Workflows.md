# SLIDES-05 — RAG, Assistants Personnalises et Workflows IA

> **Session 5** — Jour 3, matin (9h00-12h30)
> **Duree** : 3h30 | **Niveau** : Intermediaire
> **Prerequis** : Methode CREA, prompting avance et chaines de prompts (Sessions 3-4)
> **Objectifs** : Comprendre le RAG, creer des assistants personnalises, concevoir des workflows IA

---

<!-- ============================================================ -->
<!-- BLOC 1 — LE RAG SIMPLIFIE (45 min)                           -->
<!-- ============================================================ -->

## BLOC 1 — LE RAG SIMPLIFIE (45 min)

---

### Slide 1 — Page de titre

# RAG, Assistants et Workflows IA
## Session 5 — Connecter l'IA a vos donnees et automatiser

Formation IA pour les Metiers du Tertiaire
Jour 3 — Matin

---

### Slide 2 — Objectifs de la session

## Ce que vous saurez faire a la fin de cette session

1. **Comprendre** comment connecter un LLM a vos documents internes (RAG)
2. **Creer** un assistant IA personnalise (GPT, Claude Project, Gem)
3. **Definir** ce qu'est un agent IA autonome et ses limites actuelles
4. **Concevoir** un workflow IA adapte a votre metier
5. **Choisir** la bonne plateforme d'automatisation selon vos besoins

---

### Slide 3 — Deroulement de la matinee

| Bloc | Contenu | Duree |
|------|---------|-------|
| 1 | Le RAG simplifie : connecter l'IA a vos documents | 45 min |
| -- | **Pause cafe** | **10 min** |
| 2 | Creation d'assistants personnalises (GPTs, Projects, Gems) | 1h15 |
| -- | **Pause** | **5 min** |
| 3 | Agents IA autonomes et workflows | 1h15 |

---

### Slide 4 — Rappel : ou en sommes-nous ?

## Ce que vous maitrisez deja

```
SESSION 3 (Jour 2 matin)           SESSION 4 (Jour 2 apres-midi)
~~~~~~~~~~~~~~~~~~~~~~~~           ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
[x] Methode CREA                   [x] Few-shot prompting
[x] Prompts structures             [x] Chain-of-thought
[x] Iteration                      [x] Structuration des outputs
                                    [x] Chaines de prompts

                SESSION 5 (Aujourd'hui)
                ~~~~~~~~~~~~~~~~~~~~~~~
                [ ] RAG : l'IA lit VOS documents
                [ ] Assistants personnalises
                [ ] Agents IA et workflows
```

Vous savez dialoguer avec l'IA. Aujourd'hui : on lui donne **acces a vos donnees** et on l'**automatise**.

---

### Slide 5 — Introduction au RAG

# Le RAG simplifie
## Quand l'IA consulte vos documents

---

### Slide 6 — Le probleme fondamental

## Les LLM ne connaissent pas VOS documents

```
+-----------------------------------------------+
|              CE QUE LE LLM CONNAIT             |
|                                                |
|  - Wikipedia, livres, sites web publics        |
|  - Connaissances generales (jusqu'a sa date    |
|    de coupure : 2024-2025 selon le modele)     |
|                                                |
+-----------------------------------------------+

+-----------------------------------------------+
|          CE QUE LE LLM NE CONNAIT PAS          |
|                                                |
|  - Votre convention collective                 |
|  - Vos procedures internes                     |
|  - Vos rapports trimestriels                   |
|  - Vos fiches produits                         |
|  - Vos contrats fournisseurs                   |
|  - Vos comptes rendus de reunion               |
|                                                |
+-----------------------------------------------+
```

Le LLM est un expert generaliste qui n'a **jamais mis les pieds dans votre entreprise**.

---

### Slide 7 — Consequences concretes

## Sans vos documents, le LLM improvise

| Votre question | Ce que le LLM fait | Le risque |
|----------------|---------------------|-----------|
| "Quel est notre delai de preavis ?" | Repond avec le Code du travail general | Mauvaise reponse si votre convention est differente |
| "Resume notre rapport Q3" | Invente un resume plausible | **Hallucination** totale |
| "Quelles sont nos conditions de retour ?" | Donne des conditions generiques | Client mal informe |
| "Analyse nos ventes du mois" | Refuse ou invente des chiffres | Donnees fausses |

**Le LLM ne dit pas "je ne sais pas"** — il fabrique une reponse convaincante mais fausse.

---

### Slide 8 — La solution : le RAG

## RAG = Retrieval-Augmented Generation

En francais : **Generation augmentee par la recherche**

```
+-------------------------------------------------------------------+
|                                                                   |
|   R = Retrieval    -->  On RETROUVE les morceaux pertinents       |
|                         dans vos documents                        |
|                                                                   |
|   A = Augmented    -->  On AUGMENTE le prompt du LLM avec         |
|                         ces morceaux                              |
|                                                                   |
|   G = Generation   -->  Le LLM GENERE une reponse basee sur      |
|                         vos documents + ses connaissances         |
|                                                                   |
+-------------------------------------------------------------------+
```

Idee cle : on ne re-entraine pas le LLM. On lui **donne a lire** les bons passages au bon moment.

---

### Slide 9 — Le RAG en 3 etapes

## Comment ca marche (version simplifiee)

```
ETAPE 1 : PREPARATION (une seule fois)
+------------------+      +-----------+      +------------------+
| Vos documents    | ---> | Decoupage | ---> | Index de         |
| (PDF, Word,      |      | en petits |      | morceaux         |
|  Excel, web...)  |      | morceaux  |      | (base vectorielle)|
+------------------+      +-----------+      +------------------+

ETAPE 2 : RECHERCHE (a chaque question)
+------------------+      +------------------+      +------------------+
| Votre question   | ---> | Recherche des    | ---> | 3-5 morceaux     |
| "Quel est le     |      | morceaux les     |      | les plus         |
|  delai de        |      | plus proches     |      | pertinents       |
|  preavis ?"      |      | de la question   |      |                  |
+------------------+      +------------------+      +------------------+

ETAPE 3 : GENERATION
+------------------+      +------------------+      +------------------+
| Question         | ---> |       LLM        | ---> | Reponse basee    |
|       +          |      |  "Voici ce que   |      | sur VOS          |
| Morceaux         |      |   disent vos     |      | documents        |
| pertinents       |      |   documents..."  |      | + sources citees |
+------------------+      +------------------+      +------------------+
```

---

### Slide 10 — L'analogie de la bibliotheque

## Analogie : le LLM consulte votre bibliotheque

```
SANS RAG :                              AVEC RAG :

+-------------+                        +-------------+
|    LLM      |                        |    LLM      |
|  (expert    |                        |  (expert    |
|  generaliste|                        |  generaliste|
|  sans acces |                        |  AVEC acces |
|  a vos      |                        |  a votre    |
|  documents) |                        |  biblio-    |
+------+------+                        |  theque)    |
       |                               +------+------+
       v                                      |
  "Je pense que..."                           v
  (reponse generique                    "D'apres votre
   ou hallucination)                     document X, page 3..."
                                        (reponse sourcee)
```

C'est comme si vous donniez a un consultant externe **acces a votre GED** avant de lui poser une question.

---

### Slide 11 — Ce que le RAG change par metier

## Exemples concrets par metier

| Metier | Sans RAG | Avec RAG |
|--------|----------|----------|
| **RH** | "Le preavis est de 1 a 3 mois selon la convention" | "Selon votre convention Syntec art. 15, le preavis est de 3 mois pour les cadres" |
| **Commercial** | "Voici un argumentaire generique" | "Pour le client Dupont, en tenant compte de son historique d'achats Q1-Q3..." |
| **Comptabilite** | "En general, la TVA se declare..." | "Selon votre procedure interne v2.3, la declaration TVA suit le circuit..." |
| **Marketing** | "Voici des tendances du marche" | "D'apres votre etude de marche 2024 et le rapport concurrent..." |
| **Juridique** | "L'article L.1234-1 du Code..." | "L'article 7.2 de votre contrat-cadre fournisseur prevoit..." |

---

### Slide 12 — Outils RAG accessibles sans code

## Bonne nouvelle : le RAG est deja dans vos outils

Pas besoin de coder. Plusieurs outils grand public integrent le RAG :

```
+---------------------+-------------------------------------------+
| OUTIL               | COMMENT UTILISER LE RAG                   |
+---------------------+-------------------------------------------+
| ChatGPT (Plus/Team) | Upload fichiers dans une conversation     |
|                     | OU creation d'un GPT avec fichiers        |
+---------------------+-------------------------------------------+
| Claude (Pro/Team)   | Upload documents dans le chat              |
|                     | OU creation d'un Project avec documents    |
+---------------------+-------------------------------------------+
| NotebookLM (Google) | Upload de documents, analyse avec sources  |
|                     | Gratuit, ideal pour la recherche           |
+---------------------+-------------------------------------------+
| Copilot (Microsoft) | Interroge vos fichiers SharePoint/OneDrive |
|                     | Necessite licence Microsoft 365 Copilot    |
+---------------------+-------------------------------------------+
```

---

### Slide 13 — ChatGPT : upload dans une conversation

## ChatGPT : le RAG le plus simple

**Methode 1 : Upload dans le chat**

```
1. Ouvrez une conversation ChatGPT
2. Cliquez sur l'icone trombone (📎)
3. Selectionnez vos fichiers (PDF, Word, Excel, images...)
4. Posez votre question

Le LLM lit les fichiers et repond en se basant dessus.
```

**Limites :**
- Les fichiers ne sont disponibles QUE dans cette conversation
- Taille maximale par fichier : ~50 pages / 512 Mo
- A chaque nouvelle conversation, il faut re-uploader

**Ideal pour** : une question ponctuelle sur un document precis.

---

### Slide 14 — Claude : Projects pour un RAG persistant

## Claude Projects : le contexte qui reste

**Methode : creer un Project**

```
1. Claude.ai > Panneau lateral > Projects
2. "Create Project" > Donnez un nom
3. Ajoutez vos documents dans "Project Knowledge"
4. Redigez des instructions systeme (custom instructions)
5. Toutes les conversations dans ce Project auront acces aux docs

      +---------------------------+
      |      PROJECT              |
      |  "Veille Marketing"       |
      |                           |
      |  Documents :              |
      |  - rapport-marche.pdf     |
      |  - analyse-concurrent.pdf |
      |  - brief-strategie.docx   |
      |                           |
      |  Instructions :           |
      |  "Tu es un analyste       |
      |   marketing senior..."    |
      +---------------------------+
              |
              v
      Toutes les conversations
      dans ce Project ont acces
      aux documents et instructions
```

---

### Slide 15 — NotebookLM : le RAG gratuit de Google

## NotebookLM : analyse de documents avec sources

**Pourquoi NotebookLM est special :**

- **Gratuit** (compte Google suffit)
- **Sources citees** : chaque reponse renvoie au passage exact du document
- **Multi-documents** : jusqu'a 50 sources par notebook
- **Audio Overview** : genere un podcast a partir de vos documents
- Formats acceptes : PDF, Google Docs, Google Slides, sites web, YouTube

```
+-------------------------------------------------------------------+
|                     NOTEBOOKLM                                     |
|                                                                   |
|  Sources :                    Chat :                              |
|  [1] rapport-annuel.pdf      Q: "Quel a ete le CA T3 ?"          |
|  [2] budget-2024.xlsx        R: "Selon [1] page 12, le CA T3     |
|  [3] notes-comite.pdf           s'eleve a 2.3M EUR, en hausse    |
|                                  de 7% par rapport a T2 [1]       |
|                                  Le budget previsionnel [2]        |
|                                  prevoyait 2.1M EUR."             |
|                                                                   |
|                              [1] = lien cliquable vers le passage |
+-------------------------------------------------------------------+
```

---

### Slide 16 — Demo NotebookLM : preparation

## Demonstration : NotebookLM en action

**Scenario** : Un responsable marketing veut analyser 3 documents

Documents uploades :
1. **Etude de marche 2024** (PDF, 25 pages)
2. **Rapport d'activite concurrent principal** (PDF, 15 pages)
3. **Brief strategique interne** (Word, 8 pages)

**Ce que nous allons tester :**
- Question simple : "Quelle est notre part de marche ?"
- Question croisee : "Quels sont les ecarts entre notre strategie et les tendances du marche ?"
- Verification des sources : chaque reponse renvoie-t-elle au bon document ?
- Generation d'un resume croise des 3 documents

> **Note formateur** : ouvrir notebooklm.google.com et proceder a la demo en direct.

---

### Slide 17 — Demo NotebookLM : resultats

## Ce que NotebookLM nous montre

**Avantages observes :**
- Chaque affirmation est liee a une source precise
- On peut cliquer sur la source pour verifier le passage original
- Les reponses croisent intelligemment les documents
- La fonction "Audio Overview" cree un podcast de synthese

**Limites observees :**
- Ne fonctionne qu'avec les documents uploades (pas d'acces web en temps reel)
- Pas d'historique entre les sessions (chaque notebook est independant)
- Qualite variable selon la mise en forme des documents sources
- Pas d'actions possibles : uniquement de l'analyse et de la synthese

---

### Slide 18 — Tableau comparatif RAG

## Quel outil RAG pour quel usage ?

| Critere | ChatGPT Upload | Claude Projects | NotebookLM | Copilot M365 |
|---------|---------------|-----------------|------------|--------------|
| **Cout** | Inclus (Plus) | Inclus (Pro) | Gratuit | Licence Copilot |
| **Persistance** | Non (par chat) | Oui (par Project) | Oui (par notebook) | Oui (SharePoint) |
| **Sources citees** | Parfois | Parfois | Toujours | Souvent |
| **Nb de fichiers** | ~10/chat | ~200/Project | ~50/notebook | Illimite (tenant) |
| **Formats** | PDF, Word, code | PDF, Word, code | PDF, Docs, web | Office, SharePoint |
| **Ideal pour** | Question ponctuelle | Projet suivi | Recherche, analyse | Ecosysteme Microsoft |

---

### Slide 19 — Transition vers le Bloc 2

## Le RAG, c'est bien. Un assistant dedie, c'est mieux.

```
  RAG simple                      Assistant personnalise
  (upload + question)             (RAG + instructions + outils)

  +------------------+            +---------------------------+
  | Document         |            | Documents                 |
  | + Question       |            | + Instructions permanentes|
  +--------+---------+            | + Personnalite definie    |
           |                      | + Outils connectes        |
           v                      +-------------+-------------+
  Reponse ponctuelle                            |
                                                v
                                  Assistant reutilisable
                                  par toute l'equipe
```

**Apres la pause** : on cree des assistants complets et reutilisables.

---

<!-- ============================================================ -->
<!-- PAUSE CAFE (10 min)                                          -->
<!-- ============================================================ -->

### Slide 20 — Pause cafe

## Pause cafe -- 10 minutes

Pensez deja a un cas d'usage dans votre metier :
- Quels documents internes aimeriez-vous rendre "interrogeables" par l'IA ?
- Quel assistant vous ferait gagner du temps au quotidien ?

---

<!-- ============================================================ -->
<!-- BLOC 2 — CREATION D'ASSISTANTS PERSONNALISES (1h15)          -->
<!-- ============================================================ -->

## BLOC 2 — CREATION D'ASSISTANTS PERSONNALISES (1h15)

---

### Slide 21 — Introduction Bloc 2

# Assistants IA personnalises
## Vos collegues virtuels, configures pour votre metier

---

### Slide 22 — Qu'est-ce qu'un assistant personnalise ?

## Assistant = RAG + Instructions + Outils

```
+-------------------------------------------------------------------+
|                   ASSISTANT PERSONNALISE                            |
|                                                                   |
|  +---------------+  +------------------+  +-----------------+     |
|  | CONNAISSANCES |  | INSTRUCTIONS     |  | OUTILS          |     |
|  |               |  |                  |  |                 |     |
|  | Vos documents |  | Role et ton      |  | Navigation web  |     |
|  | Vos donnees   |  | Regles a suivre  |  | Generation image|     |
|  | Vos procedures|  | Format de sortie |  | Execution code  |     |
|  | Vos FAQ       |  | Limites a poser  |  | API externes    |     |
|  +---------------+  +------------------+  +-----------------+     |
|                              |                                     |
|                              v                                     |
|                    ASSISTANT PRET A L'EMPLOI                       |
|                    reutilisable, partageable                       |
+-------------------------------------------------------------------+
```

Un assistant personnalise, c'est un **LLM configure une fois** qui repond toujours dans le meme cadre.

---

### Slide 23 — Les 3 grandes plateformes

## Ou creer vos assistants ?

| Plateforme | Nom de la fonctionnalite | Acces requis | Partage |
|------------|--------------------------|--------------|---------|
| **ChatGPT** | GPTs personnalises | ChatGPT Plus/Team | Lien, GPT Store |
| **Claude** | Projects | Claude Pro/Team | Equipe (Team) |
| **Gemini** | Gems | Gemini Advanced | Personnel |

Toutes suivent le meme principe :
**Documents** + **Instructions** + **Configuration** = **Assistant dedie**

---

### Slide 24 — GPTs : structure

## GPTs personnalises (ChatGPT Plus/Team)

Un GPT se configure avec 3 briques :

```
+-------------------------------------------------------------------+
|                        GPT PERSONNALISE                            |
|                                                                   |
|  1. INSTRUCTIONS (System Prompt)                                  |
|     "Tu es un assistant RH specialise dans la convention           |
|      Syntec. Tu reponds aux questions des salaries..."            |
|                                                                   |
|  2. CONNAISSANCES (Knowledge)                                     |
|     [convention-syntec.pdf]                                       |
|     [reglement-interieur.pdf]                                     |
|     [FAQ-RH-interne.docx]                                        |
|                                                                   |
|  3. OUTILS (Capabilities)                                         |
|     [x] Navigation web                                            |
|     [x] Generation d'images (DALL-E)                              |
|     [x] Interpretation de code                                    |
|     [ ] Actions externes (API)                                    |
+-------------------------------------------------------------------+
```

---

### Slide 25 — Demo : creation d'un GPT "FAQ RH"

## Demonstration pas-a-pas : GPT "Assistant FAQ RH"

**Etape 1 : Acceder au builder**
```
ChatGPT > Menu lateral > "Explore GPTs" > "Create"
```

**Etape 2 : Configuration (onglet "Configure")**
```
Nom        : Assistant FAQ RH - Convention Syntec
Description: Repond aux questions RH des salaries
             en se basant sur la convention Syntec
             et les procedures internes.
```

**Etape 3 : Instructions**
```
Tu es l'assistant RH de l'entreprise [Nom].
Tu reponds aux questions des salaries sur :
- Les conges (poses, solde, regles)
- Le temps de travail et les horaires
- Les avantages sociaux
- Les procedures administratives RH

Regles :
- Base tes reponses UNIQUEMENT sur les documents fournis
- Cite toujours l'article ou la page source
- Si tu ne trouves pas l'information, dis "Je n'ai pas
  cette information dans mes documents. Contactez le
  service RH : rh@entreprise.com"
- Ne donne JAMAIS de conseil juridique
- Ton professionnel mais accessible
```

---

### Slide 26 — Demo GPT FAQ RH (suite)

## Demonstration (suite)

**Etape 4 : Upload des connaissances**
```
Knowledge :
  [+] convention-collective-syntec.pdf
  [+] reglement-interieur-2024.pdf
  [+] FAQ-RH-interne.docx
  [+] accord-teletravail.pdf
```

**Etape 5 : Activer les capacites**
```
Capabilities :
  [x] Web Browsing         (pour les mises a jour legales)
  [ ] DALL-E Image Gen     (inutile ici)
  [x] Code Interpreter     (pour analyser des tableaux)
```

**Etape 6 : Tester**
```
Question test : "Combien de jours de teletravail par semaine ?"
Reponse attendue : citation de l'accord de teletravail avec article
```

**Etape 7 : Partager**
```
> "Only people with a link" ou "Anyone at [entreprise]"
```

---

### Slide 27 — Claude Projects : vue d'ensemble

## Claude Projects : le contexte persistant

**Difference cle avec les GPTs** : le Project est un **espace de travail** avec du contexte persistant, pas un "bot" autonome.

```
                  +-----------------------------+
                  |     CLAUDE PROJECT           |
                  |  "Veille Concurrentielle"    |
                  +-----------------------------+
                  |                             |
                  |  Project Knowledge :        |
                  |  - rapports-concurrent.pdf  |
                  |  - veille-presse-Q3.pdf     |
                  |  - grille-analyse.xlsx      |
                  |                             |
                  |  Custom Instructions :      |
                  |  "Tu es un analyste         |
                  |   concurrentiel senior..."  |
                  |                             |
                  +-----------------------------+
                       /        |         \
                      /         |          \
               Chat 1      Chat 2       Chat 3
               "Analyse    "Compare     "Quelles
                forces du   prix avec    tendances
                concurrent   notre       emergentes ?"
                X"           offre"
```

Chaque conversation herite des documents et des instructions du Project.

---

### Slide 28 — Demo : Claude Project "Veille Marketing"

## Demonstration : Project "Veille concurrentielle Marketing"

**Etape 1 : Creer le Project**
```
Claude.ai > Projects > "Create a Project"
Nom : Veille concurrentielle Marketing Q4
```

**Etape 2 : Ajouter les documents (Project Knowledge)**
```
[+] etude-marche-sectorielle-2024.pdf
[+] rapport-annuel-concurrent-A.pdf
[+] rapport-annuel-concurrent-B.pdf
[+] nos-chiffres-ventes-Q1-Q3.xlsx
[+] brief-strategique-direction.docx
```

**Etape 3 : Rediger les Custom Instructions**
```
Tu es un analyste marketing senior specialise en veille
concurrentielle pour le secteur [X].

Quand tu analyses un concurrent :
1. Identifie ses forces et faiblesses
2. Compare avec notre positionnement (voir nos-chiffres-ventes)
3. Propose des axes de differenciation
4. Cite toujours tes sources avec le nom du document et la page

Format de sortie : utilise des tableaux comparatifs et des
bullet points. Termine par 3 recommandations actionnables.
```

---

### Slide 29 — Demo Project Veille (resultats)

## Ce que le Project permet

**Questions testees :**

| Question posee | Type de reponse |
|----------------|-----------------|
| "Quelles sont les forces du concurrent A ?" | Analyse structuree avec citations du rapport annuel |
| "Compare leur strategie prix avec la notre" | Tableau comparatif croisant nos chiffres et les leurs |
| "Quelles opportunites pour Q4 ?" | 3 recommandations basees sur l'etude de marche + brief |

**Avantages de Claude Projects :**
- Fenetre de contexte tres large (200K tokens = ~500 pages)
- Instructions personnalisees respectees dans chaque chat
- Possibilite d'ajouter des documents au fil du temps
- Partage avec l'equipe (plan Team)

---

### Slide 30 — Gemini Gems : apercu rapide

## Gemini Gems : les assistants Google

**Gems** = equivalent Google des GPTs et Projects

```
Gemini > Gem Manager > "New Gem"

Configuration :
- Nom et description
- Instructions personnalisees
- Pas d'upload de fichiers dans les Gems (limitation actuelle)
  -> Mais integration Google Drive et Workspace

Ideal si :
- Votre entreprise est sur Google Workspace
- Vous voulez un assistant connecte a Drive, Docs, Sheets
- Vous n'avez pas besoin d'upload de fichiers hors Google
```

**A noter** : l'ecosysteme Gems evolue rapidement. Verifiez les fonctionnalites les plus recentes.

---

### Slide 31 — Tableau comparatif des assistants

## Comparatif : GPTs vs Projects vs Gems

| Critere | GPTs (ChatGPT) | Projects (Claude) | Gems (Gemini) |
|---------|----------------|-------------------|----------------|
| **Upload fichiers** | Oui (Knowledge) | Oui (Project Knowledge) | Non (Drive) |
| **Instructions** | Oui (system prompt) | Oui (custom instructions) | Oui |
| **Contexte** | Par conversation | Persistant (Project) | Par conversation |
| **Fenetre contexte** | 128K tokens | 200K tokens | 1M tokens |
| **Partage** | Lien / GPT Store | Equipe (plan Team) | Personnel |
| **Outils integres** | Web, DALL-E, Code | Artefacts, analyse | Google Workspace |
| **API externes** | Oui (Actions) | Non | Extensions Google |
| **Ideal pour** | Assistants partages | Projets d'equipe | Ecosysteme Google |

---

### Slide 32 — Exemples d'assistants par metier

## Idees d'assistants pour chaque metier

| Metier | Assistant | Documents charges | Utilisation |
|--------|-----------|-------------------|-------------|
| **RH** | FAQ Salaries | Convention, reglement, accords | Questions des employes |
| **Commercial** | Prep' Rendez-vous | Fiches clients, historique, catalogue | Briefing avant RDV |
| **Marketing** | Analyste Veille | Etudes, rapports concurrents, presse | Analyse concurrentielle |
| **Comptabilite** | Guide Procedures | Procedures comptables, plan comptable | Ecritures et normes |
| **Juridique** | Revue Contrat | Modeles de contrats, jurisprudence interne | Premiere analyse de contrat |
| **Communication** | Redacteur Marque | Charte editoriale, ton of voice, exemples | Redaction coherente |
| **Support** | Agent Niveau 1 | FAQ, base de connaissances, procedures | Reponses aux tickets recurrents |

---

### Slide 33 — Atelier pratique : creez votre assistant

## Atelier (30 min) : Creez votre assistant personnalise

**Objectif** : Creer un assistant fonctionnel adapte a votre metier

**Etapes :**

```
1. DEFINIR (5 min)
   - Quel probleme resout cet assistant ?
   - Qui va l'utiliser ?
   - Quels documents lui donner ?

2. CONFIGURER (15 min)
   - Choisissez votre plateforme (ChatGPT, Claude ou Gemini)
   - Redigez les instructions (utilisez la methode CREA !)
   - Uploadez 2-3 documents (meme fictifs si besoin)

3. TESTER (10 min)
   - Posez 3 questions variees
   - Verifiez que les reponses citent les sources
   - Ajustez les instructions si necessaire
```

> **Fiche atelier** : voir FICHE-ATELIER-05A pour le guide detaille

---

### Slide 34 — Criteres de reussite de l'atelier

## Votre assistant est reussi si...

- [ ] Il repond en se basant sur les documents fournis (pas d'invention)
- [ ] Il cite ses sources (document, page, article)
- [ ] Il refuse de repondre quand l'information n'est pas dans ses documents
- [ ] Son ton est adapte a l'usage (professionnel, accessible, technique...)
- [ ] Un collegue pourrait l'utiliser sans formation supplementaire

**Erreur frequente** : des instructions trop vagues.
Appliquez la methode **CREA** pour vos instructions systeme !

---

### Slide 35 — Transition vers le Bloc 3

## Des assistants aux workflows : le niveau suivant

```
NIVEAU 1                  NIVEAU 2                 NIVEAU 3
Prompt unique     -->     Assistant          -->    Workflow
                          personnalise              automatise

Vous ecrivez              Vous configurez           Le systeme
un prompt                 une fois, puis            fonctionne
a chaque fois             re-utilisez               TOUT SEUL
```

Un assistant attend vos questions. Un **workflow** agit automatiquement.

---

<!-- ============================================================ -->
<!-- PAUSE (5 min)                                                -->
<!-- ============================================================ -->

### Slide 36 — Pause

## Pause rapide -- 5 minutes

---

<!-- ============================================================ -->
<!-- BLOC 3 — AGENTS IA AUTONOMES ET WORKFLOWS (1h15)             -->
<!-- ============================================================ -->

## BLOC 3 — AGENTS IA AUTONOMES ET WORKFLOWS (1h15)

---

### Slide 37 — Introduction Bloc 3

# Agents IA et Workflows
## Quand l'IA agit sans attendre vos instructions

---

### Slide 38 — Agents IA autonomes : definition

## Qu'est-ce qu'un agent IA ?

```
ASSISTANT CLASSIQUE                    AGENT IA AUTONOME
(ce que vous connaissez)               (la prochaine etape)

+------------------+                   +------------------+
| Vous posez       |                   | Vous donnez      |
| UNE question     |                   | UN OBJECTIF      |
+--------+---------+                   +--------+---------+
         |                                      |
         v                                      v
+------------------+                   +------------------+
| Le LLM repond    |                   | L'agent PLANIFIE |
| a cette question |                   | les etapes       |
+------------------+                   +--------+---------+
                                                |
                                                v
                                       +------------------+
                                       | L'agent EXECUTE  |
                                       | chaque etape     |
                                       +--------+---------+
                                                |
                                                v
                                       +------------------+
                                       | L'agent VERIFIE  |
                                       | et AJUSTE        |
                                       +------------------+
```

Un agent IA peut **decomposer un objectif, executer des actions, utiliser des outils** et s'adapter en cours de route.

---

### Slide 39 — Exemples d'agents IA

## Agents IA : exemples concrets

| Agent | Ce qu'il fait | Outils utilises |
|-------|---------------|-----------------|
| **Agent de recherche** | "Trouve les 5 derniers appels d'offres publics dans notre secteur" | Navigation web, extraction, synthese |
| **Agent de support** | "Reponds aux tickets clients de niveau 1, escalade le reste" | Base de connaissances, email, CRM |
| **Agent de veille** | "Surveille les actualites de nos concurrents chaque jour" | Web scraping, analyse, notification |
| **Agent de code** | "Corrige ce bug et cree la pull request" | IDE, Git, tests automatiques |
| **Agent de donnees** | "Analyse nos ventes et genere le rapport mensuel" | SQL, Excel, graphiques |

---

### Slide 40 — Limites actuelles des agents

## Agents IA : les limites a connaitre (2025)

```
+-------------------------------------------------------------------+
|                  LIMITES ACTUELLES                                  |
|                                                                   |
|  [!] FIABILITE        : L'agent peut se tromper a chaque etape    |
|                         Les erreurs s'accumulent sur 10 etapes    |
|                                                                   |
|  [!] CONTROLE         : Difficile de predire exactement ce que    |
|                         l'agent va faire                          |
|                                                                   |
|  [!] COUT             : Un agent qui navigue sur le web pendant   |
|                         30 minutes coute cher en tokens           |
|                                                                   |
|  [!] SECURITE         : Donner des acces (email, CRM, base de    |
|                         donnees) a un agent comporte des risques  |
|                                                                   |
|  [!] HALLUCINATIONS   : Un agent qui hallucine ET agit peut       |
|                         causer des degats reels                   |
+-------------------------------------------------------------------+
```

**Regle d'or** : En 2025, gardez un humain dans la boucle pour valider les actions critiques.

---

### Slide 41 — Des agents aux workflows

## La solution pragmatique : les workflows IA

Plutot que de laisser un agent improviser, on **definit le chemin a l'avance** :

```
AGENT AUTONOME                     WORKFLOW STRUCTURE
(improvise)                        (chemin predefini)

  Objectif                           Declencheur
     |                                   |
     v                                   v
  L'agent                           Etape 1 (definie)
  decide seul                            |
  quoi faire                             v
     |                               Etape 2 (definie)
     ?                                   |
  (imprevisible)                         v
                                     Condition (si/sinon)
                                        / \
                                       v   v
                                    Etape  Etape
                                    3a     3b
                                       \   /
                                        v v
                                     Sortie (definie)
```

Un workflow = une **sequence d'etapes automatisees** ou l'IA intervient a des points precis.

---

### Slide 42 — Anatomie d'un workflow IA

## Les briques d'un workflow

```
+-------------------------------------------------------------------+
|                     WORKFLOW IA                                     |
|                                                                   |
|  1. DECLENCHEUR         Qu'est-ce qui demarre le workflow ?       |
|     (Trigger)           - Un email arrive                         |
|                         - Un formulaire est soumis                |
|                         - Un horaire est atteint (ex: chaque lundi)|
|                         - Un fichier est ajoute dans un dossier   |
|                                                                   |
|  2. ACTIONS             Que fait chaque etape ?                   |
|     (Steps)             - Lire un email / document                |
|                         - Appeler un LLM pour analyser / resumer  |
|                         - Mettre a jour un tableur / CRM          |
|                         - Envoyer un message (email, Slack, Teams)|
|                                                                   |
|  3. CONDITIONS          Quand bifurquer ?                         |
|     (Filters/Routers)   - Si le sentiment est negatif -> escalade |
|                         - Si le montant > 10K -> approbation      |
|                         - Si la langue = anglais -> traduction     |
|                                                                   |
|  4. SORTIE              Quel est le resultat final ?              |
|     (Output)            - Email envoye                            |
|                         - Ligne ajoutee dans un tableur           |
|                         - Notification envoyee                    |
+-------------------------------------------------------------------+
```

---

### Slide 43 — Exemple de workflow : traitement d'emails

## Exemple concret : tri automatique des emails clients

```
DECLENCHEUR : Un email arrive dans support@entreprise.com
         |
         v
ACTION 1 : Le LLM analyse l'email
         - Categorie : question / reclamation / demande devis / spam
         - Urgence : haute / moyenne / basse
         - Langue : FR / EN / autre
         |
         v
CONDITION : Quelle categorie ?
         |
    +----+----+----+-----------+
    |         |         |      |
    v         v         v      v
 Question   Reclam.   Devis   Spam
    |         |         |      |
    v         v         v      v
 ACTION 2a  ACTION 2b ACTION 2c  Archiver
 LLM redige Escalade  Transfert
 reponse    equipe +  au service
 auto       notif     commercial
 depuis FAQ urgent
    |         |         |
    v         v         v
 SORTIE :   SORTIE :   SORTIE :
 Email de   Ticket     Email au
 reponse    prioritaire commercial
 envoye     cree       avec brief
```

---

### Slide 44 — Workflow manuel vs automatise

## La difference cle : qui appuie sur les boutons ?

| Aspect | Workflow MANUEL | Workflow AUTOMATISE |
|--------|----------------|---------------------|
| **Declencheur** | Vous decidez quand commencer | Se declenche tout seul |
| **Etapes** | Vous copiez-collez entre outils | Les outils se parlent directement |
| **LLM** | Vous collez dans ChatGPT | Le LLM est appele par API |
| **Frequence** | Quand vous y pensez | 24h/24, 7j/7 |
| **Erreur humaine** | Possible (oubli, copier-coller) | Eliminee (meme process chaque fois) |
| **Exemple** | Chaine de prompts (Session 4) | Workflow Make/Zapier |

**Vos chaines de prompts de la Session 4** etaient des workflows manuels !
L'etape suivante : les automatiser.

---

### Slide 45 — Panorama des plateformes

## Les plateformes de workflow IA

```
+-------------------------------------------------------------------+
|                                                                   |
|   SANS CODE (No-code / Low-code)           AVEC CODE              |
|                                                                   |
|   +--------+  +--------+  +--------+      +-----------+          |
|   |  Make  |  | Zapier |  | Power  |      |   n8n     |          |
|   | (ex-   |  |        |  | Auto-  |      | (open-    |          |
|   | Integro|  |        |  | mate   |      |  source)  |          |
|   | mat)   |  |        |  |        |      |           |          |
|   +--------+  +--------+  +--------+      +-----------+          |
|                                                                   |
|   Interface         Le plus         Ecosysteme    Gratuit,        |
|   visuelle,         simple,         Microsoft,    auto-heberge,   |
|   tres flexible     enorme          integre a     controle total  |
|                     catalogue       Office 365                    |
|                     d'apps                                        |
+-------------------------------------------------------------------+
```

---

### Slide 46 — Tableau comparatif des plateformes

## Comparatif detaille

| Critere | Make | Zapier | n8n | Power Automate |
|---------|------|--------|-----|----------------|
| **Difficulte** | Moyenne | Facile | Avancee | Facile-Moyenne |
| **Prix** | Gratuit (limites) puis ~9 EUR/mois | Gratuit (limites) puis ~19$/mois | Gratuit (self-hosted) ou cloud | Inclus M365 ou ~15$/mois |
| **Integration IA** | Module OpenAI, Claude | Module AI by Zapier | Nodes LLM multiples | Azure OpenAI, Copilot |
| **Nb connecteurs** | 1800+ | 7000+ | 400+ (extensible) | 1000+ (ecosysteme MS) |
| **Interface** | Visuelle (noeuds) | Liste d'etapes | Visuelle (noeuds) | Liste + visuelle |
| **Ideal pour** | Workflows complexes visuels | Automatisations simples rapides | Controle total, donnees sensibles | Entreprises sur Microsoft |
| **Courbe d'apprentissage** | 1-2 jours | Quelques heures | 3-5 jours | 1-2 jours |

**Conseil** : commencez par **Zapier** si vous debutez, passez a **Make** pour plus de controle.

---

### Slide 47 — Exemples de workflows par metier

## Idees de workflows par metier

| Metier | Workflow | Declencheur | Actions IA |
|--------|----------|-------------|------------|
| **RH** | Tri des candidatures | Email avec CV recu | LLM analyse le CV, compare avec la fiche de poste, note /10 |
| **Commercial** | Qualification de leads | Formulaire web soumis | LLM enrichit le lead, score de qualification, email de suivi |
| **Marketing** | Veille concurrentielle | Chaque lundi a 8h | Scrape actualites concurrents, LLM resume, email de synthese |
| **Comptabilite** | Traitement de factures | Facture recue par email | OCR + LLM extrait les donnees, pre-remplit l'ecriture comptable |
| **Support** | Reponse automatique N1 | Ticket client cree | LLM classe et redige une reponse, humain valide avant envoi |
| **Communication** | Repurposing de contenu | Article de blog publie | LLM genere post LinkedIn + tweet + newsletter a partir de l'article |

---

### Slide 48 — Exercice : concevoir un workflow sur papier

## Exercice (20 min) : Concevez votre workflow

**Objectif** : Dessiner un workflow IA adapte a votre metier, sur papier.

**Template a remplir :**

```
NOM DU WORKFLOW : ________________________________________

PROBLEME RESOLU : ________________________________________

DECLENCHEUR : ____________________________________________
   (Qu'est-ce qui demarre le workflow ?)

ETAPE 1 : ________________________________________________
   Action : _______________________________________________
   Outil  : _______________________________________________

ETAPE 2 (IA) : ___________________________________________
   Prompt au LLM : _______________________________________
   Sortie attendue : _____________________________________

CONDITION : Si _____________ alors Etape 3a, sinon Etape 3b

ETAPE 3a : ________________________________________________

ETAPE 3b : ________________________________________________

SORTIE FINALE : ___________________________________________

PLATEFORME ENVISAGEE : [ ] Make  [ ] Zapier  [ ] n8n  [ ] Power Automate
```

> **Fiche atelier** : voir FICHE-ATELIER-05B pour le template complet

---

### Slide 49 — Evaluation pratique : fin du Module 1

## Evaluation pratique — Module 1

**Objectif** : Demontrer votre maitrise des competences acquises durant les 5 sessions.

**L'evaluation combine :**

```
+-------------------------------------------------------------------+
|                    EVALUATION MODULE 1                              |
|                                                                   |
|  PARTIE 1 : Prompting (individuel, 15 min)                       |
|  - Redigez un prompt CREA complet pour un cas de votre metier     |
|  - Utilisez au moins 2 techniques avancees (few-shot, CoT...)    |
|  - Structurez la sortie dans un format professionnel              |
|                                                                   |
|  PARTIE 2 : Assistant ou Workflow (individuel, 15 min)            |
|  - Presentez l'assistant que vous avez cree pendant l'atelier     |
|  - OU presentez le workflow que vous avez concu                   |
|  - Expliquez le probleme resolu et les choix techniques           |
|                                                                   |
|  PARTIE 3 : QCM de fin de module (10 min)                        |
|  - 15 questions couvrant les 5 sessions                           |
|  - Permet de mesurer votre progression vs le QCM initial          |
+-------------------------------------------------------------------+
```

---

### Slide 50 — Synthese de la session

## Ce que vous avez appris aujourd'hui

```
+-------------------------------------------------------------------+
|                   SESSION 5 — BILAN                                |
|                                                                   |
|  [x] RAG : connecter l'IA a vos documents internes               |
|      -> Le LLM ne connait pas vos donnees, le RAG comble ce vide |
|      -> Outils : ChatGPT Upload, Claude Projects, NotebookLM     |
|                                                                   |
|  [x] ASSISTANTS PERSONNALISES : configurer une fois, utiliser     |
|      toujours                                                     |
|      -> GPTs, Claude Projects, Gemini Gems                        |
|      -> Documents + Instructions + Outils = Assistant dedie       |
|                                                                   |
|  [x] AGENTS et WORKFLOWS : automatiser les taches repetitives    |
|      -> Agents autonomes : prometteurs mais encore limites        |
|      -> Workflows : la solution pragmatique et fiable             |
|      -> Plateformes : Make, Zapier, n8n, Power Automate          |
+-------------------------------------------------------------------+
```

---

### Slide 51 — Bilan du Module 1

## Module 1 : le chemin parcouru

```
Session 1          Session 2          Session 3
Fondamentaux IA    Les LLM            CREA + Prompting
                                      de base
     |                  |                  |
     v                  v                  v
"L'IA, c'est      "GPT, Claude,      "Je sais ecrire
 quoi au juste ?"  Gemini : lequel     un bon prompt"
                   choisir ?"

Session 4                    Session 5
Prompting avance             RAG + Assistants + Workflows
     |                            |
     v                            v
"Je maitrise le             "Je connecte l'IA a mes
 few-shot, le CoT            donnees, je cree des
 et les chaines"              assistants et je concois
                              des workflows"
```

Vous etes passe de **"c'est quoi l'IA ?"** a **"je concois des systemes IA pour mon metier"**.

---

### Slide 52 — La suite : Module 2

## Et apres ? Module 2 — Cas d'usage metier

Le Module 2 met en pratique tout ce que vous avez appris :

- **Ateliers par metier** : projets concrets adaptes a votre poste
- **Automatisations reelles** : implementation de workflows fonctionnels
- **Travail en equipe** : collaboration sur des cas transversaux
- **Evaluation finale** : projet de A a Z avec soutenance

> Bravo pour ce Module 1 ! Vous avez desormais les bases solides pour transformer votre quotidien professionnel avec l'IA.

---

<!-- FIN DES SLIDES -->

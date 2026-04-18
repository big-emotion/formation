# SESSION 2 — Les LLM : Comprendre et Choisir
## Jour 1 — Apres-midi (3h30)
### Formation IA pour le Tertiaire

---

<!-- ============================================================ -->
<!-- BLOC 1 — COMMENT FONCTIONNE UN LLM (45 min)                  -->
<!-- ============================================================ -->

---

# BLOC 1
## Comment fonctionne un LLM
### Comprendre la mecanique sans devenir ingenieur

> Duree : 45 minutes

---

## Slide 1 — Un LLM, c'est quoi en une phrase ?

**LLM = Large Language Model = Grand Modele de Langage**

Un programme informatique entraine sur des milliards de textes
qui a appris a **predire le mot suivant** dans une phrase.

```
C'est tout.
Pas de conscience.
Pas de comprehension.
Juste une prediction statistique... extremement sophistiquee.
```

> Analogie : Un LLM, c'est comme un collegue qui a lu
> TOUTE la bibliotheque de l'entreprise et qui peut
> completer n'importe quelle phrase de facon coherente.

---

## Slide 2 — Le principe de prediction du mot suivant

Comment le LLM genere une reponse :

```
Vous tapez : "Bonjour, je souhaite reporter notre..."

Le LLM calcule :
  → "reunion"      (72% de probabilite)
  → "rendez-vous"  (18% de probabilite)
  → "entretien"    (6% de probabilite)
  → "projet"       (2% de probabilite)
  → autres         (2% de probabilite)

Il choisit "reunion", puis recommence pour le mot suivant.
Et ainsi de suite, mot apres mot.
```

Le texte est genere **un mot a la fois**, pas d'un seul bloc.

---

## Slide 3 — L'analogie de l'auto-completion

Vous connaissez deja ce principe !

```
╔══════════════════════════════════════════════╗
║  Votre telephone :                           ║
║  "On se retrouve a quelle h..."              ║
║    → [heure] [hotel] [hauteur]               ║
║                                              ║
║  Un LLM :                                    ║
║  "Redigez un email professionnel pour..."    ║
║    → une phrase entiere, coherente,          ║
║      adaptee au contexte, au ton,            ║
║      et a votre intention                    ║
╚══════════════════════════════════════════════╝
```

| Auto-completion telephone | LLM                          |
|---------------------------|------------------------------|
| 1-3 mots suggeres         | Textes complets de plusieurs pages |
| Basee sur vos habitudes   | Basee sur des milliards de textes  |
| Contexte limite           | Comprend la consigne entiere       |
| Pas de personnalisation   | Adapte le ton, le style, le format |

---

## Slide 4 — La tokenisation : comment le texte est decoupe

Avant de "lire" votre texte, le LLM le decoupe en **tokens**.

Un token = un morceau de mot (environ 3/4 d'un mot en francais).

```
Phrase : "Le directeur commercial a valide le budget"

Decoupage en tokens :
 [Le] [direct] [eur] [commer] [cial] [a] [valid] [e] [le] [budget]

 8 mots → 10 tokens
```

**Pourquoi c'est important pour vous ?**
- Les LLM facturent souvent **au nombre de tokens**
- La limite de texte que vous pouvez envoyer = un nombre max de tokens
- Un texte en francais consomme ~25% de tokens en plus qu'en anglais

---

## Slide 5 — Demonstration : visualiser les tokens

**Exercice en direct** — Allez sur : `platform.openai.com/tokenizer`

Testez ces phrases et comptez les tokens :

| Phrase                                    | Tokens (approx.) |
|-------------------------------------------|-------------------|
| "Bonjour"                                 | 2                 |
| "Hello"                                   | 1                 |
| "Pourriez-vous rediger un compte-rendu ?" | ~12               |
| "Can you write a summary?"                | 6                 |

**A retenir :**
- Le francais "coute" plus cher en tokens que l'anglais
- Les mots rares ou techniques = plus de tokens
- Les chiffres et codes sont decoupes differemment

---

## Slide 6 — La fenetre de contexte : la memoire du modele

La **fenetre de contexte** = tout ce que le modele peut "garder en tete"
pendant une conversation.

```
╔═══════════════════════════════════════════════════╗
║            FENETRE DE CONTEXTE                    ║
║                                                   ║
║  ┌─────────────────────────────────────────────┐  ║
║  │  Votre consigne initiale                    │  ║
║  │  + Votre message 1                          │  ║
║  │  + Reponse du LLM 1                         │  ║
║  │  + Votre message 2                          │  ║
║  │  + Reponse du LLM 2                         │  ║
║  │  + ...                                      │  ║
║  │  + Votre dernier message                    │  ║
║  └─────────────────────────────────────────────┘  ║
║                                                   ║
║  Quand c'est plein → le debut est "oublie"        ║
╚═══════════════════════════════════════════════════╝
```

| Modele           | Fenetre de contexte   | Equivalent texte       |
|------------------|-----------------------|------------------------|
| GPT-4o           | 128 000 tokens        | ~200 pages             |
| Claude 3.5       | 200 000 tokens        | ~300 pages             |
| Gemini 1.5 Pro   | 1 000 000 tokens      | ~1 500 pages           |

---

## Slide 7 — Fenetre de contexte : consequences pratiques

**Ce que ca change pour vous au quotidien :**

1. **Les longues conversations "s'essoufflent"**
   - Le modele oublie le debut → commencez une nouvelle conversation

2. **Collez vos documents dans le chat**
   - Avec une grande fenetre, vous pouvez analyser un rapport entier

3. **Repetez les consignes importantes**
   - Si la conversation est longue, re-precisez le contexte

> Analogie : C'est comme une reunion sans compte-rendu.
> Au bout de 3h, personne ne se souvient de ce qui a ete dit
> dans les 10 premieres minutes.

---

## Slide 8 — Temperature et creativite

La **temperature** = un reglage qui controle le niveau de "creativite".

```
Temperature BASSE (0.0 - 0.3)          Temperature HAUTE (0.7 - 1.0)
================================        ================================
→ Reponses previsibles                 → Reponses variees
→ Factuelles, repetables               → Creatives, surprenantes
→ Ideales pour :                        → Ideales pour :
  - Analyses de donnees                   - Brainstorming
  - Syntheses factuelles                  - Redaction creative
  - Extraction d'info                     - Slogans, idees nouvelles
  - Reponses juridiques                   - Reformulations
```

**En pratique :** Vous ne reglez pas directement la temperature,
mais vous pouvez **influencer le comportement** via vos instructions :
- "Sois precis et factuel" → comportement basse temperature
- "Propose-moi des idees originales" → comportement haute temperature

---

## Slide 9 — Pourquoi les reponses varient ?

Vous posez la **meme question** deux fois et obtenez des **reponses differentes**.

C'est normal ! Voici pourquoi :

```
┌───────────────────────────────────────────┐
│         MEME QUESTION POSEE               │
│                                           │
│   Facteur 1 : Temperature                 │
│   → Part d'aleatoire dans le choix du mot │
│                                           │
│   Facteur 2 : Contexte de conversation    │
│   → Les messages precedents influencent   │
│                                           │
│   Facteur 3 : Mises a jour du modele      │
│   → Les modeles evoluent dans le temps    │
│                                           │
│         = REPONSES DIFFERENTES            │
└───────────────────────────────────────────┘
```

**Conseil pratique :** Si une reponse vous plait, **sauvegardez-la** !
Vous ne l'obtiendrez peut-etre plus exactement a l'identique.

---

## Slide 10 — Ce que le LLM ne fait PAS

**ATTENTION — Idees recues a corriger :**

| On croit que le LLM...         | En realite...                              |
|--------------------------------|--------------------------------------------|
| "comprend" notre question      | Il repere des patterns statistiques         |
| "sait" des choses              | Il a memorise des associations de mots      |
| "pense" a sa reponse           | Il calcule des probabilites mot apres mot   |
| "cherche" sur Internet         | Il ne consulte que son entrainement*        |
| "se souvient" de nous          | Chaque conversation repart de zero**        |

*Sauf s'il a un acces web active (ex : ChatGPT avec navigation)
**Sauf fonctionnalites de memoire recemment ajoutees

---

## Slide 11 — Les hallucinations : le risque principal

Un LLM peut generer des informations **totalement fausses**
avec un aplomb parfait. On appelle cela des **hallucinations**.

```
╔══════════════════════════════════════════════════╗
║  EXEMPLE D'HALLUCINATION                         ║
║                                                  ║
║  Question : "Cite-moi l'arret de la Cour de     ║
║  cassation du 12 mars 2019 sur le teletravail"   ║
║                                                  ║
║  Reponse du LLM : "L'arret n° 18-21.345 de la   ║
║  chambre sociale du 12 mars 2019 stipule que..."  ║
║                                                  ║
║  → Cet arret N'EXISTE PAS.                       ║
║  → Mais la reference a l'air parfaitement reelle ║
╚══════════════════════════════════════════════════╝
```

**Regle d'or : TOUJOURS verifier les faits, les chiffres,
les references juridiques et les citations.**

---

## Slide 12 — Quiz rapide Bloc 1

Testez vos connaissances :

1. **Un LLM genere du texte en :**
   - a) Cherchant sur Internet
   - b) Predisant le mot suivant
   - c) Copiant des textes existants

2. **La fenetre de contexte, c'est :**
   - a) La taille de l'ecran
   - b) La quantite de texte que le modele peut traiter
   - c) Le nombre de conversations possibles

3. **Une hallucination, c'est :**
   - a) Un bug du logiciel
   - b) Une reponse inventee mais convaincante
   - c) Un probleme de connexion

> Reponses : 1-b, 2-b, 3-b

---

<!-- ============================================================ -->
<!-- BLOC 2 — PANORAMA DES LLM (45 min)                           -->
<!-- ============================================================ -->

---

# BLOC 2
## Panorama des LLM
### Connaitre les outils pour mieux choisir

> Duree : 45 minutes

---

## Slide 13 — Le marche des LLM en 2024-2025

```
┌─────────────────────────────────────────────────────┐
│              LES 4 GRANDS ACTEURS                   │
│                                                     │
│   ┌──────────┐  ┌──────────┐  ┌──────────┐         │
│   │  OpenAI  │  │Anthropic │  │  Google  │         │
│   │ ChatGPT  │  │  Claude  │  │  Gemini  │         │
│   │   (US)   │  │   (US)   │  │   (US)   │         │
│   └──────────┘  └──────────┘  └──────────┘         │
│                                                     │
│              ┌──────────────┐                       │
│              │  Mistral AI  │                       │
│              │   Le Chat    │                       │
│              │   (France)   │                       │
│              └──────────────┘                       │
│                                                     │
│   + Meta (Llama), xAI (Grok), Cohere, etc.         │
└─────────────────────────────────────────────────────┘
```

Nous allons detailler chacun pour que vous puissiez **choisir
en connaissance de cause**.

---

## Slide 14 — ChatGPT (OpenAI)

**Le plus connu — Le couteau suisse de l'IA**

| Caracteristique         | Detail                                    |
|-------------------------|-------------------------------------------|
| Editeur                 | OpenAI (San Francisco, USA)               |
| Modeles principaux      | GPT-4o, GPT-4o mini                       |
| Acces gratuit           | Oui (GPT-4o mini, limite)                 |
| Acces payant            | ChatGPT Plus : 20$/mois                   |
| Fenetre de contexte     | 128 000 tokens                             |
| Langues                 | 90+ langues, excellent en francais        |

**URL :** `chat.openai.com`

---

## Slide 15 — ChatGPT : forces et cas d'usage

**Forces principales :**
- Polyvalence : bon dans presque tout
- Ecosysteme riche : plugins, GPTs personnalises, DALL-E (images)
- Navigation web integree (version payante)
- Analyse de fichiers (PDF, Excel, images)
- Le plus grande base d'utilisateurs = beaucoup de tutoriels disponibles

**Ideal pour :**
- Redaction d'emails et courriers
- Brainstorming et ideation
- Analyse et synthese de documents
- Creation de contenu marketing
- Assistance a la programmation

**Limites :**
- Donnees envoyees aux USA (attention RGPD)
- Version gratuite bridee aux heures de pointe
- Parfois verbeux dans ses reponses

---

## Slide 16 — Claude (Anthropic)

**L'analyste rigoureux — Specialiste des longs documents**

| Caracteristique         | Detail                                    |
|-------------------------|-------------------------------------------|
| Editeur                 | Anthropic (San Francisco, USA)            |
| Modeles principaux      | Claude 3.5 Sonnet, Claude 3 Opus          |
| Acces gratuit           | Oui (Claude 3.5 Sonnet, limite)           |
| Acces payant            | Claude Pro : 20$/mois                     |
| Fenetre de contexte     | 200 000 tokens                             |
| Langues                 | Multilingue, tres bon en francais         |

**URL :** `claude.ai`

---

## Slide 17 — Claude : forces et cas d'usage

**Forces principales :**
- Fenetre de contexte geante : analysez des documents de 300+ pages
- Reponses nuancees et structurees
- Moins d'hallucinations que la concurrence (approche "Constitutional AI")
- Excellent pour l'analyse de textes longs et complexes
- Ton naturel et professionnel

**Ideal pour :**
- Analyse de contrats et documents juridiques
- Synthese de rapports longs
- Redaction structuree et nuancee
- Relecture et amelioration de textes
- Travail sur des donnees sensibles (engagement ethique fort)

**Limites :**
- Pas de generation d'images
- Pas de navigation web native
- Moins de plugins/extensions que ChatGPT

---

## Slide 18 — Gemini (Google)

**L'ecosysteme Google — Integration native**

| Caracteristique         | Detail                                    |
|-------------------------|-------------------------------------------|
| Editeur                 | Google DeepMind (USA)                     |
| Modeles principaux      | Gemini Pro, Gemini Advanced               |
| Acces gratuit           | Oui (Gemini Pro)                          |
| Acces payant            | Google One AI Premium : 21.99EUR/mois     |
| Fenetre de contexte     | 1 000 000 tokens (Gemini 1.5 Pro)         |
| Langues                 | 40+ langues                               |

**URL :** `gemini.google.com`

---

## Slide 19 — Gemini : forces et cas d'usage

**Forces principales :**
- Integration Google Workspace (Gmail, Docs, Sheets, Slides)
- Multimodal natif : texte, images, audio, video
- Fenetre de contexte gigantesque (1M tokens)
- Acces en temps reel a la recherche Google
- Deja integre si vous avez un compte Google

**Ideal pour :**
- Utilisateurs deja dans l'ecosysteme Google
- Analyse de documents multimedia (images, videos)
- Recherche d'informations actualisees
- Integration dans les workflows Google Workspace
- Synthese de contenus tres longs

**Limites :**
- Parfois moins precis que GPT-4o ou Claude sur les taches complexes
- Interface qui evolue tres vite (peut destabiliser)
- Disponibilite variable selon les pays

---

## Slide 20 — Mistral (Mistral AI)

**Le champion francais — Souverainete et open-source**

| Caracteristique         | Detail                                    |
|-------------------------|-------------------------------------------|
| Editeur                 | Mistral AI (Paris, France)                |
| Modeles principaux      | Mistral Large, Mistral Small              |
| Acces gratuit           | Oui (Le Chat)                             |
| Acces payant            | Le Chat Pro (offres en evolution)         |
| Fenetre de contexte     | 128 000 tokens                             |
| Langues                 | Multilingue, excellent en francais        |

**URL :** `chat.mistral.ai`

---

## Slide 21 — Mistral : forces et cas d'usage

**Forces principales :**
- Entreprise francaise : conforme RGPD par conception
- Modeles open-source : transparence et personnalisation
- Donnees hebergees en Europe
- Excellent rapport qualite/prix
- Soutenu par l'ecosysteme francais et europeen

**Ideal pour :**
- Entreprises soucieuses de la conformite RGPD
- Secteurs sensibles (sante, finance, juridique)
- Organisations preferant la souverainete numerique
- Developpeurs souhaitant personnaliser le modele
- Usage quotidien generaliste en francais

**Limites :**
- Ecosysteme de plugins moins developpe
- Moins de fonctionnalites avancees (pas encore de generation d'images)
- Communaute plus petite que ChatGPT

---

## Slide 22 — Tableau comparatif synthetique

| Critere              | ChatGPT      | Claude       | Gemini       | Mistral      |
|----------------------|--------------|--------------|--------------|--------------|
| **Prix gratuit**     | Oui (limite) | Oui (limite) | Oui          | Oui          |
| **Prix pro**         | 20$/mois     | 20$/mois     | 21.99EUR/mois| Variable     |
| **Contexte**         | 128K tokens  | 200K tokens  | 1M tokens    | 128K tokens  |
| **Docs longs**       | Bon          | Excellent    | Excellent    | Bon          |
| **Redaction**        | Excellent    | Excellent    | Bon          | Tres bon     |
| **Creativite**       | Excellent    | Tres bon     | Bon          | Bon          |
| **RGPD**             | Attention    | Attention    | Attention    | Conforme     |
| **Images**           | Oui (DALL-E) | Non          | Oui          | Non          |
| **Web en direct**    | Oui (payant) | Non          | Oui          | Oui          |
| **Ecosysteme**       | Tres riche   | En croissance| Google integ.| En croissance|

---

## Slide 23 — Quel outil pour quel besoin ?

```
VOTRE BESOIN                          → OUTIL RECOMMANDE
──────────────────────────────────────────────────────────────
Rediger un email professionnel        → ChatGPT ou Claude
Analyser un contrat de 50 pages       → Claude
Resumer une reunion enregistree       → Gemini
Brainstorming pour une campagne       → ChatGPT
Travailler avec Google Docs/Sheets    → Gemini
Conformite RGPD stricte               → Mistral
Generer des visuels                   → ChatGPT (DALL-E) ou Gemini
Recherche d'actus recentes            → Gemini ou ChatGPT (web)
Analyse de donnees sensibles          → Mistral ou Claude
Usage general quotidien               → Au choix ! Testez les 4
```

**Conseil : ne vous enfermez pas dans un seul outil.**
Les meilleurs utilisateurs savent **choisir le bon outil
pour chaque tache**.

---

## Slide 24 — Et les prix, concretement ?

**Estimation pour un usage professionnel individuel :**

```
┌─────────────────────────────────────────────────────┐
│  GRATUIT (pour commencer et tester)                 │
│  → Suffisant pour 80% des besoins debutants         │
│  → Limites : nombre de messages/heure               │
│                                                     │
│  ~20 EUR/MOIS (pour un usage professionnel regulier)│
│  → Acces aux meilleurs modeles                      │
│  → Plus de messages, plus de fonctionnalites        │
│  → A comparer avec : 1 cafe/jour de travail         │
│                                                     │
│  OFFRES EQUIPE (pour les entreprises)               │
│  → ChatGPT Team : 25$/utilisateur/mois              │
│  → Claude Team : 30$/utilisateur/mois               │
│  → Gemini Business : inclus Google Workspace        │
└─────────────────────────────────────────────────────┘
```

> Les prix evoluent rapidement. Verifiez sur les sites officiels.

---

<!-- ============================================================ -->
<!-- BLOC 3 — PRISE EN MAIN GUIDEE (1h15)                         -->
<!-- ============================================================ -->

---

# BLOC 3
## Prise en main guidee
### Creer ses comptes et comparer les outils

> Duree : 1h15

---

## Slide 25 — Objectif de cette session pratique

Vous allez :

1. **Creer un compte** sur ChatGPT (si pas deja fait)
2. **Creer un compte** sur Claude (si pas deja fait)
3. **Acceder** a Gemini via votre compte Google
4. **Tester la meme question** sur les 3 outils
5. **Comparer** les resultats

```
A la fin de ce bloc, vous aurez :
  ✓ 3 comptes operationnels
  ✓ Une premiere experience sur chaque outil
  ✓ Votre propre avis sur les differences
```

---

## Slide 26 — Etape 1 : Creer un compte ChatGPT

**Procedure pas a pas :**

```
1. Allez sur : chat.openai.com
2. Cliquez sur "Sign up" (S'inscrire)
3. Options :
   - Email + mot de passe
   - Connexion via Google
   - Connexion via Microsoft
4. Verifiez votre email
5. Completez votre profil (prenom suffit)
6. Vous etes sur la page de chat !
```

**Conseils :**
- Utilisez votre email professionnel
- La version gratuite est largement suffisante pour debuter
- Pas besoin de numero de telephone (optionnel)

> Temps estime : 3 minutes

---

## Slide 27 — Etape 2 : Creer un compte Claude

**Procedure pas a pas :**

```
1. Allez sur : claude.ai
2. Cliquez sur "Sign up"
3. Options :
   - Email + mot de passe
   - Connexion via Google
4. Verifiez votre email
5. Acceptez les conditions d'utilisation
6. Vous etes sur la page de chat !
```

**Conseils :**
- Interface epuree, tres simple a prendre en main
- Le bouton "Upload" permet d'envoyer des fichiers directement
- Limite : environ 30 messages par conversation en version gratuite

> Temps estime : 3 minutes

---

## Slide 28 — Etape 3 : Acceder a Gemini

**Procedure pas a pas :**

```
1. Allez sur : gemini.google.com
2. Connectez-vous avec votre compte Google
   (celui que vous utilisez deja pour Gmail)
3. C'est tout ! Pas d'inscription supplementaire.
4. Vous etes sur la page de chat !
```

**Conseils :**
- Si vous avez deja Gmail, vous avez deja acces
- L'icone en forme d'etoile dans Gmail/Docs = Gemini integre
- Gemini peut analyser vos emails et documents Google (si vous l'autorisez)

> Temps estime : 1 minute

---

## Slide 29 — Exercice comparatif 1 : L'email professionnel

**Copiez exactement cette consigne dans ChatGPT, Claude ET Gemini :**

```
Redigez un email professionnel pour reporter une reunion
prevue demain a 14h avec mon equipe de 5 personnes.
Motif : conflit d'agenda avec une reunion client prioritaire.
Proposez 2 creneaux de remplacement la semaine prochaine.
Ton : courtois mais direct.
```

**Ensuite, comparez :**

| Critere a observer     | ChatGPT | Claude | Gemini |
|------------------------|---------|--------|--------|
| Longueur de la reponse |         |        |        |
| Ton adopte             |         |        |        |
| Structure de l'email   |         |        |        |
| Creneaux proposes      |         |        |        |
| Qualite globale (1-5)  |         |        |        |

> Temps : 10 minutes

---

## Slide 30 — Exercice comparatif 2 : La synthese

**Copiez ce texte puis cette consigne dans les 3 outils :**

```
[Collez un article de presse de ~500 mots
que le formateur aura prepare a l'avance]

Consigne : Faites une synthese de ce texte en 5 points cles,
avec pour chaque point une phrase explicative.
Format : liste numerotee.
Public cible : directeur general non specialiste du sujet.
```

**Comparez :**

| Critere a observer         | ChatGPT | Claude | Gemini |
|----------------------------|---------|--------|--------|
| Fidelite au texte original |         |        |        |
| Clarte de la synthese      |         |        |        |
| Pertinence des 5 points    |         |        |        |
| Adaptation au public cible |         |        |        |
| Qualite globale (1-5)      |         |        |        |

> Temps : 15 minutes

---

## Slide 31 — Exercice comparatif 3 : Le tableau

**Copiez cette consigne dans les 3 outils :**

```
Creez un tableau comparatif des 4 types de conges
en France (conges payes, RTT, conge maladie, conge parental)
avec ces colonnes :
- Type de conge
- Duree legale
- Remuneration
- Conditions
- A savoir

Format : tableau structure. Informations a jour.
```

**Comparez :**

| Critere a observer         | ChatGPT | Claude | Gemini |
|----------------------------|---------|--------|--------|
| Exactitude des informations|         |        |        |
| Lisibilite du tableau      |         |        |        |
| Completude                 |         |        |        |
| Mise en forme              |         |        |        |
| Qualite globale (1-5)      |         |        |        |

> Temps : 15 minutes

---

## Slide 32 — Debrief collectif des exercices

**Questions a discuter ensemble :**

1. Quel outil avez-vous prefere ? Pourquoi ?
2. Avez-vous remarque des differences significatives ?
3. Un outil a-t-il fait des erreurs factuelles ?
4. Lequel vous semble le plus adapte a votre metier ?

**Observations frequentes :**
- ChatGPT : souvent plus long et detaille
- Claude : souvent mieux structure et plus nuance
- Gemini : parfois plus concis, acces web utile

> Il n'y a pas de "meilleur" outil universel.
> Le meilleur outil est celui qui repond le mieux
> a VOTRE besoin specifique.

---

<!-- ============================================================ -->
<!-- BLOC 4 — PREMIERS PROMPTS ET BONNES PRATIQUES (30 min)        -->
<!-- ============================================================ -->

---

# BLOC 4
## Premiers prompts et bonnes pratiques
### Eviter les pieges, adopter les bons reflexes

> Duree : 30 minutes

---

## Slide 33 — Les 5 erreurs du debutant

```
╔══════════════════════════════════════════════════════╗
║          LES 5 ERREURS A EVITER                     ║
║                                                      ║
║  1. PROMPTS TROP VAGUES                              ║
║     "Fais-moi un truc sur le marketing"              ║
║                                                      ║
║  2. PAS DE CONTEXTE                                  ║
║     "Ecris un email" (a qui ? pourquoi ? quel ton ?) ║
║                                                      ║
║  3. ATTENTE DE PERFECTION AU PREMIER ESSAI           ║
║     Abandonner apres une premiere reponse moyenne     ║
║                                                      ║
║  4. SAISIE DE DONNEES SENSIBLES                      ║
║     Coller des fiches de paie ou mots de passe       ║
║                                                      ║
║  5. ACCEPTER SANS VERIFIER                           ║
║     Copier-coller la reponse sans relire              ║
╚══════════════════════════════════════════════════════╝
```

---

## Slide 34 — Erreur 1 : Prompts trop vagues

**Mauvais prompt :**
```
"Fais-moi un truc sur le marketing"
```

**Bon prompt :**
```
"Redige un plan d'action marketing en 5 etapes
pour lancer un nouveau service de conseil RH
aupres des PME de 50 a 200 salaries.
Budget : 10 000 EUR. Duree : 3 mois.
Format : tableau avec etapes, actions, budget, KPIs."
```

> Plus votre demande est precise, plus la reponse sera utile.
> Pensez "brief a un prestataire" : vous ne diriez pas
> "faites-moi un truc", vous preciseriez le cahier des charges.

---

## Slide 35 — Erreur 4 : Les donnees sensibles

**NE JAMAIS saisir dans un LLM :**

```
╔══════════════════════════════════════════════╗
║  ✗ Noms + donnees personnelles de salaries  ║
║  ✗ Numeros de securite sociale               ║
║  ✗ Fiches de paie                            ║
║  ✗ Donnees medicales                         ║
║  ✗ Mots de passe et codes d'acces            ║
║  ✗ Donnees clients nominatives               ║
║  ✗ Informations financieres confidentielles  ║
║  ✗ Strategies internes secretes              ║
╚══════════════════════════════════════════════╝
```

**Pourquoi ?**
- Vos donnees peuvent etre utilisees pour entrainer le modele*
- Aucun LLM ne garantit la confidentialite absolue
- Risque RGPD reel pour les donnees personnelles

*Sauf offres Enterprise specifiques avec garanties contractuelles

**Astuce :** Anonymisez ! Remplacez "Jean Dupont" par "Salarie A".

---

## Slide 36 — Les 5 reflexes a adopter

```
╔══════════════════════════════════════════════════════╗
║          LES 5 BONS REFLEXES                         ║
║                                                      ║
║  1. DONNER DU CONTEXTE                               ║
║     Qui vous etes, pour qui, pourquoi                ║
║                                                      ║
║  2. ETRE SPECIFIQUE                                  ║
║     Format, longueur, ton, public cible              ║
║                                                      ║
║  3. ITERER                                           ║
║     Affiner la reponse en plusieurs echanges         ║
║                                                      ║
║  4. VERIFIER LES FAITS                               ║
║     Chiffres, dates, references = a verifier         ║
║                                                      ║
║  5. SAUVEGARDER LES PROMPTS EFFICACES                ║
║     Creer sa bibliotheque de prompts                 ║
╚══════════════════════════════════════════════════════╝
```

---

## Slide 37 — Reflexe 3 : Iterer (le plus important)

**Le LLM est un assistant : dialoguez avec lui !**

```
ESSAI 1 : "Redige un email pour reporter une reunion"
  → Resultat : correct mais trop formel

ITERATION 2 : "C'est bien mais le ton est trop formel.
  Rends-le plus decontracte, on est une petite equipe."
  → Resultat : mieux, mais trop long

ITERATION 3 : "Parfait pour le ton. Raccourcis-le de moitie."
  → Resultat : exactement ce qu'il faut !
```

```
      ESSAI 1          ITERATION 2        ITERATION 3
    ┌─────────┐       ┌─────────┐        ┌─────────┐
    │ Correct │  →→→  │  Mieux  │  →→→   │ Parfait │
    │ mais... │       │ mais... │        │   !!!   │
    └─────────┘       └─────────┘        └─────────┘
```

> En moyenne, il faut **2 a 3 iterations** pour obtenir
> un resultat vraiment satisfaisant. C'est normal !

---

## Slide 38 — Reflexe 5 : Sauvegarder ses prompts

**Creez votre "boite a outils" personnelle :**

```
MON REPERTOIRE DE PROMPTS
─────────────────────────
📁 Emails
   ├── Email de relance client.txt
   ├── Email de report reunion.txt
   └── Email de bienvenue nouveau collaborateur.txt

📁 Syntheses
   ├── Synthese de reunion.txt
   ├── Synthese de rapport mensuel.txt
   └── Synthese d'article pour la direction.txt

📁 Analyses
   ├── Analyse de CV.txt
   ├── Analyse de donnees commerciales.txt
   └── Comparatif fournisseurs.txt
```

**Ou les stocker ?**
- Un simple fichier texte ou document Word
- Un dossier partage d'equipe
- Les "prompts favoris" dans ChatGPT/Claude
- Un outil dedie (Notion, Google Keep, etc.)

---

## Slide 39 — La formule du bon prompt

**Structure recommandee pour debuter :**

```
┌─────────────────────────────────────────────────┐
│                                                 │
│  ROLE    : "Tu es un [role/expert en...]"       │
│                                                 │
│  CONTEXTE : "Je travaille dans [contexte]       │
│              et j'ai besoin de [objectif]"      │
│                                                 │
│  TACHE   : "Redige / Analyse / Compare /        │
│             Propose / Resume [quoi exactement]" │
│                                                 │
│  FORMAT  : "Sous forme de [tableau / liste /    │
│             email / plan d'action]"             │
│                                                 │
│  CONTRAINTES : "En [X lignes / ton formel /     │
│                  pour [public cible]]"          │
│                                                 │
└─────────────────────────────────────────────────┘
```

**Exemple complet :**
> "Tu es un responsable RH. Je dois rediger une annonce
> pour un poste de comptable en CDI dans une PME de 80 salaries.
> Redige l'annonce complete avec : intitule, missions (5 max),
> profil recherche, avantages. Ton professionnel mais attractif.
> Maximum 300 mots."

---

## Slide 40 — Synthese de la session 2

**Ce que vous avez appris aujourd'hui :**

```
┌─────────────────────────────────────────────────────┐
│  BLOC 1 : Comment fonctionne un LLM                │
│  → Prediction du mot suivant, tokens, contexte,    │
│    temperature, hallucinations                      │
│                                                     │
│  BLOC 2 : Panorama des LLM                         │
│  → ChatGPT, Claude, Gemini, Mistral                │
│  → Chaque outil a ses forces                       │
│                                                     │
│  BLOC 3 : Prise en main                            │
│  → 3 comptes crees et operationnels                │
│  → Premiere comparaison sur des cas concrets       │
│                                                     │
│  BLOC 4 : Bonnes pratiques                          │
│  → 5 erreurs a eviter, 5 reflexes a adopter        │
│  → La formule ROLE + CONTEXTE + TACHE + FORMAT     │
└─────────────────────────────────────────────────────┘
```

---

## Slide 41 — Pour la prochaine session

**Mission avant la Session 3 :**

1. Testez au moins **3 prompts professionnels** sur l'outil de votre choix
2. Notez ce qui a bien fonctionne et ce qui n'a pas fonctionne
3. Identifiez **1 tache recurrente** de votre quotidien
   que vous aimeriez automatiser avec l'IA

**Prochaine session : Les Agents IA et le Prompting Avance**
- Qu'est-ce qu'un Agent IA vs un simple chatbot ?
- Techniques de prompting avancees
- Creer ses premiers workflows intelligents

---

## Slide 42 — Questions / Reponses

```
╔══════════════════════════════════════════════════════╗
║                                                      ║
║              QUESTIONS ?                             ║
║                                                      ║
║   N'hesitez pas a poser vos questions               ║
║   sur ce que nous avons vu aujourd'hui.             ║
║                                                      ║
║   Rappel des ressources :                           ║
║   → chat.openai.com  (ChatGPT)                     ║
║   → claude.ai         (Claude)                      ║
║   → gemini.google.com (Gemini)                      ║
║   → chat.mistral.ai   (Mistral / Le Chat)           ║
║                                                      ║
╚══════════════════════════════════════════════════════╝
```

> Fin de la Session 2 — Jour 1 Apres-midi

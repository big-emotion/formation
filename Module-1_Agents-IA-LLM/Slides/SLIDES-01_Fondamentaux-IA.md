# SLIDES-01 : Fondamentaux de l'Intelligence Artificielle

> **Session 1 — Jour 1 matin (3h30)**
> Formation IA pour salaries du tertiaire | Niveau debutant
> Format : ~45 slides pour presentation Google Slides

---

<!-- ============================================================ -->
<!-- BLOC 1 — INTRODUCTION ET TOUR DE TABLE (30 min)              -->
<!-- ============================================================ -->

## Slide 1 — Titre

# Fondamentaux de l'Intelligence Artificielle

**Formation IA pour le Tertiaire — Module 1, Session 1**

- Duree : 3h30 (avec pause)
- Niveau : debutant, aucun prerequis technique
- Formateur : [Nom du formateur]
- Date : [Date]

> "L'IA ne remplacera pas les humains. Mais les humains qui utilisent l'IA remplaceront ceux qui ne l'utilisent pas."

---

## Slide 2 — Objectifs de la session

### A la fin de cette session, vous serez capables de :

1. **Definir** ce qu'est l'intelligence artificielle (et ce qu'elle n'est pas)
2. **Distinguer** Machine Learning, Deep Learning et IA generative
3. **Identifier** des cas d'usage concrets dans votre metier
4. **Comprendre** les enjeux ethiques et le cadre legal (RGPD, AI Act)
5. **Evaluer** le potentiel d'automatisation de vos taches quotidiennes

---

## Slide 3 — Deroulement de la matinee

| Bloc | Contenu | Duree |
|------|---------|-------|
| 1 | Introduction et tour de table | 30 min |
| 2 | Histoire et definitions de l'IA | 45 min |
| -- | **Pause cafe** | **10 min** |
| 3 | Machine Learning vs Deep Learning | 45 min |
| 4 | Applications concretes dans le tertiaire | 45 min |
| 5 | Ethique, limites et cadre legal | 30 min |

---

## Slide 4 — Tour de table

### Presentez-vous en 1 minute :

- Votre **prenom** et votre **poste**
- Votre **niveau actuel** avec l'IA (jamais utilise / un peu / regulierement)
- **Une question** que vous vous posez sur l'IA
- **Une crainte** ou **un espoir** lie a l'IA dans votre metier

> Le formateur note les questions sur un tableau visible — elles seront traitees au fil de la session.

---

## Slide 5 — QCM de positionnement initial

### Avant de commencer, testons vos connaissances !

Rendez-vous sur le **QCM de positionnement** :

> Voir **FICHE-03** — QCM de positionnement initial

- 10 questions, pas de piege
- Objectif : mesurer votre point de depart (pas vous evaluer !)
- Vous referez ce QCM en fin de formation pour voir votre progression

**Duree : 5 minutes**

---

<!-- ============================================================ -->
<!-- BLOC 2 — HISTOIRE ET DEFINITIONS (45 min)                    -->
<!-- ============================================================ -->

## Slide 6 — Un peu d'histoire : l'IA ne date pas d'hier

### La grande chronologie de l'IA

```
1950 ---- 1958 ---- 1966 ---- 1974-80 ---- 1987-93 ---- 1997
  |         |         |           |              |          |
Turing   Perceptron  ELIZA    1er hiver       2e hiver   Deep Blue
 Test    (1er neurone (1er      de l'IA        de l'IA    bat Kasparov
          artificiel) chatbot)                             aux echecs
```

- **1950** : Alan Turing pose LA question — "Une machine peut-elle penser ?"
- **1958** : Frank Rosenblatt invente le perceptron (ancetre du neurone artificiel)
- **1966** : ELIZA, le tout premier "chatbot" (tres basique)

---

## Slide 7 — Les hivers de l'IA

### Pourquoi l'IA a failli disparaitre... deux fois

| Periode | Ce qui s'est passe | Pourquoi ca a coince |
|---------|--------------------|-----------------------|
| **1974-1980** | 1er hiver de l'IA | Promesses non tenues, ordinateurs trop lents, financements coupes |
| **1987-1993** | 2e hiver de l'IA | Systemes experts trop rigides, couteux, incapables d'apprendre |

**Analogie** : C'est comme si on avait invente le concept de la voiture electrique en 1900... mais que les batteries n'existaient pas encore. L'idee etait bonne, la technologie pas prete.

---

## Slide 8 — La renaissance (1997-2016)

### L'IA revient en force

```
1997 --------- 2011 --------- 2012 --------- 2016
  |              |               |               |
Deep Blue      Siri           AlexNet         AlphaGo
bat Kasparov   (Apple)        revolution      bat le champion
aux echecs                    du deep         du monde de Go
                              learning
```

- **1997** : Deep Blue (IBM) bat Kasparov — mais c'est de la "force brute", pas de l'apprentissage
- **2012** : AlexNet revolutionne la reconnaissance d'images grace au deep learning
- **2016** : AlphaGo (Google) bat le champion du monde de Go — un jeu ou la force brute est impossible

---

## Slide 9 — L'explosion de l'IA generative (2020-2025)

### La periode dans laquelle nous vivons

```
2020 -------- 2022 -------- 2023 -------- 2024-2025
  |             |              |               |
GPT-3        ChatGPT        GPT-4          Claude 3.5/4
(OpenAI)     revolution     multimodal     Gemini 2.0
             mondiale       (texte+image)  Llama 3, Mistral
```

- **2020** : GPT-3 montre qu'un modele de langage peut ecrire des textes bluffants
- **Nov. 2022** : ChatGPT — 100 millions d'utilisateurs en 2 mois (record absolu)
- **2023** : GPT-4 — comprend aussi les images, raisonne mieux
- **2024-2025** : Explosion de la concurrence — Claude (Anthropic), Gemini (Google), Llama (Meta), Mistral (France)

---

## Slide 10 — Definir l'IA : 3 niveaux

### Toutes les IA ne se valent pas

| Niveau | Definition | Existe ? | Exemple |
|--------|-----------|----------|---------|
| **IA faible** (etroite) | Excellente sur UNE tache precise | OUI | Filtre anti-spam, GPS, reconnaissance faciale |
| **IA forte** (generale) | Capable de faire TOUT ce qu'un humain fait | NON | Science-fiction (pour l'instant) |
| **Super IA** | Plus intelligente que tous les humains reunis | NON | Pure science-fiction |

> **Important** : Tout ce que vous utilisez aujourd'hui (ChatGPT, Siri, Google...) est de l'IA faible. Meme si ca semble "intelligent", ca ne comprend pas vraiment.

---

## Slide 11 — L'IA faible : notre quotidien

### Vous utilisez deja de l'IA sans le savoir !

- **Netflix** : "Parce que vous avez regarde..." (systeme de recommandation)
- **Gmail** : "Ce mail est probablement un spam" (classification)
- **Google Maps** : "Prenez la A6, 15 min plus rapide" (optimisation)
- **Smartphone** : Deverrouillage par reconnaissance faciale (vision par ordinateur)
- **Banque** : "Transaction suspecte detectee" (detection d'anomalies)

**Analogie** : L'IA faible, c'est comme un employe ultra-specialise. Excellent dans son domaine, mais incapable de faire autre chose.

---

## Slide 12 — L'IA generative : la revolution de 2022

### Ce qui a TOUT change

**Avant 2022** : L'IA analysait des donnees existantes
**Apres 2022** : L'IA **cree** du contenu nouveau

| Type de contenu | Outils | Exemple |
|-----------------|--------|---------|
| Texte | ChatGPT, Claude, Gemini | Rediger un email, resumer un rapport |
| Images | DALL-E, Midjourney, Stable Diffusion | Creer une illustration, un logo |
| Audio | ElevenLabs, Suno | Generer une voix, une musique |
| Video | Sora, Runway | Creer un clip a partir d'un texte |
| Code | GitHub Copilot, Cursor | Ecrire un programme informatique |

---

## Slide 13 — Pourquoi c'est une revolution ?

### L'IA generative change la donne pour les metiers du tertiaire

**Avant** : Il fallait etre expert pour creer du contenu de qualite
- Rediger un rapport ? Il faut savoir ecrire
- Creer un visuel ? Il faut maitriser Photoshop
- Analyser des donnees ? Il faut connaitre Excel avance

**Maintenant** : Il faut savoir **poser les bonnes questions** (= prompt)
- "Redige un email professionnel pour relancer un client inactif depuis 3 mois"
- "Cree un tableau comparatif de ces 3 offres fournisseurs"
- "Resume ce rapport de 50 pages en 10 points cles"

> Le nouveau pouvoir, c'est **savoir demander**.

---

## Slide 14 — Les 4 grandes branches de l'IA

### L'IA, c'est un vaste domaine

```
                    Intelligence Artificielle
                            |
        +---------+---------+---------+
        |         |         |         |
    Vision     Traitement  Robotique  Systemes
    par        du langage             experts
    ordinateur naturel (NLP)
```

| Branche | Ce qu'elle fait | Exemple metier |
|---------|----------------|----------------|
| **Vision par ordinateur** | Analyser des images/videos | Controle qualite, OCR de factures |
| **NLP** (traitement du langage) | Comprendre/generer du texte | Chatbots, traduction, resume |
| **Robotique** | Agir dans le monde physique | Logistique, industrie |
| **Systemes experts** | Appliquer des regles metier | Diagnostic, aide a la decision |

---

## Slide 15 — Focus NLP : la branche qui vous concerne le plus

### Le traitement du langage naturel (NLP) au quotidien

Le NLP permet aux machines de **comprendre** et **generer** du langage humain.

**Applications directes pour vous :**
- Traduction automatique (DeepL, Google Translate)
- Correction et reformulation (Grammarly, LanguageTool)
- Resume automatique de documents
- Analyse de sentiment (avis clients, enquetes RH)
- Chatbots et assistants virtuels
- Generation de contenu (emails, rapports, articles)

> **ChatGPT et Claude sont des outils de NLP** — c'est la branche la plus impactante pour les metiers du tertiaire.

---

<!-- ============================================================ -->
<!-- BLOC 3 — MACHINE LEARNING vs DEEP LEARNING (45 min)          -->
<!-- ============================================================ -->

## Slide 16 — Pause cafe

### On fait une pause de 10 minutes !

- Prenez un cafe
- Echangez avec vos voisins
- Notez vos questions

> On reprend a [heure] avec la partie technique (promis, ca reste accessible !)

---

## Slide 17 — Machine Learning : l'IA qui apprend

### La grande idee du Machine Learning (apprentissage automatique)

**Programmation classique :**
```
Regles + Donnees  --->  [Programme]  --->  Resultats
```

**Machine Learning :**
```
Donnees + Resultats attendus  --->  [Algorithme]  --->  Regles apprises
```

**Analogie** : Imaginez apprendre a un enfant ce qu'est un chat.
- Methode classique : "Un chat a 4 pattes, des moustaches, des oreilles pointues..."
- Methode ML : Vous lui montrez 10 000 photos de chats. Il finit par reconnaitre un chat tout seul.

---

## Slide 18 — Apprentissage supervise

### Methode 1 : on donne les reponses pour que la machine apprenne

```
Donnees etiquetees          Modele entraine
  (avec reponses)              (predit)
       |                          |
  [Email] -> "spam"         [Nouvel email] -> "spam" ou "non spam" ?
  [Email] -> "non spam"
  [Email] -> "spam"
  ... x 10 000
```

**2 types principaux :**

| Type | Question posee | Exemple metier |
|------|---------------|----------------|
| **Classification** | "Dans quelle categorie ?" | Spam ou pas spam ? Client satisfait ou mecontent ? |
| **Regression** | "Quel chiffre ?" | Quel sera le CA du mois prochain ? Quel prix pour ce bien ? |

---

## Slide 19 — Exemple concret : detection de spam

### Comment Gmail filtre vos emails

```
Phase 1 : ENTRAINEMENT                Phase 2 : PREDICTION

Des milliers d'emails                  Nouvel email arrive
etiquetes "spam" / "non spam"
    |                                       |
    v                                       v
L'algorithme repere                    Le modele analyse :
des patterns :                         - Mots suspects ? OUI
- mots ("gratuit", "urgent")          - Expediteur inconnu ? OUI
- expediteur inconnu                   - Lien douteux ? OUI
- liens suspects                            |
    |                                       v
    v                                  Verdict : SPAM (98%)
Modele entraine                        -> Dossier spam
```

> Chaque fois que vous cliquez "Ceci n'est pas un spam", vous re-entrainez le modele !

---

## Slide 20 — Apprentissage non supervise

### Methode 2 : la machine decouvre des groupes toute seule

```
Donnees SANS etiquettes          Groupes decouverts
  (pas de reponses)
       |                         Groupe A : Jeunes urbains, gros budget tech
  [Client 1] age, achats...      Groupe B : Familles, budget moyen, weekend
  [Client 2] age, achats...  ->  Groupe C : Seniors, achats reguliers, fidelite
  [Client 3] age, achats...      Groupe D : Etudiants, petits achats, promos
  ... x 100 000
```

**Application phare : la segmentation clients**

| Cluster | Profil decouvert | Action marketing |
|---------|-----------------|------------------|
| A | Jeunes actifs urbains | Pub digitale, offres tech |
| B | Familles | Promotions weekend, packs famille |
| C | Seniors fideles | Programme fidelite, service premium |
| D | Etudiants | Offres etudiants, reseaux sociaux |

---

## Slide 21 — Autres exemples d'apprentissage non supervise

### Quand on ne sait pas ce qu'on cherche

| Technique | Ce qu'elle fait | Exemple metier |
|-----------|----------------|----------------|
| **Clustering** | Regrouper des elements similaires | Segmenter des clients, regrouper des CV |
| **Detection d'anomalies** | Reperer ce qui sort de l'ordinaire | Fraude bancaire, erreurs comptables |
| **Reduction de dimension** | Simplifier des donnees complexes | Synthese de tableaux de bord |

**Analogie** : C'est comme trier un tas de LEGO en vrac. Personne ne vous dit comment trier — vous decidez vous-meme (par couleur ? par taille ? par forme ?). L'algorithme fait pareil.

---

## Slide 22 — Du Machine Learning au Deep Learning

### Pourquoi aller plus loin ?

```
Machine Learning                    Deep Learning
(classique)                         (reseaux de neurones profonds)

Donnees simples                     Donnees complexes
(tableaux, chiffres)                (images, texte, audio, video)
     |                                   |
     v                                   v
L'humain choisit                    La machine decouvre
les caracteristiques                ses propres criteres
(ex: age, revenu, ville)           (ex: contours, textures, motifs)
     |                                   |
     v                                   v
Bon pour des donnees                Excellent pour des donnees
structurees                         non structurees
```

---

## Slide 23 — Le neurone artificiel : analogie avec le cerveau

### Comment ca marche (version simplifiee)

**Neurone biologique :**
```
Signaux entrants  --->  [Neurone]  --->  Signal sortant
(dendrites)              (soma)          (axone)
```

**Neurone artificiel :**
```
Donnees entrants  --->  [Calcul + Activation]  --->  Resultat
(inputs x poids)        (fonction mathematique)       (output)
```

**Un reseau de neurones profond = des milliers de neurones organises en couches**

```
Entrees    Couche 1    Couche 2    Couche 3    Sortie
  O ----->   O -------> O -------> O -------> Resultat
  O ----->   O -------> O -------> O
  O ----->   O -------> O
             O -------> O
```

> "Profond" = beaucoup de couches (parfois des centaines)

---

## Slide 24 — Pourquoi le Deep Learning marche maintenant ?

### 3 ingredients reunis au bon moment

```
        Donnees                Puissance               Algorithmes
       massives               de calcul                ameliores
          |                      |                        |
   Internet, reseaux      GPU (cartes                Recherche
   sociaux, capteurs,     graphiques),               academique,
   numerisation           cloud computing            open source
          |                      |                        |
          +----------+-----------+----------+-------------+
                     |
                     v
              DEEP LEARNING
            performant en 2012+
```

**Analogie** : Le Deep Learning, c'est comme une recette de cuisine.
- Les **donnees** = les ingredients (il en faut beaucoup et de bonne qualite)
- La **puissance de calcul** = le four (il faut qu'il soit assez puissant)
- Les **algorithmes** = la recette (il faut la bonne methode)

> Sans un seul de ces 3 elements, ca ne fonctionne pas.

---

## Slide 25 — IA generative : creer du contenu nouveau

### Le Deep Learning applique a la creation

**Comment ca fonctionne (simplifie) :**

```
Phase 1 : ENTRAINEMENT                  Phase 2 : GENERATION

Le modele lit des milliards             Vous posez une question (prompt)
de textes (livres, articles,                 |
sites web...)                                v
     |                                  Le modele genere une reponse
     v                                  mot par mot, en predisant
Il apprend les patterns                 le mot suivant le plus probable
du langage :                                 |
- grammaire                                  v
- style                                 "Le capital de la France
- connaissances                          est... Paris"
- raisonnement
```

> **Point cle** : Le modele ne "sait" rien. Il predit le mot suivant le plus probable. C'est statistique, pas magique.

---

## Slide 26 — Resume : IA, ML, DL, IA generative

### Comment tout s'emboite

```
+--------------------------------------------------+
|              Intelligence Artificielle            |
|                                                  |
|   +------------------------------------------+  |
|   |          Machine Learning                |  |
|   |                                          |  |
|   |   +----------------------------------+   |  |
|   |   |        Deep Learning             |   |  |
|   |   |                                  |   |  |
|   |   |   +--------------------------+   |   |  |
|   |   |   |    IA Generative         |   |   |  |
|   |   |   |  (GPT, Claude, DALL-E)   |   |   |  |
|   |   |   +--------------------------+   |   |  |
|   |   +----------------------------------+   |  |
|   +------------------------------------------+  |
+--------------------------------------------------+
```

- **IA** : toute technique simulant l'intelligence
- **ML** : l'IA qui apprend a partir de donnees
- **DL** : le ML avec des reseaux de neurones profonds
- **IA generative** : le DL qui cree du contenu nouveau

---

## Slide 27 — Quiz rapide !

### Testez votre comprehension

**1.** Netflix qui recommande des films, c'est :
- a) De l'IA generative
- b) Du Machine Learning
- c) De la robotique

**2.** ChatGPT qui ecrit un email, c'est :
- a) Du Machine Learning classique
- b) De l'IA generative
- c) Un systeme expert

**3.** Un filtre anti-spam, c'est de l'apprentissage :
- a) Supervise
- b) Non supervise

> **Reponses** : 1-b, 2-b, 3-a

---

<!-- ============================================================ -->
<!-- BLOC 4 — APPLICATIONS CONCRETES DANS LE TERTIAIRE (45 min)   -->
<!-- ============================================================ -->

## Slide 28 — L'IA dans VOS metiers

### 5 demonstrations concretes

Nous allons voir comment l'IA s'applique a **5 fonctions du tertiaire** :

| # | Fonction | Demonstration |
|---|----------|--------------|
| 1 | **RH** | Tri de CV et analyse d'entretiens |
| 2 | **Marketing** | Generation de contenu et analyse de sentiment |
| 3 | **Finance** | Analyse de donnees et detection d'anomalies |
| 4 | **Commercial** | Scoring de leads et personalisation |
| 5 | **Gestion / Admin** | Automatisation documentaire et synthese |

---

## Slide 29 — Demo 1 : RH — Recruter avec l'IA

### Cas d'usage pour les Ressources Humaines

| Tache | Sans IA | Avec IA |
|-------|---------|---------|
| Tri de CV | 2 min/CV x 200 CV = 6h40 | Preseletion en 5 min |
| Redaction d'offre d'emploi | 45 min de redaction | 5 min (generation + relecture) |
| Synthese d'entretien | Notes manuscrites partielles | Transcription + resume automatique |
| Onboarding | Documents standards | FAQ personnalisee par poste |

**Exemple de prompt :**
> "Analyse ces 5 CV pour un poste de controleur de gestion junior. Classe-les par pertinence en justifiant chaque classement selon les criteres suivants : diplome, experience, competences Excel."

**Attention** : Toujours relire et valider — l'IA peut avoir des biais (genre, age, origine).

---

## Slide 30 — Demo 2 : Marketing — Creer et analyser

### Cas d'usage pour le Marketing

| Tache | Sans IA | Avec IA |
|-------|---------|---------|
| Redaction post LinkedIn | 30 min | 5 min (generation + ajustement) |
| Analyse avis clients | Lecture manuelle x centaines | Analyse de sentiment automatique |
| Creation de visuels | Brief designer + iterations | Generation en quelques secondes |
| Persona marketing | Atelier de 2h | Generation en 10 min + validation |

**Exemple de prompt :**
> "Analyse ces 50 avis clients Google. Identifie les 3 points forts et les 3 points faibles les plus mentionnes. Presente le resultat dans un tableau avec le nombre de mentions."

---

## Slide 31 — Demo 3 : Finance — Analyser et detecter

### Cas d'usage pour la Finance

| Tache | Sans IA | Avec IA |
|-------|---------|---------|
| Categorisation de depenses | Saisie manuelle | Classification automatique |
| Detection de fraude | Controles ponctuels | Surveillance en temps reel |
| Previsions budgetaires | Tableurs complexes | Modeles predictifs |
| Lecture de factures | Saisie manuelle (OCR basique) | OCR intelligent + extraction |

**Exemple de prompt :**
> "Voici un tableau de depenses sur 12 mois. Identifie les postes qui ont augmente de plus de 15% par rapport a l'annee precedente. Propose 3 pistes d'optimisation."

---

## Slide 32 — Demo 4 : Commercial — Vendre mieux

### Cas d'usage pour les equipes commerciales

| Tache | Sans IA | Avec IA |
|-------|---------|---------|
| Scoring de leads | Intuition + experience | Score predictif base sur les donnees |
| Email de relance | Copier-coller generique | Email personnalise par contexte |
| Preparation de RDV | Recherche manuelle sur le prospect | Synthese automatique du prospect |
| Compte-rendu de RDV | Redaction apres coup | Transcription + synthese en direct |

**Exemple de prompt :**
> "Je vais rencontrer le directeur financier de [entreprise]. Fais-moi une fiche de preparation avec : chiffres cles de l'entreprise, actualites recentes, enjeux probables, et 3 questions d'ouverture pertinentes."

---

## Slide 33 — Demo 5 : Gestion / Admin — Automatiser

### Cas d'usage pour la gestion et l'administratif

| Tache | Sans IA | Avec IA |
|-------|---------|---------|
| Synthese de reunion | Notes partielles | Transcription + compte-rendu structure |
| Classement de documents | Tri manuel | Classification automatique |
| Reponse aux emails repetitifs | Copier-coller | Generation de reponses types |
| Traduction de documents | Traducteur en ligne | Traduction contextualisee + mise en forme |

**Exemple de prompt :**
> "Voici la transcription d'une reunion d'1h. Redige un compte-rendu structure avec : participants, decisions prises, actions a mener (qui, quoi, quand), et points en suspens."

---

## Slide 34 — Bilan : le gain de temps estime

### Ce que l'IA peut vous faire gagner

```
Tache repetitive de 30 min/jour
         x 220 jours/an
         = 110 heures/an
         = presque 3 semaines de travail

Si l'IA reduit cette tache de 70%
         = 77 heures economisees/an
         = du temps pour des taches a forte valeur ajoutee
```

**L'IA ne remplace pas votre expertise. Elle amplifie votre productivite.**

---

## Slide 35 — Activite : et dans VOTRE quotidien ?

### Discussion en sous-groupes (10 min)

**Consigne** : En groupes de 3-4 personnes, identifiez :

1. **3 taches repetitives** que vous faites chaque semaine
2. Pour chacune, estimez :
   - Le temps passe actuellement
   - Si l'IA pourrait aider (oui / peut-etre / non)
   - Le gain de temps estime

| Tache | Temps actuel | IA possible ? | Gain estime |
|-------|-------------|---------------|-------------|
| Ex: Trier les emails | 30 min/jour | Oui | 20 min/jour |
| ... | ... | ... | ... |
| ... | ... | ... | ... |

> Chaque groupe partagera ses 3 taches avec le reste de la salle.

---

## Slide 36 — Restitution et debriefing

### Ce qu'on retient de vos retours

- Quelles taches reviennent le plus souvent ?
- Quelles fonctions sont les plus "automatisables" ?
- Ou l'humain reste-t-il indispensable ?

**3 categories de taches :**

| Categorie | Description | Exemples |
|-----------|------------|----------|
| **Automatisable** | L'IA peut faire 80%+ seule | Tri, classification, synthese |
| **Assistable** | L'IA aide, l'humain supervise | Redaction, analyse, creation |
| **Humaine** | L'IA ne peut pas remplacer | Negociation, empathie, strategie |

---

<!-- ============================================================ -->
<!-- BLOC 5 — ETHIQUE, LIMITES ET CADRE LEGAL (30 min)            -->
<!-- ============================================================ -->

## Slide 37 — Les limites de l'IA : les hallucinations

### Quand l'IA invente avec aplomb

**Definition** : Une hallucination, c'est quand l'IA genere une information **fausse mais presentee avec assurance**.

**Exemples reels :**
- Un avocat americain a cite des jurisprudences inventees par ChatGPT (2023)
- Des biographies fictives generees avec des details tres credibles
- Des chiffres et statistiques totalement inventes mais vraisemblables

**Pourquoi ?** L'IA ne "sait" rien — elle predit des mots probables. Si aucune bonne reponse n'est probable, elle invente quelque chose de plausible.

**Regle d'or** : Ne jamais faire confiance a l'IA sans verification. Toujours croiser avec une source fiable.

---

## Slide 38 — Les biais algorithmiques

### L'IA reproduit (et amplifie) nos biais

**Principe** : L'IA apprend sur des donnees humaines. Si ces donnees contiennent des biais, l'IA les reproduit.

| Domaine | Biais observe | Consequence |
|---------|--------------|-------------|
| **Recrutement** | CV masculins favorises | Discrimination a l'embauche |
| **Credit bancaire** | Quartiers defavorises penalises | Exclusion financiere |
| **Justice** | Minorites surrepresentees dans les donnees | Predictions biaisees |
| **Sante** | Sous-representation de certaines populations | Diagnostics moins fiables |

**Ce qu'il faut retenir** : L'IA n'est pas "objective". Elle reflete les donnees sur lesquelles elle a ete entrainee.

> Toujours se demander : "Sur quelles donnees ce modele a-t-il appris ?"

---

## Slide 39 — RGPD et IA

### Ce que vous devez savoir

**Le RGPD (Reglement General sur la Protection des Donnees) s'applique a l'IA.**

| Principe RGPD | Application a l'IA |
|---------------|-------------------|
| **Consentement** | Informer les personnes que l'IA traite leurs donnees |
| **Minimisation** | Ne collecter que les donnees necessaires |
| **Droit a l'explication** | Pouvoir expliquer une decision prise par l'IA |
| **Droit d'opposition** | Pouvoir refuser une decision 100% automatisee |
| **Portabilite** | Pouvoir recuperer ses donnees |

**En pratique** :
- Ne jamais copier-coller de donnees personnelles dans ChatGPT ou Claude
- Anonymiser les donnees avant de les soumettre a un outil d'IA
- Verifier la politique de confidentialite de l'outil utilise

---

## Slide 40 — L'AI Act europeen

### Le premier cadre legal mondial pour l'IA

L'Union europeenne a adopte l'**AI Act** (2024), qui classe les IA par niveau de risque :

```
+------------------------------------------+
|          RISQUE INACCEPTABLE             |  INTERDIT
|  (score social, manipulation,            |
|   surveillance biometrique de masse)     |
+------------------------------------------+
|          RISQUE ELEVE                    |  TRES ENCADRE
|  (recrutement, credit, justice,          |
|   sante, education)                      |
+------------------------------------------+
|          RISQUE LIMITE                   |  OBLIGATIONS DE
|  (chatbots, deepfakes)                   |  TRANSPARENCE
+------------------------------------------+
|          RISQUE MINIMAL                  |  PAS DE
|  (filtres spam, jeux video)              |  CONTRAINTE
+------------------------------------------+
```

> **A retenir** : Si vous utilisez l'IA en RH (recrutement) ou en finance (credit), vous etes dans la zone "risque eleve" — des obligations legales s'appliquent.

---

## Slide 41 — Propriete intellectuelle

### A qui appartient ce que l'IA genere ?

**Questions ouvertes (le droit evolue) :**

| Question | Etat actuel |
|----------|------------|
| Un texte genere par IA est-il protegeable ? | Non en general (pas d'auteur humain) |
| Peut-on utiliser des contenus generes commercialement ? | Oui, mais conditions variables selon les outils |
| L'IA a-t-elle appris sur des oeuvres protegees ? | Oui, et c'est un debat juridique majeur |
| Qui est responsable si l'IA produit un contenu illegal ? | L'utilisateur, pas l'outil |

**Regles pratiques :**
- Ne pas publier un contenu genere tel quel sans relecture
- Verifier les conditions d'utilisation de chaque outil
- Documenter l'usage de l'IA dans vos processus
- L'humain reste responsable du resultat final

---

## Slide 42 — Les bonnes pratiques

### 10 regles d'or pour utiliser l'IA au travail

| # | Regle | Pourquoi |
|---|-------|----------|
| 1 | **Toujours verifier** les reponses de l'IA | Hallucinations possibles |
| 2 | **Ne jamais partager** de donnees personnelles/confidentielles | RGPD + securite |
| 3 | **Anonymiser** les donnees avant utilisation | Protection des personnes |
| 4 | **Garder un esprit critique** | L'IA se trompe avec assurance |
| 5 | **Documenter** l'usage de l'IA | Tracabilite et conformite |
| 6 | **Relire et adapter** le contenu genere | Qualite et responsabilite |
| 7 | **Respecter** le droit d'auteur | Ne pas publier tel quel |
| 8 | **Informer** collegues et clients de l'usage de l'IA | Transparence |
| 9 | **Se former** en continu | Le domaine evolue tres vite |
| 10 | **L'IA est un outil**, pas un remplacement | Vous restez aux commandes |

---

## Slide 43 — Synthese de la session

### Ce que vous avez appris ce matin

```
+------------------------------------------------------------------+
|  1. L'IA existe depuis 1950, mais c'est en 2022 que tout         |
|     a change avec l'IA generative (ChatGPT)                      |
|                                                                  |
|  2. Machine Learning = apprendre a partir de donnees             |
|     Deep Learning = reseaux de neurones profonds                 |
|     IA generative = creer du contenu nouveau                     |
|                                                                  |
|  3. L'IA a des applications concretes dans TOUS les metiers      |
|     du tertiaire (RH, marketing, finance, commercial, gestion)   |
|                                                                  |
|  4. Mais attention aux limites : hallucinations, biais,          |
|     RGPD, AI Act, propriete intellectuelle                       |
|                                                                  |
|  5. Regle d'or : l'IA est un assistant puissant, mais VOUS       |
|     restez responsable du resultat                               |
+------------------------------------------------------------------+
```

---

## Slide 44 — Et la suite ?

### Cet apres-midi : Session 2

**Prompting et Agents IA**

- Comment bien formuler ses demandes a l'IA (l'art du prompt)
- Decouverte des agents IA et de leurs capacites
- Ateliers pratiques avec ChatGPT et Claude
- Construction de votre premier workflow IA

> Voir **SLIDES-03** pour la presentation de l'apres-midi

---

## Slide 45 — Questions / Reponses

### Vos questions avant la pause dejeuner

- Reprenons les questions notees en debut de session
- Avons-nous repondu a toutes ?
- Nouvelles questions ?

**Ressources pour aller plus loin :**
- FICHE-03 : QCM de positionnement (a refaire en fin de formation)
- FICHE-04 : Glossaire IA (distribue en version papier)

> **Merci pour votre attention et votre participation !**
> Rendez-vous cet apres-midi pour la mise en pratique.

---

*Document genere pour la Formation IA Tertiaire — Module 1, Session 1*
*Version 1.0*

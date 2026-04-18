# SLIDES-09 — Automatisation No-Code et APIs avec l'IA

> **Session 9** — Jour 5, matin (9h00-12h30)
> **Duree** : 3h30 | **Niveau** : Avance
> **Prerequis** : Sessions 1-8 (fondamentaux IA, prompting, cas metiers, integration bureautique)
> **Objectifs** : Comprendre l'automatisation no-code, creer des scenarios Make, integrer l'IA via APIs

---

<!-- ============================================================ -->
<!-- BLOC 1 — INTRODUCTION AUTOMATISATION NO-CODE (45 min)        -->
<!-- ============================================================ -->

## BLOC 1 — INTRODUCTION AUTOMATISATION NO-CODE (45 min)

---

### Slide 1 — Page de titre

# Automatisation No-Code et APIs avec l'IA
## Session 9 — Faire travailler l'IA a votre place, meme quand vous dormez

Formation IA pour les Metiers du Tertiaire
Jour 5 — Matin

---

### Slide 2 — Objectifs de la session

## Ce que vous saurez faire a la fin de cette session

1. **Comprendre** les concepts d'automatisation (trigger, action, filtre)
2. **Creer** un scenario d'automatisation sur Make (ex-Integromat)
3. **Expliquer** ce qu'est une API et comment elle fonctionne
4. **Integrer** un appel a l'IA (OpenAI) dans un workflow automatise
5. **Concevoir** un mini-projet d'automatisation adapte a votre metier

---

### Slide 3 — Deroulement de la matinee

| Bloc | Contenu | Duree |
|------|---------|-------|
| 1 | Introduction a l'automatisation no-code | 45 min |
| -- | **Pause cafe** | **10 min** |
| 2 | Premier scenario Make : formulaire --> Sheets --> email | 1h00 |
| -- | **Pause** | **5 min** |
| 3 | Integrer l'IA dans les workflows (APIs + Make) | 1h00 |
| 4 | Conception du mini-projet final | 30 min |

---

### Slide 4 — Rappel : d'ou on vient

## Notre parcours jusqu'ici

```
JOUR 1-2 : FONDAMENTAUX          JOUR 3-4 : PRATIQUE METIER
~~~~~~~~~~~~~~~~~~~~~~~~~         ~~~~~~~~~~~~~~~~~~~~~~~~
[x] Comprendre l'IA et les LLM   [x] RAG et assistants
[x] Prompting de base             [x] Cas d'usage metier
[x] Prompting avance              [x] IA dans Workspace/M365
[x] Chaines de prompts            [x] Workflows hybrides

                    JOUR 5 (Aujourd'hui)
                    ~~~~~~~~~~~~~~~~~~~~
                    [ ] Automatisation no-code
                    [ ] APIs et IA automatisee
                    [ ] Mini-projet final
```

Aujourd'hui : on passe de **"je dialogue avec l'IA"** a **"l'IA travaille automatiquement pour moi"**.

---

### Slide 5 — Qu'est-ce que l'automatisation ?

## Automatiser = faire faire a la machine les taches repetitives

**Definition :**
> Une automatisation execute une sequence d'actions predefinies,
> declenchee par un evenement, sans intervention humaine.

**Exemples du quotidien (que vous connaissez deja) :**
- Regle Gmail : "Si l'email contient 'facture', deplacer dans le dossier Factures"
- Reponse automatique d'absence
- Notification Teams quand un fichier est modifie

**Ce qu'on va faire aujourd'hui :**
- La meme chose, mais **en plus puissant** et **avec de l'IA**

---

### Slide 6 — Les 4 concepts fondamentaux

## Le vocabulaire de l'automatisation

```
+------------------------------------------------------------------+
|                                                                  |
|  1. TRIGGER (Declencheur)                                        |
|     "Quand est-ce que ca demarre ?"                              |
|     Exemple : un nouveau formulaire est soumis                   |
|                                                                  |
|  2. ACTION                                                       |
|     "Qu'est-ce qui se passe ensuite ?"                           |
|     Exemple : ecrire une ligne dans Google Sheets                |
|                                                                  |
|  3. FILTRE (Condition)                                           |
|     "Seulement si..."                                            |
|     Exemple : seulement si le montant > 1000 EUR                 |
|                                                                  |
|  4. ITERATION (Boucle)                                           |
|     "Pour chaque element..."                                     |
|     Exemple : pour chaque ligne du tableau, envoyer un email     |
|                                                                  |
+------------------------------------------------------------------+
```

Ces 4 concepts suffisent pour creer 90% des automatisations.

---

### Slide 7 — Analogie : la chaine de dominos

## Pensez "dominos"

```
[Trigger]  -->  [Action 1]  -->  [Filtre]  -->  [Action 2]  -->  [Action 3]
   |               |               |               |               |
   v               v               v               v               v
Nouveau        Lire les       Montant        Envoyer       Ajouter une
formulaire     donnees du     > 500 EUR ?    un email      ligne dans
soumis         formulaire     Oui -->        au manager    le tableau
                              Non --> STOP                  de suivi
```

Chaque domino tombe et declenche le suivant. On appelle ca un **scenario** ou un **workflow**.

---

### Slide 8 — Pourquoi le no-code ?

## No-code = pas besoin de programmer

| Approche | Compétence requise | Temps de creation | Flexibilite |
|----------|-------------------|-------------------|-------------|
| **Code** (Python, JavaScript) | Developpeur | Heures/jours | Maximale |
| **No-code** (Make, Zapier) | Aucune en dev | Minutes/heures | Tres bonne |
| **Regles email** (Gmail, Outlook) | Aucune | Minutes | Limitee |

**Le no-code est parfait pour vous si :**
- Vous n'etes pas developpeur
- Vous avez des taches repetitives a automatiser
- Vous voulez connecter plusieurs outils entre eux
- Vous voulez integrer de l'IA dans vos processus

---

### Slide 9 — Panorama des outils no-code

## Les principaux outils d'automatisation

```
+----------------+     +----------------+     +----------------+
|     MAKE       |     |    ZAPIER      |     |   N8N          |
| (ex-Integromat)|     |                |     |                |
|                |     |                |     |                |
| Plan gratuit   |     | Plan gratuit   |     | Open source    |
| 1000 ops/mois  |     | 100 taches/mois|     | Auto-heberge   |
| Interface      |     | Interface      |     | Interface      |
| visuelle       |     | lineaire       |     | visuelle       |
| Tres flexible  |     | Tres simple    |     | Tres flexible  |
+----------------+     +----------------+     +----------------+

+----------------+     +----------------+
| POWER AUTOMATE |     |   IFTTT        |
| (Microsoft)    |     |                |
|                |     |                |
| Inclus dans    |     | Grand public   |
| M365 Business  |     | Tres simple    |
| Integration    |     | Limite en      |
| Microsoft      |     | entreprise     |
+----------------+     +----------------+
```

**Notre choix pour la formation : Make** (interface visuelle, plan gratuit genereux, flexible).

---

### Slide 10 — Presentation de Make

## Make (ex-Integromat) : votre outil du jour

**Pourquoi Make ?**
- Interface **visuelle** : vous voyez le flux comme un schema
- **Plan gratuit** : 1000 operations/mois (largement suffisant pour debuter)
- **+1500 applications** connectees (Google, Microsoft, Slack, Notion, etc.)
- **Module HTTP** : permet d'appeler n'importe quelle API (dont OpenAI)
- Communaute active et documentation en francais

**Interface Make :**
```
+-------------------------------------------------------------------+
|  Make.com                                          [Run once]     |
|                                                                   |
|  +----------+      +----------+      +----------+                 |
|  | Google   | ---> | Filtre   | ---> | Gmail    |                 |
|  | Sheets   |      | Montant  |      | Envoyer  |                 |
|  | Nouvelle |      | > 500    |      | email    |                 |
|  | ligne    |      |          |      |          |                 |
|  +----------+      +----------+      +----------+                 |
|                                                                   |
+-------------------------------------------------------------------+
```

---

### Slide 11 — Demonstration : interface Make

## Visite guidee de l'interface Make

**Elements cles :**

| Element | Role |
|---------|------|
| **Scenario** | Un workflow complet (ensemble de modules connectes) |
| **Module** | Un bloc (trigger ou action) representant un outil |
| **Connexion** | La fleche entre deux modules (passage de donnees) |
| **Run once** | Tester le scenario une seule fois |
| **Scheduling** | Programmer l'execution automatique (toutes les 15 min, etc.) |
| **History** | Journal des executions passees |

**Demonstration en direct :**
1. Creer un nouveau scenario
2. Ajouter un module Google Sheets
3. Explorer les options disponibles
4. Comprendre le mapping de donnees

---

### Slide 12 — Les types de modules dans Make

## Anatomie d'un scenario Make

```
TYPES DE MODULES :

  (O)  TRIGGER          : Demarre le scenario
       Icone : cercle   (ex: "Nouvelle ligne dans Sheets")

  [ ]  ACTION           : Execute une operation
       Icone : carre    (ex: "Envoyer un email")

  < >  FILTRE           : Condition de passage
       Icone : losange  (ex: "Si montant > 500")

  {~}  TRANSFORMATEUR   : Modifie les donnees
       Icone : engrenage (ex: "Convertir date", "Concatener textes")

  [+]  ITERATEUR         : Boucle sur une liste
       Icone : fleche    (ex: "Pour chaque ligne du fichier")

  [=]  AGREGATEUR       : Regroupe des resultats
       Icone : entonnoir (ex: "Combiner en un seul email")
```

---

<!-- ============================================================ -->
<!-- BLOC 2 — PREMIER SCENARIO MAKE (1h00)                        -->
<!-- ============================================================ -->

## BLOC 2 — PREMIER SCENARIO MAKE (1h00)

---

### Slide 13 — Creer votre compte Make

# Premier scenario Make
## Formulaire --> Google Sheets --> Email

---

### Slide 14 — Etape 0 : creation du compte

## Creer votre compte Make gratuit

**Instructions :**
1. Aller sur **make.com**
2. Cliquer sur "Get started free"
3. S'inscrire avec votre compte Google (plus simple)
4. Choisir le plan **Free** (1000 operations/mois)

```
+-----------------------------------+
|  Plan FREE - Ce qui est inclus :  |
|                                   |
|  - 1000 operations/mois           |
|  - 2 scenarios actifs             |
|  - Execution toutes les 15 min    |
|  - Tous les modules disponibles   |
|  - Historique 7 jours             |
|                                   |
|  Largement suffisant pour         |
|  apprendre et experimenter !      |
+-----------------------------------+
```

---

### Slide 15 — Notre premier scenario : la vue d'ensemble

## Ce qu'on va construire

```
SCENARIO : "Formulaire --> Sheets --> Email"

  (O) Google Forms       [ ] Google Sheets     [ ] Gmail
  Nouveau formulaire  -> Ajouter une ligne  -> Envoyer un email
  soumis                 au tableau de suivi   de confirmation

  Declencheur            Action 1              Action 2
```

**Cas d'usage reel :**
- Un client remplit un formulaire de contact
- Les donnees sont automatiquement ajoutees a votre tableau de suivi
- Un email de confirmation est envoye au client

---

### Slide 16 — Etape 1 : preparer les outils

## Preparation (5 min)

**Google Forms :**
1. Creer un formulaire simple avec 3 champs :
   - Nom (reponse courte)
   - Email (reponse courte)
   - Message (paragraphe)
2. Obtenir le lien du formulaire

**Google Sheets :**
1. Creer un nouveau tableur "Suivi formulaires"
2. En-tetes : Nom | Email | Message | Date | Statut

**Conseil** : si vous manquez de temps, utilisez les modeles fournis par le formateur.

---

### Slide 17 — Etape 2 : creer le scenario dans Make

## Construction pas a pas (20 min)

**Module 1 : Trigger Google Forms**
```
1. Cliquer sur [+] pour ajouter un module
2. Rechercher "Google Forms"
3. Choisir "Watch Responses"
4. Connecter votre compte Google
5. Selectionner votre formulaire
```

**Module 2 : Action Google Sheets**
```
1. Cliquer sur [+] apres le module Forms
2. Rechercher "Google Sheets"
3. Choisir "Add a Row"
4. Mapper les champs : Nom --> Colonne A, Email --> Colonne B, etc.
```

**Module 3 : Action Gmail**
```
1. Cliquer sur [+] apres le module Sheets
2. Rechercher "Gmail"
3. Choisir "Send an Email"
4. Destinataire : {{Email}} (du formulaire)
5. Sujet : "Merci pour votre message"
6. Corps : email de confirmation personnalise
```

---

### Slide 18 — Etape 3 : tester et debugger

## Tester votre scenario

**Methode de test :**

```
1. Cliquer sur "Run once" (en bas a gauche)
   --> Make attend un evenement

2. Soumettre votre formulaire avec des donnees test
   --> Le scenario se declenche

3. Observer le resultat :
   +----------+      +----------+      +----------+
   |  VERT    | ---> |  VERT    | ---> |  VERT    |   = Tout fonctionne !
   +----------+      +----------+      +----------+

   +----------+      +----------+      +----------+
   |  VERT    | ---> |  ROUGE   | ---> |  GRIS    |   = Erreur au module 2
   +----------+      +----------+      +----------+

4. Si erreur : cliquer sur le module rouge pour voir le detail
```

---

### Slide 19 — Les erreurs courantes et solutions

## Debugging : les problemes frequents

| Probleme | Cause probable | Solution |
|----------|---------------|----------|
| "Connection expired" | Token Google expire | Reconnecter le compte Google |
| "Mapping error" | Champ mal associe | Verifier le mapping des donnees |
| "404 Not Found" | Fichier Sheets supprime/deplace | Reconfigurer le module |
| "Rate limit" | Trop d'executions rapides | Attendre quelques minutes |
| "Empty response" | Formulaire sans reponse | Soumettre une reponse test |

**Bonne pratique** : toujours tester avec "Run once" avant d'activer le scheduling.

---

### Slide 20 — Bonnes pratiques Make

## Regles d'or pour vos scenarios

1. **Nommez vos scenarios** clairement (ex: "Contact Form --> CRM")
2. **Testez toujours** avec "Run once" avant d'activer
3. **Ajoutez des filtres** pour eviter les executions inutiles
4. **Gerez les erreurs** : ajoutez un module "Error handler"
5. **Surveillez vos operations** : le plan gratuit = 1000 ops/mois
6. **Documentez** : ajoutez des notes sur chaque module

```
BON NOMMAGE :                    MAUVAIS NOMMAGE :
~~~~~~~~~~~~~                    ~~~~~~~~~~~~~~~~
"Lead Form --> Sheets + Email"   "Scenario 1"
"Daily Sales Report --> Slack"   "test"
"New Invoice --> PDF + Drive"    "mon scenario"
```

---

### Slide 21 — Exercice : ameliorer votre scenario

## Exercice — Ameliorez votre scenario (10 min)

**Ajoutez au moins UNE amelioration :**

| Amelioration | Comment |
|-------------|---------|
| **Filtre** | N'envoyer l'email que si le message contient "urgent" |
| **Formatage** | Ajouter la date/heure automatique dans Sheets |
| **Email enrichi** | Personnaliser l'email avec le nom du formulaire |
| **Notification** | Ajouter un module Slack/Teams pour prevenir l'equipe |

**Bonus** : ajoutez un module "Error handler" pour recevoir un email si le scenario echoue.

---

<!-- ============================================================ -->
<!-- BLOC 3 — INTEGRER L'IA DANS LES WORKFLOWS (1h00)            -->
<!-- ============================================================ -->

## BLOC 3 — INTEGRER L'IA DANS LES WORKFLOWS (1h00)

---

### Slide 22 — L'IA dans les workflows automatises

# Integrer l'IA dans vos automatisations
## Quand le no-code rencontre l'intelligence artificielle

---

### Slide 23 — C'est quoi une API ?

## API : l'interface entre deux logiciels

**Analogie du restaurant :**

```
+-------------------------------------------------------------------+
|                                                                   |
|  VOUS (le client)     LE SERVEUR (l'API)     LA CUISINE (le LLM) |
|                                                                   |
|  "Je voudrais un      Prend la commande      Prepare le plat     |
|   resume de ce        Transmet a la           Genere le resume    |
|   texte, s'il         cuisine                 Renvoie le          |
|   vous plait"         Apporte le plat         resultat            |
|                                                                   |
|  Vous n'allez pas en cuisine.                                     |
|  Vous passez par le serveur (l'API).                              |
|                                                                   |
+-------------------------------------------------------------------+
```

**En termes techniques :**
- **Requete** = votre commande (prompt + parametres)
- **API** = le serveur qui transmet
- **Reponse** = le plat (texte genere par l'IA)

---

### Slide 24 — API en pratique : comment ca marche

## Anatomie d'un appel API

```
REQUETE (ce que vous envoyez) :
+-------------------------------------------+
| URL : https://api.openai.com/v1/chat/     |
| Methode : POST                            |
| En-tetes :                                |
|   Authorization: Bearer sk-xxxxx          |
|   Content-Type: application/json          |
| Corps :                                   |
|   {                                       |
|     "model": "gpt-4o-mini",              |
|     "messages": [                         |
|       {"role": "user",                    |
|        "content": "Resume ce texte..."}   |
|     ]                                     |
|   }                                       |
+-------------------------------------------+

REPONSE (ce que vous recevez) :
+-------------------------------------------+
| {                                         |
|   "choices": [                            |
|     {"message": {                         |
|       "content": "Voici le resume..."     |
|     }}                                    |
|   ]                                       |
| }                                         |
+-------------------------------------------+
```

Pas de panique : Make fait tout ca pour vous avec une interface visuelle !

---

### Slide 25 — Cle API : votre pass d'acces

## Obtenir une cle API OpenAI

**Qu'est-ce qu'une cle API ?**
- Un code unique qui vous identifie aupres du service
- Comme un badge d'acces personnel
- A ne **jamais** partager publiquement

**Comment l'obtenir (OpenAI) :**
1. Aller sur **platform.openai.com**
2. Creer un compte (ou se connecter)
3. Menu > API Keys > "Create new secret key"
4. Copier la cle (elle ne sera affichee qu'une fois !)
5. Ajouter un credit minimum (5 EUR suffisent pour des mois d'usage leger)

**Cout :**
- GPT-4o-mini : ~0.15 EUR pour 1000 requetes courtes
- GPT-4o : ~1.50 EUR pour 1000 requetes courtes
- Pour la formation : quelques centimes maximum

---

### Slide 26 — Le module HTTP dans Make

## Le module HTTP : votre pont vers toutes les APIs

```
SANS module HTTP :                  AVEC module HTTP :
~~~~~~~~~~~~~~~~~                   ~~~~~~~~~~~~~~~~~
Make ne connait que                 Make peut appeler
les apps pre-integrees              N'IMPORTE QUELLE API

Google, Slack, etc.                 OpenAI, Claude, Mistral,
                                    votre API interne, etc.
```

**Comment ajouter le module HTTP :**
1. Dans votre scenario, cliquer [+]
2. Rechercher "HTTP"
3. Choisir "Make a request"
4. Configurer : URL, methode, en-tetes, corps

C'est le module le plus **puissant** de Make. Il ouvre la porte a toutes les possibilites.

---

### Slide 27 — Scenario 1 : Sheets --> API OpenAI --> Email

## Scenario pratique : enrichir des donnees avec l'IA

```
SCENARIO : "Personnaliser des emails avec l'IA"

  (O) Google Sheets      {~} HTTP (OpenAI)      [ ] Gmail
  Pour chaque ligne   -> Genere un email      -> Envoie l'email
  du tableau             personnalise avec IA     personnalise

  Trigger               Transformation IA        Action
```

**Cas d'usage reel :**
Vous avez 50 contacts dans un tableau. Pour chacun, l'IA genere un email personnalise en fonction de son profil, puis l'email est envoye automatiquement.

---

### Slide 28 — Construction du scenario IA (etape par etape)

## Etape 1 : Le trigger Google Sheets

**Configuration du module Google Sheets :**
- Action : "Search Rows" (chercher les lignes)
- Tableur : votre fichier de contacts
- Filtre : colonne "Statut" = "A traiter"

**Donnees recuperees pour chaque ligne :**
```
{
  "nom": "Marie Dupont",
  "entreprise": "TechCorp",
  "secteur": "Numerique",
  "email": "marie@techcorp.fr"
}
```

---

### Slide 29 — Construction du scenario IA (suite)

## Etape 2 : L'appel API OpenAI

**Configuration du module HTTP :**

| Parametre | Valeur |
|-----------|--------|
| **URL** | `https://api.openai.com/v1/chat/completions` |
| **Methode** | POST |
| **En-tete 1** | `Authorization: Bearer {{votre_cle_api}}` |
| **En-tete 2** | `Content-Type: application/json` |

**Corps de la requete :**
```json
{
  "model": "gpt-4o-mini",
  "messages": [
    {
      "role": "system",
      "content": "Tu es un expert en communication commerciale B2B."
    },
    {
      "role": "user",
      "content": "Redige un email de prospection personnalise pour {{nom}},
                  qui travaille chez {{entreprise}} dans le secteur {{secteur}}.
                  Ton professionnel, 5 lignes maximum."
    }
  ]
}
```

---

### Slide 30 — Construction du scenario IA (fin)

## Etape 3 : Envoyer l'email personnalise

**Configuration du module Gmail :**

| Champ | Valeur |
|-------|--------|
| **Destinataire** | `{{email}}` (depuis Sheets) |
| **Objet** | "Une idee pour {{entreprise}}" |
| **Corps** | `{{reponse_openai}}` (depuis le module HTTP) |

**Resultat final :**
```
Pour chaque contact du tableau :
  1. Make lit les infos du contact
  2. L'IA genere un email personnalise
  3. L'email est envoye automatiquement
  4. Le statut passe a "Traite" dans Sheets

50 emails personnalises en 2 minutes au lieu de 2 heures !
```

---

### Slide 31 — Exercice pratique : scenario IA

## Exercice — Construisez le scenario Sheets --> IA --> Email (20 min)

**Consigne :**
1. Creez un tableur avec 5 contacts fictifs (nom, entreprise, secteur, email)
2. Dans Make, creez un nouveau scenario
3. Ajoutez les 3 modules : Sheets > HTTP (OpenAI) > Gmail
4. Configurez chaque module comme montre
5. Testez avec "Run once"

**Simplification autorisee :**
- Utilisez la cle API fournie par le formateur
- Si Gmail bloque : remplacez par un module "Envoyer a soi-meme"
- Si le temps manque : observez la demonstration et reproduisez apres

---

### Slide 32 — Scenario 2 : Drive --> Resume IA --> Sauvegarde

## Scenario avance : resumer automatiquement les nouveaux fichiers

```
SCENARIO : "Auto-resume de documents"

  (O) Google Drive       [ ] Google Docs       {~} HTTP (OpenAI)
  Nouveau fichier     -> Lire le contenu    -> Generer un resume
  dans le dossier        du document            avec l'IA
  "A traiter"

       |
       v
  [ ] Google Docs
  Creer un nouveau
  document "Resume de..."
  dans le dossier "Resumes"
```

**Cas d'usage reel :**
Chaque fois qu'un collegue depose un rapport dans un dossier partage, un resume est automatiquement cree et sauvegarde.

---

### Slide 33 — Details du scenario Drive --> Resume

## Configuration du scenario de resume automatique

**Module 1 : Trigger Google Drive**
- Action : "Watch Files" (surveiller les nouveaux fichiers)
- Dossier : "A traiter"
- Filtrer par type : .docx, .pdf, .txt

**Module 2 : Google Docs - Lire le contenu**
- Action : "Get content of a Document"
- Fichier : celui detecte par le trigger

**Module 3 : HTTP (OpenAI)**
- Prompt : "Resume le texte suivant en 5 points cles, en francais : {{contenu}}"
- Modele : gpt-4o-mini (suffisant et economique)

**Module 4 : Google Docs - Creer un document**
- Titre : "Resume - {{nom_fichier_original}}"
- Contenu : la reponse de l'IA
- Dossier : "Resumes"

---

### Slide 34 — Autres idees de scenarios IA

## Inspirations pour vos propres scenarios

| Scenario | Trigger | IA | Action finale |
|----------|---------|-----|---------------|
| **Veille automatisee** | Nouveau article RSS | Resume + analyse | Email digest quotidien |
| **Tri d'emails** | Nouvel email recu | Categorie + priorite | Etiquetage + notification |
| **Rapport automatique** | Chaque lundi 8h | Analyse donnees Sheets | PDF + envoi par email |
| **FAQ automatique** | Nouveau message Slack | Reponse basee sur docs | Reponse dans le fil |
| **Traduction** | Nouveau fichier Drive | Traduction IA | Sauvegarde version traduite |
| **Scoring leads** | Nouveau contact CRM | Analyse du profil | Score + notification |

Chaque scenario suit le meme schema : **Trigger --> [IA] --> Action**.

---

### Slide 35 — Securite et bonnes pratiques API

## Regles de securite pour les APIs et l'automatisation

```
+------------------------------------------------------------------+
|  A FAIRE                           |  A NE PAS FAIRE              |
|  ~~~~~~~~                          |  ~~~~~~~~~~~~~~~             |
|                                    |                              |
|  Stocker la cle API dans les       |  Ecrire la cle en dur dans  |
|  "Connections" de Make             |  le scenario                 |
|                                    |                              |
|  Utiliser le modele le moins       |  Utiliser GPT-4 pour tout   |
|  cher suffisant (gpt-4o-mini)     |  (couteux et lent)           |
|                                    |                              |
|  Ajouter un filtre pour limiter    |  Laisser tourner sans limite|
|  les executions                    |  = facture surprise          |
|                                    |                              |
|  Tester avec "Run once" d'abord   |  Activer le scheduling       |
|                                    |  sans avoir teste            |
|                                    |                              |
|  Verifier les donnees sensibles    |  Envoyer des donnees         |
|  avant envoi a l'API              |  personnelles a l'API        |
+------------------------------------------------------------------+
```

---

### Slide 36 — Cout des APIs : comprendre la facturation

## Combien coute l'IA en API ?

**Modele de facturation : au token (mot)**

| Modele | Cout input | Cout output | Exemple : 1000 emails |
|--------|-----------|-------------|----------------------|
| GPT-4o-mini | 0.15 $/M tokens | 0.60 $/M tokens | ~0.50 EUR |
| GPT-4o | 2.50 $/M tokens | 10 $/M tokens | ~8 EUR |
| Claude 3.5 Sonnet | 3 $/M tokens | 15 $/M tokens | ~12 EUR |

**En pratique pour un usage tertiaire :**
- Resume de 10 documents/jour : ~2 EUR/mois
- 100 emails personnalises/semaine : ~1 EUR/mois
- Analyse quotidienne de donnees : ~3 EUR/mois

**Conclusion** : l'IA en API est **extremement abordable** pour les usages bureautiques.

---

<!-- ============================================================ -->
<!-- BLOC 4 — CONCEPTION DU MINI-PROJET (30 min)                  -->
<!-- ============================================================ -->

## BLOC 4 — CONCEPTION DU MINI-PROJET (30 min)

---

### Slide 37 — Le mini-projet final

# Conception du mini-projet
## Votre automatisation IA personnalisee

---

### Slide 38 — Presentation du projet final

## Cet apres-midi : vous construisez votre propre projet

**Objectif :**
Creer un scenario d'automatisation **utile pour votre metier** qui integre au moins :

```
+------------------------------------------------------------------+
|  EXIGENCES MINIMALES DU PROJET :                                 |
|                                                                  |
|  [x] 3 etapes minimum dans le scenario                          |
|  [x] Au moins 1 etape utilisant l'IA (API ou module IA)         |
|  [x] Un trigger pertinent pour votre quotidien                  |
|  [x] Un resultat concret et utile (email, document, notification)|
|  [x] Une fiche projet documentee                                 |
|                                                                  |
+------------------------------------------------------------------+
```

**Duree de construction** : 1h30 cet apres-midi (Session 10).

---

### Slide 39 — Exemples de projets par metier

## Inspirations par fonction

| Metier | Projet | Scenario |
|--------|--------|----------|
| **RH** | Tri automatique de CV | Email avec CV --> IA analyse --> Tableau scoring |
| **Comptabilite** | Alerte anomalies | Sheets mis a jour --> IA detecte anomalies --> Email alerte |
| **Commercial** | Prospection personnalisee | CRM nouveau lead --> IA genere email --> Envoi + suivi |
| **Communication** | Veille concurrentielle | RSS actualites --> IA resume --> Digest Slack |
| **Assistanat** | Compte rendu automatique | Notes brutes --> IA structure --> Document formate |
| **Juridique** | Analyse de contrats | Nouveau PDF Drive --> IA extrait points cles --> Fiche synthese |
| **Marketing** | Reponses reseaux sociaux | Nouveau commentaire --> IA propose reponse --> Validation |

---

### Slide 40 — Temps de conception sur papier

## Concevez votre projet (15 min)

**Remplissez cette fiche de conception :**

```
MON PROJET D'AUTOMATISATION IA
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

1. NOM DU PROJET : ________________________________________

2. PROBLEME A RESOUDRE :
   Quelle tache repetitive voulez-vous automatiser ?
   ________________________________________________________

3. SCENARIO (schema) :
   [Trigger] --> [Etape 2] --> [Etape IA] --> [Action finale]
   _________    __________    ___________    ________________

4. OUTILS NECESSAIRES :
   [ ] Google Sheets   [ ] Gmail        [ ] Google Drive
   [ ] OpenAI API      [ ] Slack        [ ] Autre : ______

5. RESULTAT ATTENDU :
   Que produit votre scenario ? _____________________________

6. TEMPS GAGNE ESTIME : _____ min/semaine
```

---

### Slide 41 — Validation avec le formateur

## Validation de votre projet (15 min)

**Le formateur passe voir chaque participant pour :**

1. **Verifier la faisabilite** : est-ce realisable en 1h30 ?
2. **Ajuster la complexite** : simplifier si trop ambitieux, enrichir si trop simple
3. **Valider le choix d'outils** : les modules Make necessaires existent-ils ?
4. **Conseiller** : suggestions de modules ou approches alternatives

**Criteres de validation :**
- Le projet est **realiste** en 1h30
- Il integre **au moins 1 etape IA**
- Il a une **utilite concrete** pour votre metier
- La conception sur papier est **claire et complete**

---

### Slide 42 — Niveaux de difficulte

## Adaptez votre projet a votre niveau

```
NIVEAU 1 — DEBUTANT (3 modules)
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
[Trigger simple] --> [IA genere du texte] --> [Sauvegarde resultat]
Exemple : Sheets --> Resume IA --> Email

NIVEAU 2 — INTERMEDIAIRE (4-5 modules)
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
[Trigger] --> [Filtre] --> [IA] --> [Action 1] --> [Action 2]
Exemple : Form --> Filtre urgence --> IA categorise --> Email + Sheets

NIVEAU 3 — AVANCE (6+ modules)
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
[Trigger] --> [Iteration] --> [IA] --> [Filtre] --> [Actions multiples]
Exemple : Sheets (50 lignes) --> Pour chaque --> IA personnalise --> Email + MAJ Sheets
```

Choisissez le niveau qui vous correspond. Le formateur vous aidera a ajuster.

---

### Slide 43 — Recapitulatif de la matinee

## Ce que vous avez appris ce matin

```
+------------------------------------------------------------------+
|                                                                  |
|  [x] Concepts d'automatisation : trigger, action, filtre        |
|  [x] Presentation de Make (ex-Integromat)                       |
|  [x] Premier scenario : formulaire --> Sheets --> email          |
|  [x] APIs expliquees (analogie du restaurant)                   |
|  [x] Module HTTP dans Make pour appeler OpenAI                   |
|  [x] Scenario IA : Sheets --> API OpenAI --> email personnalise  |
|  [x] Scenario IA : Drive --> resume IA --> sauvegarde            |
|  [x] Conception de votre mini-projet sur papier                  |
|                                                                  |
+------------------------------------------------------------------+
```

---

### Slide 44 — Programme de l'apres-midi

## Cet apres-midi : construction et presentations

```
SESSION 10 — APRES-MIDI
~~~~~~~~~~~~~~~~~~~~~~~~

14h00 - 15h30 : Construction du projet (1h30)
                Vous codez votre scenario dans Make
                Le formateur vous accompagne

15h30 - 16h00 : Documentation (30 min)
                Fiche projet a remplir

16h00 - 17h00 : Presentations orales (1h00)
                3 min par personne + feedback

17h00 - 17h30 : Evaluation finale et cloture (30 min)
                QCM + auto-evaluation + attestation
```

**Bon appetit et a cet apres-midi pour le grand final !**

---

### Slide 45 — Checklist pour cet apres-midi

## Avant de partir en pause dejeuner

**Verifiez que vous avez :**

- [ ] Votre fiche de conception validee par le formateur
- [ ] Votre compte Make fonctionnel
- [ ] Votre cle API OpenAI (ou celle du formateur)
- [ ] Les fichiers necessaires (Sheets, Drive) prepares
- [ ] Une idee claire de votre scenario en 3+ etapes

**Si quelque chose manque** : profitez de la pause pour le preparer.

A tout a l'heure !

---

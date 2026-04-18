# Formation IA pour les Métiers du Tertiaire — Exercices pratiques — Session 9

# FICHE 42 — 3 Scénarios Make avec IA

---

## Scénario 1 — Niveau : Débutant — Enrichissement automatique de leads

### Objectif

Quand une nouvelle ligne est ajoutée dans Google Sheets (nom d'entreprise, contact, email), un appel à l'API OpenAI génère un résumé de l'entreprise et une suggestion d'approche commerciale. Le résultat est écrit automatiquement dans le tableur.

### Schéma du workflow

```
+-------------------+       +-------------------+       +-------------------+
|                   |       |                   |       |                   |
|  Google Sheets    |------>|  HTTP Request     |------>|  Google Sheets    |
|  Watch New Rows   |       |  (API OpenAI)     |       |  Update a Row     |
|                   |       |                   |       |                   |
+-------------------+       +-------------------+       +-------------------+
     TRIGGER                     TRAITEMENT IA              ACTION
```

### Modules Make utilisés

| # | Module | Action |
|---|--------|--------|
| 1 | Google Sheets | Watch New Rows (trigger) |
| 2 | HTTP | Make a request (appel API OpenAI) |
| 3 | Google Sheets | Update a Row |

### Prérequis

- Un Google Sheet avec les colonnes suivantes :

| A - Entreprise | B - Contact | C - Email | D - Résumé IA | E - Approche suggérée |
|----------------|-------------|-----------|---------------|----------------------|
| Decathlon | Marie Durand | m.durand@decathlon.fr | *(à remplir par l'IA)* | *(à remplir par l'IA)* |

### Pas-à-pas détaillé

#### Étape 1 — Module Google Sheets : Watch New Rows

1. Créez un nouveau scénario dans Make
2. Ajoutez le module **Google Sheets → Watch New Rows**
3. Sélectionnez votre connexion Google
4. Choisissez votre spreadsheet et votre feuille
5. "Contains headers" → **Yes**

#### Étape 2 — Module HTTP : Make a request (API OpenAI)

1. Ajoutez un module **HTTP → Make a request**
2. Configurez comme suit :

| Paramètre | Valeur |
|-----------|--------|
| **URL** | `https://api.openai.com/v1/chat/completions` |
| **Method** | POST |
| **Headers** | Header 1 : `Authorization` = `Bearer sk-VOTRE_CLE_API` |
| | Header 2 : `Content-Type` = `application/json` |

3. **Body type** : Raw
4. **Content type** : JSON (application/json)
5. **Request content** (copiez et adaptez) :

```json
{
  "model": "gpt-4o-mini",
  "messages": [
    {
      "role": "system",
      "content": "Tu es un expert en développement commercial B2B. Tu fournis des analyses concises et des recommandations actionnables."
    },
    {
      "role": "user",
      "content": "Voici une entreprise prospect :\n- Nom : {{1.Entreprise}}\n- Contact : {{1.Contact}}\n- Email : {{1.Email}}\n\nFais deux choses :\n1. RÉSUMÉ : En 2-3 phrases, décris l'activité de cette entreprise et son positionnement marché.\n2. APPROCHE : Suggère une approche commerciale personnalisée en 2-3 phrases (angle d'accroche, bénéfice clé à mettre en avant).\n\nFormat de réponse :\nRÉSUMÉ : [ton résumé]\nAPPROCHE : [ta suggestion]"
    }
  ],
  "temperature": 0.7,
  "max_tokens": 300
}
```

> **Note** : Les `{{1.Entreprise}}`, `{{1.Contact}}` et `{{1.Email}}` sont les variables Make issues du module 1 (Google Sheets). Dans l'interface Make, vous les insérerez en cliquant sur les pastilles du module précédent.

6. Cochez **"Parse response"** pour que Make décompose automatiquement la réponse JSON

#### Étape 3 — Module Google Sheets : Update a Row

1. Ajoutez un module **Google Sheets → Update a Row**
2. Sélectionnez le même spreadsheet et la même feuille
3. **Row number** : mappez le numéro de ligne du module 1 (Watch New Rows)
4. **Colonne D (Résumé IA)** : mappez la réponse de l'API

   Chemin dans la réponse JSON :
   ```
   {{2.data.choices[].message.content}}
   ```

   > Vous pouvez aussi utiliser un module **Text Parser** entre les deux pour séparer le RÉSUMÉ et l'APPROCHE, ou simplement mettre la réponse complète en colonne D.

5. **Colonne E (Approche suggérée)** : si vous avez séparé les données, mappez la partie APPROCHE. Sinon, laissez vide.

#### Étape 4 — Tester

1. Ajoutez une nouvelle ligne dans votre Google Sheet
2. Revenez dans Make et cliquez sur **"Run once"**
3. Vérifiez que les colonnes D et E sont remplies

### Points de vigilance

- Le modèle `gpt-4o-mini` est recommandé pour les exercices (moins cher que `gpt-4o`)
- La clé API ne doit jamais être partagée (voir FICHE-45)
- Si l'entreprise n'est pas connue de l'IA, le résumé sera générique : c'est normal
- Le champ `max_tokens` limite la longueur de la réponse (300 tokens ~ 200 mots)

### Extensions possibles

- Ajouter un filtre : ne traiter que les lignes où la colonne D est vide
- Ajouter un module Slack pour notifier l'équipe commerciale
- Stocker les résultats dans un CRM (HubSpot, Pipedrive) en plus du tableur

---

## Scénario 2 — Niveau : Intermédiaire — Réponse automatique aux emails de réclamation

### Objectif

Quand un email de réclamation arrive, l'IA analyse le sentiment, rédige un brouillon de réponse empathique, et alerte le manager si le sentiment est très négatif.

### Schéma du workflow

```
+------------------+     +------------------+     +------------------+
|                  |     |                  |     |                  |
|  Gmail           |---->|  HTTP Request    |---->|  Router          |
|  Watch Emails    |     |  (API Claude)    |     |  (Embranchement) |
|  Filtre:         |     |                  |     |                  |
|  "réclamation"   |     +------------------+     +--------+---------+
|  ou "plainte"    |                                       |
+------------------+                                       |
                                              +------------+------------+
                                              |                         |
                                    +---------v--------+      +---------v--------+
                                    |                  |      |                  |
                                    |  Gmail           |      |  Email/Slack     |
                                    |  Create Draft    |      |  Alerte Manager  |
                                    |  (brouillon)     |      |  (si négatif     |
                                    |                  |      |   fort)          |
                                    +------------------+      +------------------+
                                      ROUTE 1 : Toujours       ROUTE 2 : Si négatif
```

### Modules Make utilisés

| # | Module | Action |
|---|--------|--------|
| 1 | Gmail | Watch Emails (trigger avec filtre) |
| 2 | HTTP | Make a request (API Anthropic Claude) |
| 3 | Router | Embranchement conditionnel |
| 3a | Gmail | Create a Draft (brouillon de réponse) |
| 3b | Email ou Slack | Alerte au manager (route conditionnelle) |

### Instructions de configuration

#### Étape 1 — Gmail : Watch Emails

- Configurez le trigger Gmail pour surveiller les nouveaux emails
- **A vous de trouver** : comment ajouter un filtre pour ne capter que les emails contenant "réclamation" ou "plainte" dans le sujet ou le corps ?
  - Indice : regardez le champ "Search criteria" ou ajoutez un module Filter après le trigger

#### Étape 2 — HTTP : Appel API Anthropic (Claude)

Configuration du module HTTP :

| Paramètre | Valeur |
|-----------|--------|
| **URL** | `https://api.anthropic.com/v1/messages` |
| **Method** | POST |
| **Headers** | `x-api-key` = `VOTRE_CLE_API_ANTHROPIC` |
| | `anthropic-version` = `2023-06-01` |
| | `Content-Type` = `application/json` |

**Body** :

```json
{
  "model": "claude-sonnet-4-20250514",
  "max_tokens": 500,
  "messages": [
    {
      "role": "user",
      "content": "Voici un email de réclamation client :\n\nExpéditeur : {{1.from}}\nObjet : {{1.subject}}\nContenu : {{1.textContent}}\n\nAnalyse cet email et fournis :\n1. SENTIMENT : note de 1 (très négatif) à 5 (neutre/positif)\n2. RÉSUMÉ : résumé du problème en 1 phrase\n3. RÉPONSE : brouillon de réponse empathique et professionnelle (5-8 lignes)\n\nFormat strict :\nSENTIMENT: [chiffre]\nRÉSUMÉ: [résumé]\nRÉPONSE: [texte de la réponse]"
    }
  ]
}
```

#### Étape 3 — Router (embranchement)

- **A vous de trouver** : ajoutez un module **Router** après le module HTTP
- **Route 1** (toujours active) : vers Gmail → Create a Draft
- **Route 2** (conditionnelle) : vers Email/Slack pour alerter le manager
  - Indice : utilisez un filtre sur la route 2. La condition doit vérifier si le SENTIMENT est 1 ou 2. Vous pouvez utiliser le module **Text Parser** pour extraire le chiffre, ou faire une condition sur la présence de "SENTIMENT: 1" ou "SENTIMENT: 2" dans la réponse.

#### Étape 4 — Gmail : Create a Draft

- **A vous de trouver** : configurez le module pour créer un brouillon de réponse
- Le destinataire doit être l'expéditeur de l'email original
- L'objet doit commencer par "Re: " suivi de l'objet original
- Le corps doit contenir la RÉPONSE générée par l'IA

#### Étape 5 — Alerte Manager (route conditionnelle)

- Envoyez un email ou un message Slack au manager
- Incluez : l'expéditeur original, le résumé du problème, le score de sentiment

### Points de vigilance

- Les brouillons doivent toujours être **relus par un humain** avant envoi
- L'analyse de sentiment par l'IA n'est pas parfaite : calibrez sur des exemples réels
- Pensez à la confidentialité des données clients envoyées à l'API
- Le filtre Gmail peut aussi utiliser les libellés/labels pour plus de précision

### Extensions possibles

- Ajouter une catégorisation automatique (produit, livraison, facturation, SAV...)
- Logger toutes les réclamations dans un Google Sheet de suivi
- Ajouter un module de traduction si les réclamations arrivent en plusieurs langues

---

## Scénario 3 — Niveau : Avancé — Pipeline de contenu marketing

### Objectif

Quand un sujet d'article est soumis via Google Forms, l'IA génère automatiquement un article de blog, un post LinkedIn et un objet d'email newsletter. Tous les contenus sont stockés dans Google Docs et Google Sheets.

### Schéma du workflow

```
+------------------+     +------------------+     +------------------+
|                  |     |                  |     |                  |
|  Google Forms    |---->|  HTTP Request    |---->|  HTTP Request    |
|  Watch Responses |     |  API : Article   |     |  API : Post      |
|                  |     |  de blog         |     |  LinkedIn        |
+------------------+     +------------------+     +--------+---------+
                                                           |
                              +----------------------------+
                              |
                    +---------v--------+     +------------------+     +------------------+
                    |                  |     |                  |     |                  |
                    |  HTTP Request    |---->|  Google Docs     |---->|  Google Sheets   |
                    |  API : Objet     |     |  Create Document |     |  Add a Row       |
                    |  email           |     |  (article)       |     |  (tous contenus) |
                    +------------------+     +------------------+     +------------------+
```

### Modules Make utilisés

| # | Module | Action |
|---|--------|--------|
| 1 | Google Forms | Watch Responses (trigger) |
| 2 | HTTP | Make a request — Génération article (API OpenAI) |
| 3 | HTTP | Make a request — Génération post LinkedIn (API OpenAI) |
| 4 | HTTP | Make a request — Génération objet email (API OpenAI) |
| 5 | Google Docs | Create a Document (avec l'article complet) |
| 6 | Google Sheets | Add a Row (récapitulatif de tous les contenus) |

### Grandes étapes (à construire par l'apprenant)

#### Étape 1 — Préparer les outils

- Créez un Google Form avec les champs :
  - Sujet de l'article (texte court)
  - Audience cible (choix : Professionnels / Grand public / Étudiants)
  - Ton souhaité (choix : Formel / Décontracté / Expert)
  - Mots-clés (texte long, optionnel)

- Créez un Google Sheet "Pipeline Contenu" avec les colonnes :
  - Date | Sujet | Article (lien Google Doc) | Post LinkedIn | Objet Email | Statut

#### Étape 2 — Module 1 : Trigger Google Forms

- Configurez le module Google Forms pour surveiller les nouvelles réponses
- Mappez les champs du formulaire

#### Étape 3 — Module 2 : Génération de l'article de blog

Appel API OpenAI. Voici les **éléments à intégrer dans le prompt** :

- Rôle système : rédacteur de contenu professionnel
- Instructions : rédiger un article de blog de 800 mots environ
- Inclure : le sujet, l'audience cible, le ton, les mots-clés issus du formulaire
- Structure demandée : titre, introduction, 3-4 sous-sections, conclusion avec call-to-action
- `max_tokens` : 1500 (environ 800-1000 mots)

> **A vous de construire le prompt complet et le JSON du body.**

#### Étape 4 — Module 3 : Génération du post LinkedIn

- Nouveau appel API avec un prompt différent
- Demander un post LinkedIn de 150-200 mots
- Inclure des emojis pertinents et un call-to-action
- Le post doit être cohérent avec l'article généré
- **Astuce** : passez le résumé de l'article (pas l'article entier) comme contexte

#### Étape 5 — Module 4 : Génération de l'objet email

- Appel API pour générer 3 propositions d'objets d'email newsletter
- Court, accrocheur, moins de 60 caractères chacun
- Un objet informatif, un curieux, un urgent

#### Étape 6 — Module 5 : Création du Google Doc

- Créez un document Google Docs avec l'article complet
- Titre du document : `[Date] - Article - [Sujet]`
- **A vous de trouver** quel module Make utiliser et comment mapper le contenu

#### Étape 7 — Module 6 : Ajout dans Google Sheets

- Ajoutez une ligne dans le tableur récapitulatif avec :
  - Date du jour
  - Sujet (issu du formulaire)
  - Lien vers le Google Doc créé
  - Post LinkedIn (texte complet)
  - Objets email (les 3 propositions)
  - Statut : "A relire"

### Points de vigilance

- Enchaîner 3 appels API dans un même scénario consomme 3 opérations + les modules Google = 5-6 opérations par exécution
- Utilisez `gpt-4o-mini` pour réduire les coûts (un article ~ 0.01-0.03$)
- Les contenus générés doivent impérativement être **relus et ajustés** avant publication
- Attention au `max_tokens` : trop bas = article tronqué, trop haut = coûts inutiles
- Gérez les erreurs : ajoutez un module d'alerte email si un appel API échoue

### Extensions possibles

- Ajouter la génération d'une image avec l'API DALL-E pour illustrer l'article
- Intégrer la publication directe sur WordPress via son API
- Ajouter un module de traduction pour créer les versions EN/ES du contenu
- Programmer la publication LinkedIn via l'API LinkedIn (nécessite un compte développeur)
- Ajouter une étape de validation humaine (email au manager avec bouton "Approuver")

---

## Récapitulatif des 3 scénarios

| Scénario | Niveau | Modules | Opérations/exécution | Compétences travaillées |
|----------|--------|---------|---------------------|------------------------|
| 1. Enrichissement leads | Débutant | 3 | 3 | Trigger, HTTP, mapping basique |
| 2. Réponse réclamation | Intermédiaire | 5 | 5 | Router, filtres, parsing texte |
| 3. Pipeline contenu | Avancé | 6 | 6 | Chaînage API, Google Docs, autonomie |

> **Conseil** : Commencez toujours par le scénario 1 pour bien maîtriser les bases avant de passer aux suivants. N'hésitez pas à tester chaque module individuellement avec "Run once" avant de lancer le scénario complet.

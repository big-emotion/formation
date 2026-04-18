# Formation IA pour les Métiers du Tertiaire — Fiche de référence — Session 9

# FICHE 41 — Les APIs Expliquées Simplement

---

## 1. L'analogie du restaurant

> **Imaginez que vous êtes au restaurant :**
>
> | Au restaurant | Dans le monde des APIs |
> |---------------|----------------------|
> | **Vous** (le client) | Votre application (Make, un site web, un script...) |
> | **Le menu** | La **documentation** de l'API (ce que vous pouvez demander) |
> | **Le serveur** | L'**API** elle-même (l'intermédiaire qui transmet votre demande) |
> | **La cuisine** | Le **serveur/service** distant (là où le travail se fait réellement) |
> | **Votre commande** | La **requête** (request) que vous envoyez |
> | **Votre plat** | La **réponse** (response) que vous recevez |
> | **Votre numéro de table** | Votre **clé API** (pour vous identifier et vous authentifier) |
>
> Vous n'avez pas besoin de savoir comment la cuisine fonctionne. Vous passez commande via le serveur, et vous recevez votre plat. C'est exactement le principe d'une API.

---

## 2. Définition technique accessible

**API** signifie **Application Programming Interface** (Interface de Programmation d'Application).

En termes simples : une API est une **interface qui permet à deux logiciels de communiquer entre eux**, sans que vous ayez besoin de savoir comment ils fonctionnent en interne.

Quand vous demandez à ChatGPT de rédiger un texte via Make, voici ce qui se passe :
1. Make envoie votre demande (le prompt) à l'API OpenAI
2. L'API traite la demande côté serveur OpenAI
3. L'API renvoie la réponse (le texte généré) à Make
4. Make utilise cette réponse dans la suite du workflow

**Vous n'avez pas besoin de coder.** Make se charge d'envoyer et de recevoir les données. Vous configurez simplement les bons paramètres.

---

## 3. Les 4 types de requêtes (verbes HTTP)

Quand vous communiquez avec une API, vous utilisez un **verbe HTTP** qui indique ce que vous voulez faire :

| Verbe | Signification | Analogie | Exemple concret |
|-------|--------------|----------|-----------------|
| **GET** | "Donne-moi des informations" | Consulter le menu | Récupérer la liste des emails non lus |
| **POST** | "Crée quelque chose de nouveau" | Passer une commande | Envoyer un prompt à ChatGPT et obtenir une réponse |
| **PUT** | "Modifie cette chose existante" | Changer sa commande | Mettre à jour le statut d'un contact dans un CRM |
| **DELETE** | "Supprime cette chose" | Annuler sa commande | Supprimer une tâche terminée |

> **En pratique dans cette formation** : vous utiliserez principalement **POST** pour envoyer des prompts aux APIs d'IA (OpenAI, Anthropic) et recevoir des réponses.

---

## 4. Anatomie d'un appel API

### Schéma ASCII

```
VOTRE APPLICATION (Make)                          SERVEUR DISTANT (OpenAI)
+-------------------------+                       +------------------------+
|                         |   --- REQUÊTE --->    |                        |
|  1. URL (endpoint)      |                       |   Le serveur traite    |
|  2. Méthode (POST)      |                       |   votre demande        |
|  3. Headers             |                       |                        |
|     - Clé API           |                       |                        |
|     - Type de contenu   |   <--- RÉPONSE ---    |                        |
|  4. Body (données)      |                       |   Il renvoie le        |
|                         |                       |   résultat             |
+-------------------------+                       +------------------------+
```

### Les composants détaillés

**A. URL de base (Endpoint)**

C'est l'adresse à laquelle vous envoyez votre requête.

```
https://api.openai.com/v1/chat/completions
```

- `https://api.openai.com` = le serveur
- `/v1` = la version de l'API
- `/chat/completions` = la ressource spécifique (ici, la génération de texte)

**B. Headers (en-têtes)**

Les informations complémentaires envoyées avec votre requête :

```
Authorization: Bearer sk-xxxxxxxxxxxxxxxxxxxxx
Content-Type: application/json
```

- `Authorization` : votre clé API (comme un badge d'accès)
- `Content-Type` : le format des données envoyées (JSON = format texte structuré)

**C. Body (corps de la requête)**

Les données que vous envoyez. En JSON :

```json
{
  "model": "gpt-4o-mini",
  "messages": [
    {
      "role": "user",
      "content": "Résume ce texte en 3 points clés : ..."
    }
  ],
  "temperature": 0.7
}
```

**D. Réponse**

Ce que le serveur vous renvoie :

| Code HTTP | Signification | Que faire ? |
|-----------|--------------|-------------|
| **200** | OK, tout s'est bien passé | Récupérer les données de la réponse |
| **400** | Erreur client (mauvaise requête) | Vérifier votre JSON, vos paramètres |
| **401** | Non autorisé | Vérifier votre clé API |
| **403** | Interdit | Vous n'avez pas accès à cette ressource |
| **429** | Trop de requêtes | Attendre un peu, vous avez dépassé la limite |
| **500** | Erreur serveur | Le service distant a un problème, réessayer plus tard |

---

## 5. Exemple concret avec l'API OpenAI

Voici un appel complet, tel que vous le configureriez dans Make :

### Requête

```
POST https://api.openai.com/v1/chat/completions

Headers:
  Authorization: Bearer sk-xxxxxxxxxxxxxxxxxxxxxxxx
  Content-Type: application/json

Body:
{
  "model": "gpt-4o-mini",
  "messages": [
    {
      "role": "system",
      "content": "Tu es un assistant professionnel spécialisé en relation client."
    },
    {
      "role": "user",
      "content": "Bonjour, pouvez-vous m'aider ?"
    }
  ],
  "temperature": 0.7,
  "max_tokens": 500
}
```

### Réponse (simplifiée)

```json
{
  "id": "chatcmpl-abc123",
  "choices": [
    {
      "message": {
        "role": "assistant",
        "content": "Bonjour ! Bien sûr, je suis là pour vous aider. Comment puis-je vous assister aujourd'hui ?"
      }
    }
  ],
  "usage": {
    "prompt_tokens": 35,
    "completion_tokens": 22,
    "total_tokens": 57
  }
}
```

> **Ce qui vous intéresse** : le contenu se trouve dans `choices[0].message.content`. C'est ce chemin que vous utiliserez dans Make pour extraire la réponse de l'IA.

---

## 6. Pourquoi c'est utile pour vous

| Cas d'usage | Ce que l'API permet |
|-------------|-------------------|
| **Automatiser des appels à ChatGPT/Claude depuis Make** | Envoyer un prompt et récupérer la réponse sans ouvrir le navigateur |
| **Connecter des outils entre eux** | Quand un outil n'a pas d'intégration native dans Make, l'API est le pont universel |
| **Créer des workflows sur mesure** | Enchaîner plusieurs appels IA dans un même scénario (analyser, puis résumer, puis rédiger) |
| **Traiter des volumes** | Traiter 100 lignes d'un tableur automatiquement, là où vous feriez 100 copier-coller manuels |
| **Personnaliser les réponses** | Adapter le prompt à chaque situation grâce aux variables Make |

---

## 7. Sécurité des clés API

Les clés API sont comme des **mots de passe** donnant accès à des services payants. Quelques règles essentielles :

| Règle | Pourquoi | Comment |
|-------|----------|---------|
| **Ne jamais partager sa clé API** | Quelqu'un pourrait l'utiliser et vous seriez facturé | Ne pas la mettre dans un email, un Google Doc partagé, un chat |
| **Ne pas mettre la clé dans le code visible** | Elle pourrait fuiter sur internet | Utiliser les variables d'environnement ou le coffre-fort Make |
| **Surveiller sa consommation** | Pour éviter les mauvaises surprises sur la facture | Consulter le dashboard OpenAI : platform.openai.com/usage |
| **Mettre une limite de dépense** | Plafonner les coûts en cas d'erreur ou d'abus | Settings → Billing → Usage limits sur OpenAI |
| **Supprimer les clés inutilisées** | Réduire les risques si une clé est compromise | Faire le ménage régulièrement dans Settings → API Keys |

> **En résumé** : une API est simplement un moyen pour deux logiciels de se parler. Avec Make, vous configurez visuellement ces échanges sans coder. Dans la fiche suivante (FICHE-42), vous mettrez cela en pratique avec de vrais scénarios intégrant l'IA.

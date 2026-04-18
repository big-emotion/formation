# Formation IA pour les Métiers du Tertiaire — Fiche formateur — Session 9

# FICHE 45 — Clés API et Comptes de Test : Guide de Préparation

---

> **IMPORTANT** : Cette fiche ne contient PAS de vraies clés API. Elle contient les **instructions** pour que le formateur prépare les comptes et les accès avant la session. Toutes les clés API sont des exemples fictifs.

---

## 1. Checklist de préparation (à faire 1 semaine avant la formation)

### Comptes et accès

- [ ] **Créer un compte OpenAI** avec crédits prépayés
  - Aller sur https://platform.openai.com
  - Créer un compte ou se connecter
  - Aller dans Settings > Billing > Add payment method
  - Ajouter un crédit de **20 $** (suffisant pour ~12 participants sur une session)
  - Activer le "Usage limit" à 25 $ (marge de sécurité)

- [ ] **Générer une clé API OpenAI**
  - Aller dans Settings > API Keys
  - Cliquer sur "Create new secret key"
  - Nommer la clé : `Formation-Session9-[DATE]`
  - **Copier immédiatement la clé** (elle ne sera plus visible ensuite)
  - La stocker dans un gestionnaire de mots de passe (JAMAIS dans un email ou document partagé)

- [ ] **Créer un compte Make** (gratuit)
  - Option A : **1 compte par participant** (recommandé) — chaque participant crée son compte en début de session
  - Option B : **1 compte formateur** en démonstration — le formateur projette son écran
  - Si option A : préparer un guide rapide d'inscription (voir FICHE-40)

- [ ] **Préparer un Google Sheet partagé** avec données de test
  - Créer un tableur nommé `Session9_Donnees_Test`
  - Onglet 1 — "Leads" avec les colonnes :
    | Entreprise | Contact | Email | Résumé IA | Approche suggérée |
    |-----------|---------|-------|-----------|-------------------|
    | Decathlon | Marie Durand | test@example.com | | |
    | Leroy Merlin | Pierre Martin | test2@example.com | | |
    | BNP Paribas | Sophie Lambert | test3@example.com | | |
  - Onglet 2 — "Pipeline Contenu" avec les colonnes :
    | Date | Sujet | Lien Article | Post LinkedIn | Objet Email | Statut |
    |------|-------|-------------|---------------|-------------|--------|
  - Partager le tableur en mode "Éditeur" avec les participants (ou utiliser un lien partagé)

- [ ] **Préparer un Google Form de test**
  - Créer un formulaire nommé `Session9_Sujet_Article`
  - Champs : Sujet (texte court), Audience (choix), Ton (choix), Mots-clés (texte long)
  - Lier les réponses au Google Sheet (onglet dédié)

- [ ] **Tester les 3 scénarios de FICHE-42 la veille**
  - Scénario 1 : Enrichissement leads — vérifier que l'API répond correctement
  - Scénario 2 : Réponse réclamation — tester avec un email fictif
  - Scénario 3 : Pipeline contenu — vérifier la création du Google Doc
  - **Objectif** : s'assurer que tout fonctionne et que les crédits API sont suffisants

---

## 2. Configuration de l'API OpenAI dans Make (pas-à-pas)

### Étape 1 — Ajouter le module HTTP

1. Dans votre scénario Make, cliquez sur "+" pour ajouter un module
2. Recherchez **"HTTP"**
3. Sélectionnez **"Make a request"**

### Étape 2 — Configurer la requête

| Champ | Valeur |
|-------|--------|
| **URL** | `https://api.openai.com/v1/chat/completions` |
| **Method** | `POST` |

### Étape 3 — Configurer les Headers

Cliquez sur "Add a header" deux fois :

| Header | Valeur |
|--------|--------|
| `Authorization` | `Bearer sk-xxxxxxxxxxxxxxxxxxxxxxxx` *(remplacer par votre vraie clé)* |
| `Content-Type` | `application/json` |

### Étape 4 — Configurer le Body

- **Body type** : Raw
- **Content type** : JSON (application/json)
- **Request content** :

```json
{
  "model": "gpt-4o-mini",
  "messages": [
    {
      "role": "system",
      "content": "Tu es un assistant professionnel."
    },
    {
      "role": "user",
      "content": "Votre prompt ici avec les {{variables}} Make"
    }
  ],
  "temperature": 0.7,
  "max_tokens": 500
}
```

### Étape 5 — Parser la réponse JSON

1. Cochez l'option **"Parse response"** en bas du module HTTP
2. Cela permet à Make de décomposer la réponse JSON automatiquement
3. Vous pourrez ensuite accéder à :
   - `data.choices[1].message.content` — le texte généré par l'IA
   - `data.usage.total_tokens` — le nombre de tokens consommés

### Schéma récapitulatif de la configuration

```
MODULE HTTP - Make a request
+-------------------------------------------------------+
| URL:     https://api.openai.com/v1/chat/completions   |
| Method:  POST                                          |
|                                                        |
| Headers:                                               |
|   Authorization: Bearer sk-xxxx...                     |
|   Content-Type: application/json                       |
|                                                        |
| Body (Raw JSON):                                       |
|   {                                                    |
|     "model": "gpt-4o-mini",                           |
|     "messages": [...],                                 |
|     "temperature": 0.7,                                |
|     "max_tokens": 500                                  |
|   }                                                    |
|                                                        |
| [x] Parse response                                    |
+-------------------------------------------------------+
         |
         v
  Sortie: data.choices[1].message.content
```

---

## 3. Gestion du budget API

### Coûts estimés par modèle

| Modèle | Coût input (par 1M tokens) | Coût output (par 1M tokens) | Coût moyen par appel |
|--------|---------------------------|----------------------------|---------------------|
| **gpt-4o-mini** (recommandé) | ~0.15 $ | ~0.60 $ | ~0.005 - 0.02 $ |
| gpt-4o | ~2.50 $ | ~10.00 $ | ~0.03 - 0.10 $ |
| gpt-4 | ~30.00 $ | ~60.00 $ | ~0.10 - 0.50 $ |

> **Recommandation** : Utilisez **gpt-4o-mini** pour tous les exercices. La qualité est largement suffisante pour les cas d'usage de la formation, et le coût est 10 à 50 fois inférieur à GPT-4.

### Estimation du budget pour la session

| Activité | Appels estimés | Coût estimé |
|----------|---------------|-------------|
| Démonstrations formateur | ~20 appels | ~0.20 $ |
| Scénario 1 (12 participants x 3 tests) | ~36 appels | ~0.36 $ |
| Scénario 2 (12 participants x 2 tests) | ~24 appels | ~0.48 $ |
| Scénario 3 (12 participants x 3 tests) | ~108 appels (3 appels/exécution) | ~1.08 $ |
| Marge pour erreurs et tests supplémentaires | ~50 appels | ~0.50 $ |
| **TOTAL ESTIMÉ** | **~238 appels** | **~2.62 $** |

> Budget recommandé : **20 $** (large marge de sécurité pour couvrir toutes les sessions de la formation).

### Mettre une limite de dépense

1. Aller sur https://platform.openai.com/settings/organization/limits
2. Définir le **"Monthly budget"** à 25 $
3. Définir un **"Email alert"** à 15 $ (pour être prévenu avant d'atteindre la limite)

---

## 4. Alternative sans API (si budget limité)

Si le budget ne permet pas d'utiliser l'API OpenAI, voici des alternatives :

### Option A — Copier-coller manuel

1. Les apprenants utilisent les **versions gratuites** de ChatGPT ou Claude dans leur navigateur
2. Ils copient le prompt préparé, le collent dans l'interface web, récupèrent la réponse
3. Ils collent la réponse manuellement dans Google Sheets
4. **Avantage** : gratuit
5. **Inconvénient** : pas d'automatisation, l'objectif pédagogique sur Make est partiellement perdu

### Option B — Démo formateur en live

1. Le formateur fait la démonstration en direct sur son écran
2. Les apprenants observent et prennent des notes
3. Ils reproduisent les étapes simples sur leur compte Make (sans API)
4. **Avantage** : ils voient le résultat réel
5. **Inconvénient** : moins d'apprentissage par la pratique

### Option C — Module Make "OpenAI" natif (plus simple que HTTP)

1. Make propose un **module natif OpenAI** (pas besoin de configurer le HTTP manuellement)
2. Ajoutez le module "OpenAI" > "Create a Completion"
3. Entrez simplement votre clé API et votre prompt
4. Make gère automatiquement le formatage de la requête
5. **Avantage** : configuration plus simple, moins d'erreurs
6. **Inconvénient** : moins pédagogique (les apprenants ne voient pas la mécanique API)

### Option D — API gratuite ou low-cost

| Alternative | Avantage | Limitation |
|-------------|----------|-----------|
| **Groq** (gratuit) | API gratuite avec Llama, rapide | Limites de requêtes, modèles open source |
| **Mistral** (tier gratuit) | API française, modèle performant | Nombre d'appels limité sur le tier gratuit |
| **Google Gemini** (tier gratuit) | 60 requêtes/minute gratuites | Nécessite un compte Google Cloud |

---

## 5. Sécurité

### Règles absolues pendant la formation

| Règle | Détail |
|-------|--------|
| **Ne JAMAIS partager la clé API dans un document partagé** | Pas dans le Google Sheet, pas dans le chat, pas dans un email. La clé est projetée uniquement sur l'écran du formateur ou communiquée individuellement. |
| **Ne JAMAIS mettre la clé dans le corps d'un email** | Même un email interne. Utiliser un canal sécurisé si nécessaire. |
| **Supprimer la clé API après la formation** | Aller dans Settings > API Keys > supprimer la clé utilisée. En créer une nouvelle pour la prochaine session. |
| **Surveiller la consommation en temps réel** | Pendant la session, garder un onglet ouvert sur https://platform.openai.com/usage pour vérifier que la consommation reste normale. |
| **Limiter les droits de la clé** | Si possible, créer une clé avec des permissions restreintes (pas d'accès aux modèles les plus chers). |

### Comment distribuer la clé aux participants (si nécessaire)

1. **Méthode recommandée** : projeter la clé à l'écran pendant 2 minutes, les participants la copient dans leur configuration Make
2. **Alternative** : la communiquer oralement, caractère par caractère
3. **A éviter absolument** : l'envoyer par email, la mettre dans un Google Doc partagé, la poster dans un chat de groupe

---

## 6. Troubleshooting : 5 problèmes fréquents et solutions

### Problème 1 — Clé API invalide

**Symptôme** : Erreur 401 "Unauthorized" ou "Invalid API Key"

**Solutions** :
1. Vérifier qu'il n'y a pas d'espace avant ou après la clé lors du copier-coller
2. Vérifier que le header est bien `Authorization: Bearer sk-xxxxx` (avec "Bearer " et un espace)
3. Vérifier que la clé n'a pas été supprimée ou expirée sur platform.openai.com
4. Créer une nouvelle clé si le problème persiste

---

### Problème 2 — Quota dépassé / Insufficient funds

**Symptôme** : Erreur 429 "Rate limit exceeded" ou "You exceeded your current quota"

**Solutions** :
1. Vérifier le solde sur Settings > Billing > Usage
2. Ajouter des crédits si nécessaire
3. Si c'est un rate limit (trop de requêtes en même temps) : attendre 60 secondes et réessayer
4. Réduire le `max_tokens` dans les appels pour consommer moins
5. Passer de `gpt-4o` à `gpt-4o-mini` si ce n'est pas déjà fait

---

### Problème 3 — Erreur JSON (Invalid JSON)

**Symptôme** : Erreur 400 "Invalid JSON" ou "Could not parse JSON body"

**Solutions** :
1. Vérifier que toutes les chaînes sont entre **guillemets doubles** `"..."` (pas de guillemets simples)
2. Vérifier qu'il n'y a **pas de virgule après le dernier élément** d'un objet ou d'un tableau
3. Vérifier que les accolades et crochets sont bien fermés
4. Utiliser un validateur JSON en ligne : https://jsonlint.com
5. Vérifier que les variables Make ({{...}}) ne contiennent pas de guillemets ou de caractères spéciaux qui cassent le JSON
6. **Astuce** : si le contenu d'une variable contient des guillemets, utilisez la fonction Make `replace` pour les échapper

**Exemple d'erreur fréquente** :
```json
{
  "messages": [
    {"role": "user", "content": "Analyse : {{1.contenu}}"}
  ],
}
```
Le problème : la virgule `,` après `]` est en trop. Et si `{{1.contenu}}` contient des guillemets `"`, cela cassera le JSON.

---

### Problème 4 — Timeout (délai dépassé)

**Symptôme** : Erreur "Request timed out" ou le module HTTP reste en chargement

**Solutions** :
1. Augmenter le timeout dans les paramètres du module HTTP Make (par défaut : 40 secondes)
   - Cliquez sur la clé à molette du module > "Timeout" > mettre 120 secondes
2. Réduire le `max_tokens` (une réponse plus courte est plus rapide)
3. Utiliser `gpt-4o-mini` (plus rapide que `gpt-4o`)
4. Vérifier le statut de l'API OpenAI : https://status.openai.com
5. Réessayer simplement (problème ponctuel côté serveur)

---

### Problème 5 — Réponse vide ou inattendue

**Symptôme** : Le module HTTP renvoie une réponse mais le champ "content" est vide ou ne contient pas ce qui est attendu

**Solutions** :
1. Vérifier que **"Parse response"** est coché dans le module HTTP
2. Vérifier le chemin d'accès à la réponse : `data.choices[1].message.content`
   - Attention : dans Make, l'indexation commence souvent à 1 (pas 0)
3. Cliquer sur la bulle du module HTTP pour inspecter la réponse brute
4. Vérifier que le prompt est bien formulé et qu'il ne demande pas quelque chose d'impossible
5. Si la réponse est tronquée : augmenter `max_tokens`
6. Vérifier que `temperature` n'est pas à 0 (cela peut donner des réponses très courtes dans certains cas)

---

## Récapitulatif pré-session (jour J)

| Timing | Action du formateur |
|--------|-------------------|
| **J-7** | Créer les comptes, générer la clé API, préparer les Google Sheets/Forms |
| **J-1** | Tester les 3 scénarios de bout en bout. Vérifier les crédits API. |
| **J (matin)** | Ouvrir un onglet sur platform.openai.com/usage pour monitorer. Préparer la clé API pour la projeter. |
| **Pendant la session** | Surveiller la consommation toutes les 30 minutes. Être prêt à basculer sur les alternatives (section 4) en cas de problème. |
| **Après la session** | Supprimer la clé API utilisée. Noter le coût réel pour le budget des prochaines sessions. |

---

> **Note finale** : La préparation technique est la clé du succès de cette session. Un formateur qui a testé les scénarios la veille pourra résoudre 90 % des problèmes des apprenants en quelques secondes. Prévoyez 1h de préparation technique la veille de la session.

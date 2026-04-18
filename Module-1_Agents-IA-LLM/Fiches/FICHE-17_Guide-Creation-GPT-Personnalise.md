# FICHE-17 — Guide de Création d'un GPT Personnalisé (ChatGPT)

> **Formation IA pour les Métiers du Tertiaire**
> Guide pas-à-pas — Session 5 (3 pages)

---

## Qu'est-ce qu'un GPT personnalisé ?

Un GPT personnalisé est une version de ChatGPT configurée pour une tâche spécifique avec :
- Des **instructions permanentes** (sa "fiche de poste")
- Des **documents de référence** (sa "bibliothèque")
- Des **capacités** activées/désactivées (recherche web, analyse de code, génération d'images)

**Prérequis :** Compte ChatGPT Plus (20€/mois) ou Team/Enterprise

---

## Étape 1 : Accéder au GPT Builder

1. Connectez-vous sur **chat.openai.com**
2. Dans la barre latérale gauche, cliquez sur **"Explorer les GPTs"**
3. En haut à droite, cliquez sur **"+ Créer"**
4. Vous arrivez sur le **GPT Builder** avec 2 onglets :
   - **Créer** : mode conversation (l'IA vous guide)
   - **Configurer** : mode manuel (vous remplissez les champs)

> **Recommandation :** Utilisez l'onglet **"Configurer"** pour plus de contrôle.

---

## Étape 2 : Configurer les paramètres de base

### Nom
Donnez un nom clair et descriptif.
- ✅ "Assistant FAQ RH — Convention Syntec"
- ✅ "Rédacteur LinkedIn B2B — TechSolutions"
- ❌ "Mon GPT" (trop vague)

### Description
1-2 phrases expliquant ce que fait le GPT.
> "Répond aux questions des salariés sur la convention collective Syntec, les congés, le télétravail et les avantages sociaux."

### Photo
Uploadez un logo ou une icône, ou laissez l'IA en générer un.

---

## Étape 3 : Rédiger les instructions

C'est la partie la plus importante. Les instructions définissent le comportement permanent de votre GPT.

### Structure recommandée :

```
## Identité
Tu es [rôle], spécialisé dans [domaine]. Tu travailles pour [contexte].

## Mission
Ta mission est de [objectif principal]. Tu aides les [public cible] à [bénéfice].

## Règles de comportement
- Tu réponds TOUJOURS en français
- Tu utilises un ton [ton souhaité]
- Tu structures tes réponses avec [format préféré]
- Tu cites tes sources quand tu utilises les documents uploadés

## Ce que tu fais
- [Liste des tâches autorisées]

## Ce que tu ne fais PAS
- [Liste des interdictions]
- Tu ne donnes JAMAIS de conseil juridique définitif
- Tu ne partages JAMAIS de données personnelles
- Tu recommandes de consulter [expert] pour les cas complexes

## Format de réponse
- Commence par un résumé en 1-2 phrases
- Développe avec des puces ou des paragraphes courts
- Termine par "Sources : [document, page/section]" quand applicable
```

---

### Exemple complet : GPT "Assistant FAQ RH"

```
## Identité
Tu es un assistant RH expert, spécialisé dans la convention collective
Syntec et le droit du travail français. Tu travailles pour l'entreprise
TechConseil, ESN de 120 salariés basée à Paris.

## Mission
Ta mission est de répondre aux questions des salariés sur leurs droits,
les procédures internes et la convention collective. Tu les aides à
comprendre leurs droits de manière claire et accessible.

## Règles de comportement
- Tu réponds TOUJOURS en français
- Tu utilises un ton professionnel, bienveillant et pédagogique
- Tu vulgarises le jargon juridique
- Tu cites systématiquement l'article ou la section du document source

## Ce que tu fais
- Répondre aux questions sur les congés, RTT, arrêts maladie
- Expliquer les dispositions de la convention Syntec
- Clarifier les procédures internes (télétravail, notes de frais, formation)
- Calculer des droits (jours de congés, préavis, ancienneté)

## Ce que tu ne fais PAS
- Tu ne donnes JAMAIS de conseil juridique définitif
- Tu ne remplaces PAS le service RH — tu recommandes de les contacter
  pour les situations complexes ou personnelles
- Tu ne traites PAS de données salariales individuelles
- Tu ne prends PAS position sur des litiges

## Format de réponse
- Commence par une réponse directe en 1-2 phrases
- Développe avec les détails pertinents
- Cite la source : "Réf : Convention Syntec, Article X.X" ou
  "Réf : Procédure interne, p.X"
- Termine par "⚠️ Pour votre cas personnel, contactez le service RH"
  si la question est sensible
```

---

## Étape 4 : Uploader les documents de référence

Dans la section **"Connaissances"** (Knowledge), uploadez vos documents.

### Documents à uploader (exemples par métier) :

| Métier | Documents suggérés |
|--------|-------------------|
| **RH** | Convention collective, accord d'entreprise, procédures internes, organigramme, livret d'accueil |
| **Marketing** | Charte éditoriale, guide de marque, personas, historique campagnes |
| **Finance** | Plan comptable, procédures de clôture, modèles de reporting |
| **Commercial** | Grille tarifaire, argumentaire produit, FAQ objections, CRM export |
| **Gestion** | Procédures administratives, templates, organigramme, annuaire |

### Formats acceptés :
PDF, DOCX, TXT, CSV, XLSX, JSON, images (PNG, JPG)

### Conseils :
- **Nommez bien vos fichiers** : "Convention-Syntec-2024.pdf" plutôt que "doc1.pdf"
- **Documents à jour** : assurez-vous que les documents sont les versions actuelles
- **Pas de données personnelles** : anonymisez avant d'uploader
- **Taille max** : environ 20 fichiers, 512 Mo au total

---

## Étape 5 : Configurer les capacités

Activez ou désactivez selon vos besoins :

| Capacité | Quand l'activer | Quand la désactiver |
|----------|----------------|---------------------|
| **Recherche web** | Si le GPT doit chercher des infos à jour | Si les réponses doivent venir uniquement des docs uploadés |
| **DALL-E (images)** | Si le GPT doit créer des visuels | Pour un GPT purement texte |
| **Code Interpreter** | Si le GPT doit analyser des données CSV/Excel | Pour un GPT de rédaction pure |

---

## Étape 6 : Ajouter des amorces de conversation

Ce sont les suggestions affichées quand un utilisateur ouvre le GPT.

### Exemples pour le GPT "Assistant FAQ RH" :
- "Combien de jours de congés ai-je droit avec 3 ans d'ancienneté ?"
- "Quelle est la procédure pour poser un jour de télétravail ?"
- "Comment fonctionne le compte épargne temps ?"
- "Quel est le délai de préavis pour une démission ?"

---

## Étape 7 : Tester et publier

### Tester :
1. Utilisez le panneau de prévisualisation à droite du Builder
2. Posez 5-10 questions types
3. Vérifiez que les réponses sont correctes et cohérentes
4. Ajustez les instructions si nécessaire

### Publier :
- **Seulement pour moi** : usage personnel
- **Avec un lien** : partageable à des personnes spécifiques
- **Public** : visible dans le GPT Store (déconseillé pour un usage interne)

---

## Checklist avant publication

- [ ] Les instructions sont claires et complètes
- [ ] Les documents uploadés sont à jour et anonymisés
- [ ] Les capacités activées correspondent au besoin
- [ ] Les amorces de conversation sont pertinentes
- [ ] J'ai testé avec au moins 10 questions différentes
- [ ] Les réponses citent correctement les sources
- [ ] Le GPT refuse poliment les questions hors périmètre
- [ ] Aucune donnée personnelle ou confidentielle n'est exposée

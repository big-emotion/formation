# FICHE-18 — Guide de Création d'un Claude Project

> **Formation IA pour les Métiers du Tertiaire**
> Guide pas-à-pas — Session 5 (3 pages)

---

## Qu'est-ce qu'un Claude Project ?

Un Project Claude est un espace de travail dédié avec :
- Des **instructions personnalisées** permanentes
- Une **base de connaissances** (vos documents de référence)
- Un **historique** de toutes les conversations du projet
- Un **contexte persistant** : Claude se souvient du projet entre les conversations

**Prérequis :** Compte Claude Pro (20$/mois)

---

## Étape 1 : Créer un nouveau Project

1. Connectez-vous sur **claude.ai**
2. Dans la barre latérale gauche, cliquez sur **"Projects"**
3. Cliquez sur **"+ Create Project"** (Créer un projet)
4. Donnez un **nom** au projet :
   - ✅ "Veille Concurrentielle — Marketing"
   - ✅ "FAQ RH — Convention Collective"
   - ❌ "Projet 1" (trop vague)
5. Ajoutez une **description** (optionnel mais recommandé)

---

## Étape 2 : Rédiger les instructions personnalisées

Cliquez sur **"Set custom instructions"** pour définir le comportement de Claude dans ce projet.

### Structure recommandée :

```
## Ton rôle
Tu es [rôle expert] travaillant pour [entreprise/contexte].
Tu aides [public cible] à [objectif].

## Contexte
[Informations clés sur l'entreprise, le secteur, la situation]

## Documents disponibles
Tu as accès aux documents suivants :
- [Nom du document 1] : [description courte]
- [Nom du document 2] : [description courte]
Utilise-les SYSTÉMATIQUEMENT pour répondre aux questions.

## Règles
- Réponds toujours en français
- Cite tes sources (nom du document, page/section)
- Ton [professionnel/pédagogique/analytique]
- [Autres contraintes spécifiques]

## Format de réponse
[Structure type de tes réponses]
```

---

### Exemple : Project "Veille Concurrentielle Marketing"

```
## Ton rôle
Tu es un analyste en intelligence concurrentielle, spécialisé
dans le secteur des logiciels SaaS B2B. Tu travailles pour
TechSolutions, éditeur d'un outil de tableau de bord pour DAF.

## Contexte
- TechSolutions : 80 salariés, CA 8M€, croissance 25%/an
- Produit : SmartBoard, tableau de bord automatisé pour DAF
- Cible : PME/ETI 50-500 salariés
- Concurrents principaux : DataViz Pro, FinanceCockpit, QuickDash

## Documents disponibles
Tu as accès à :
- Nos fiches produit et argumentaire commercial
- Les pages web de nos concurrents (captures)
- Notre dernière étude de marché
- Nos retours clients (enquête satisfaction)
Base-toi sur ces documents pour tes analyses.

## Règles
- Réponds en français, ton analytique et factuel
- Distingue toujours les FAITS (issus des documents) des
  HYPOTHÈSES (ton analyse)
- Cite tes sources
- Propose toujours des recommandations actionnables

## Ce que tu fais
- Analyser les forces/faiblesses des concurrents
- Identifier des opportunités de différenciation
- Rédiger des fiches concurrentielles
- Proposer des arguments de vente face à chaque concurrent
- Synthétiser les tendances du marché

## Format
- Commence par un "En bref" en 2-3 phrases
- Développe avec des tableaux comparatifs quand possible
- Termine par "Recommandations" en 3 points max
```

---

## Étape 3 : Uploader les documents

Dans la section **"Project knowledge"**, uploadez vos fichiers.

### Comment uploader :
1. Cliquez sur **"Add content"** dans la zone Project Knowledge
2. Sélectionnez vos fichiers ou glissez-déposez
3. Les fichiers apparaissent dans la liste des connaissances du projet

### Formats acceptés :
PDF, DOCX, TXT, CSV, code source, images (PNG, JPG)

### Conseils pour les documents :

| Bonne pratique | Mauvaise pratique |
|---------------|-------------------|
| Fichiers bien nommés ("Étude-Marché-SaaS-2024.pdf") | Fichiers cryptiques ("scan003.pdf") |
| Documents à jour | Anciennes versions |
| Texte sélectionnable (PDF natif) | Scans/images de documents |
| Documents < 200 pages | Documents très volumineux |
| Données anonymisées | Données personnelles nominatives |

### Idées de documents par métier :

| Métier | Documents à uploader |
|--------|---------------------|
| **RH** | Convention collective, accords d'entreprise, livret d'accueil, procédures, organigramme |
| **Marketing** | Charte de marque, guide éditorial, études de marché, personas, analyses concurrentielles |
| **Finance** | Plans comptables, procédures budgétaires, rapports annuels, modèles de reporting |
| **Commercial** | Fiches produit, grilles tarifaires, scripts de vente, FAQ objections |
| **Gestion** | Procédures administratives, modèles de documents, annuaires, organigrammes |

---

## Étape 4 : Démarrer une conversation

1. Dans votre Project, cliquez sur **"Start chat"** (ou l'icône de nouvelle conversation)
2. Posez votre question — Claude a automatiquement accès aux documents et aux instructions
3. Vous pouvez aussi uploader des fichiers supplémentaires dans la conversation (temporaires, pas ajoutés au Project)

### Premières questions à tester :

**Pour vérifier que les documents sont bien pris en compte :**
> "Quels documents as-tu dans ta base de connaissances ? Résume-les brièvement."

**Pour tester la qualité des réponses :**
> "En te basant sur les documents disponibles, [question spécifique sur le contenu]"

**Pour tester les instructions :**
> "Quelle est ta mission et quelles sont tes règles ?" (Claude doit résumer ses instructions)

---

## Étape 5 : Fonctionnalités avancées

### Artifacts dans les Projects
Claude crée automatiquement des Artifacts (documents structurés) quand vous demandez :
- Des rapports ou analyses
- Du code
- Des tableaux comparatifs
- Des documents formatés

Les Artifacts sont réutilisables entre les conversations du même Project.

### Partager un Project
Vous pouvez partager un Project avec des collègues (si votre plan le permet) :
1. Cliquez sur les paramètres du Project
2. Ajoutez des membres par email
3. Chaque membre accède aux mêmes documents et instructions

### Organiser vos conversations
- Renommez vos conversations pour les retrouver facilement
- Utilisez des conversations séparées pour des sujets différents
- Le contexte du Project est partagé, mais chaque conversation a son propre historique

---

## Comparatif GPT personnalisé vs Claude Project

| Critère | GPT (ChatGPT) | Project (Claude) |
|---------|--------------|-----------------|
| **Instructions** | ✅ Instructions système | ✅ Instructions personnalisées |
| **Documents** | ✅ Knowledge (base docs) | ✅ Project Knowledge |
| **Mémoire** | ⚠️ Par conversation | ✅ Contexte persistant par Project |
| **Fenêtre de contexte** | 128K tokens | 200K tokens |
| **Partage** | Via lien ou GPT Store | Par invitation email |
| **Analyse de code** | ✅ Code Interpreter | ✅ Artifacts |
| **Images** | ✅ DALL-E | ❌ Non |
| **Recherche web** | ✅ Activable | ✅ Activable |
| **Prix** | 20€/mois (Plus) | 20$/mois (Pro) |

**En résumé :**
- **ChatGPT GPTs** = meilleur pour les outils partagés publiquement et l'analyse de données
- **Claude Projects** = meilleur pour l'analyse de longs documents et le travail en équipe

---

## Checklist avant d'utiliser votre Project

- [ ] Le nom et la description sont clairs
- [ ] Les instructions personnalisées sont complètes (rôle, règles, format)
- [ ] Les documents sont uploadés, à jour et bien nommés
- [ ] Aucune donnée personnelle ou confidentielle non autorisée
- [ ] J'ai testé avec 5-10 questions types
- [ ] Les réponses citent les bonnes sources
- [ ] Claude respecte les règles définies dans les instructions

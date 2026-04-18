# FICHE-06 — Guide de Démarrage Rapide : Claude

> **Formation IA pour les Métiers du Tertiaire**
> Guide pas-à-pas avec captures d'écran (2 pages)

---

## Étape 1 : Créer un compte

1. Ouvrez votre navigateur et allez sur **claude.ai**
2. Cliquez sur **"Sign up"** (S'inscrire)
3. Choisissez votre méthode d'inscription :
   - Email + mot de passe
   - Connexion via Google (recommandé)
4. Confirmez votre email
5. Acceptez les conditions d'utilisation

> **Note :** La version gratuite donne un accès limité à Claude 3.5 Sonnet. La version Pro (20$/mois) offre un usage illimité, les Projects, et l'accès aux modèles les plus avancés.

---

## Étape 2 : Découvrir l'interface

```
┌─────────────────────────────────────────────────────┐
│  [≡] Claude                     [+] Nouvelle conv.  │
├──────────┬──────────────────────────────────────────┤
│          │                                          │
│ Récent   │        Zone de conversation             │
│          │                                          │
│ Conv. 1  │     "Comment puis-je vous aider ?"      │
│ Conv. 2  │                                          │
│ Conv. 3  │                                          │
│          │                                          │
│──────────│                                          │
│ Projects │                                          │
│          │                                          │
│ Projet 1 │                                          │
│ Projet 2 │                                          │
│          ├──────────────────────────────────────────┤
│          │  [📎] [🖼️] Écrivez ici...           [➤]│
│          │                                          │
└──────────┴──────────────────────────────────────────┘
```

### Les éléments clés de l'interface :

| Élément | Fonction |
|---------|----------|
| **[+] Nouvelle conversation** | Démarrer un nouvel échange |
| **Récent** | Historique de vos conversations |
| **Projects** | Vos projets avec base de connaissances (version Pro) |
| **Zone de texte** | Écrivez vos prompts ici |
| **[📎] Pièce jointe** | Uploader des fichiers (PDF, images, CSV, code...) |
| **[➤] Envoyer** | Envoyer votre message |

---

## Étape 3 : Votre première conversation

### Essayez ces prompts :

**Prompt 1 — Test simple :**
> Bonjour Claude ! Présente-toi en 3 phrases.

**Prompt 2 — Test professionnel :**
> Je suis responsable RH dans une entreprise de 80 salariés. Rédige un email de bienvenue pour un nouveau collaborateur qui arrive lundi prochain au poste de chargé de communication.

**Prompt 3 — Test d'analyse avec document :**
> [Uploadez un PDF] Lis ce document et fais-moi une synthèse en 10 points clés.

---

## Étape 4 : Les fonctionnalités clés de Claude

### Upload de fichiers (la force de Claude)
Claude excelle dans l'analyse de documents longs grâce à sa fenêtre de contexte de 200 000 tokens (~500 pages).

1. Cliquez sur l'icône **📎** (trombone)
2. Sélectionnez votre fichier (PDF, image, CSV, TXT, code...)
3. Vous pouvez uploader **plusieurs fichiers** à la fois
4. Posez votre question sur le(s) fichier(s)

**Formats supportés :** PDF, DOCX, TXT, CSV, XLSX, images (PNG, JPG), fichiers de code

**Exemple :**
> Uploadez un rapport de 50 pages + demandez : "Compare les sections 3 et 7 de ce rapport et identifie les contradictions éventuelles"

### Les Artifacts
Quand Claude génère du contenu structuré (document, code, tableau), il le présente dans un **Artifact** — une fenêtre séparée à droite de la conversation.

- Les Artifacts sont **copiables** et **téléchargeables**
- Vous pouvez demander à Claude de **modifier** un Artifact existant
- Utile pour : documents, code, SVG, HTML, tableaux

### Les Projects (version Pro)
Les Projects permettent de créer un **espace de travail** avec :
- Des **instructions personnalisées** (comme des instructions système)
- Des **documents de référence** permanents (convention collective, guide de style, procédures...)
- Un **historique** de toutes les conversations du projet

**Créer un Project :**
1. Cliquez sur **"Projects"** dans la barre latérale
2. Cliquez sur **"Créer un projet"**
3. Donnez-lui un nom et une description
4. Ajoutez des instructions personnalisées
5. Uploadez vos documents de référence
6. Commencez à converser dans le contexte du projet

**Exemple de Project :** "Assistant FAQ RH" avec la convention collective uploadée et des instructions pour répondre aux questions des salariés.

---

## Étape 5 : Astuces et bonnes pratiques

### Ce que Claude fait particulièrement bien :
| Tâche | Pourquoi Claude excelle |
|-------|------------------------|
| **Analyse de longs documents** | Fenêtre de 200K tokens, peut lire des rapports entiers |
| **Rédaction structurée** | Produit des documents bien organisés |
| **Synthèse nuancée** | Bon équilibre entre concision et précision |
| **Raisonnement éthique** | Signale les biais et les limites |
| **Travail en français** | Très bonne qualité de français |

### Raccourcis et astuces :
| Astuce | Comment |
|--------|---------|
| Aller à la ligne | `Shift + Entrée` |
| Uploader plusieurs fichiers | Sélectionnez-les tous d'un coup |
| Continuer une réponse coupée | Écrivez "Continue" |
| Modifier le ton | "Reformule en ton plus formel / plus accessible" |
| Obtenir un Artifact | Demandez un "document", "code" ou "tableau" structuré |

---

## Précautions importantes

- **Ne saisissez JAMAIS** de données personnelles sensibles (noms + données RH, données clients...)
- **Vérifiez toujours** les informations factuelles générées
- Claude peut **refuser** certaines demandes qu'il juge risquées — reformulez si le refus est injustifié
- Les documents uploadés sont traités en mémoire le temps de la conversation — ils ne sont pas stockés de manière permanente (sauf dans les Projects Pro)
- En version gratuite, le nombre de messages est **limité** par période — passez à Pro si vous utilisez Claude quotidiennement

---

## Claude vs ChatGPT : quand utiliser l'un ou l'autre ?

| Situation | Recommandation |
|-----------|---------------|
| Analyser un document de 100+ pages | **Claude** (fenêtre de contexte plus large) |
| Générer une image | **ChatGPT** (DALL-E intégré) |
| Analyser un fichier CSV / Excel | **ChatGPT** (Code Interpreter) |
| Rédiger un document long et structuré | **Claude** (meilleure cohérence) |
| Avoir un assistant personnalisé permanent | **Les deux** (GPTs / Projects) |
| Besoin rapide sans inscription | **Claude** ou **Le Chat** (Mistral) |

# Formation IA pour les Métiers du Tertiaire

> **Fiche de référence — Session 8**
> Module 2 — Pratique Métier | FICHE-36 : Guide Copilot dans Microsoft 365

---

## 1. Prérequis

| Élément | Détail |
|---------|--------|
| **Licence Microsoft 365** | E3 ou E5 (entreprise) / Business Standard ou Business Premium (PME) |
| **Add-on Copilot** | Licence Microsoft 365 Copilot (30 USD/utilisateur/mois en supplément) |
| **Navigateur** | Microsoft Edge recommandé (compatible Chrome) |
| **Application desktop** | Word, Excel, PowerPoint, Outlook en version desktop ou web |
| **Alternative formation** | Démo formateur ou compte d'essai Microsoft 365 Copilot |

### Vérifier l'activation de Copilot

1. Ouvrez une application Microsoft 365 (Word, Excel...)
2. Cherchez l'icone Copilot dans le ruban (barre d'outils supérieure)
3. Si l'icone n'apparaît pas : vérifiez votre licence dans "Compte" > "Abonnements"

```
+---------------------------------------------------------------+
|  Fichier  Accueil  Insertion  Conception  Mise en page  ...   |
|---------------------------------------------------------------|
|  [Copilot ★]  |  Police  |  Taille  |  B I U  |  ...         |
|---------------------------------------------------------------|
|                                                               |
|  Le bouton Copilot apparaît dans le ruban                     |
|  de chaque application Microsoft 365                          |
|                                                               |
+---------------------------------------------------------------+
```

> **Note** : Même sans licence Copilot, le Copilot Chat gratuit (bing.com/copilot ou copilot.microsoft.com) peut être utilisé pour certaines tâches de génération de texte.

---

## 2. Copilot dans Word

### 2.1 Fonctions principales

| Fonction | Description |
|----------|-------------|
| **Rédiger** | Générer du contenu à partir d'une consigne (prompt) |
| **Reformuler** | Proposer des variantes d'un passage sélectionné |
| **Résumer** | Créer un résumé du document ou d'une section |
| **Transformer en tableau** | Convertir du texte en tableau structuré |
| **Référencer un fichier** | Utiliser un document OneDrive/SharePoint comme source |

### 2.2 Accès dans Word

- **Ruban** : Cliquez sur le bouton "Copilot" dans la barre d'outils
- **Dans le texte** : Positionnez le curseur et cliquez sur l'icone Copilot qui apparaît en marge
- **Panneau latéral** : Pour les conversations avec Copilot sur le document entier

```
+---------------------------------------------------------------+
|  [Copilot ★]                                                  |
|---------------------------------------------------------------|
|                                                    | Panneau  |
|  Mon rapport trimestriel                           | Copilot  |
|                                                    |----------|
|  [★ Rédiger avec Copilot]                          | Résumer  |
|  |                                              |  | ce doc   |
|  |  Décrivez ce que vous voulez écrire...       |  |          |
|  |  Vous pouvez référencer un fichier avec /    |  | Poser    |
|  |                                              |  | une      |
|  |  [Générer]    [Options]                      |  | question |
|  |                                              |  |          |
+---------------------------------------------------------------+
```

### 2.3 Exercice guidé : Rédiger un rapport trimestriel

**Objectif** : Transformer des notes brutes en un rapport trimestriel structuré.

**Notes brutes de départ** :

```
- CA T3 : 1.2M EUR (+8% vs T2)
- Nouveaux clients : 15 (dont 3 grands comptes)
- Taux de rétention : 94%
- Problème : délais de livraison allongés (fournisseur Asie)
- Recrutement : 4 postes pourvus sur 6 ouverts
- Projet CRM : déploiement terminé, formation en cours
- Objectif T4 : 1.4M EUR
```

**Étapes** :

1. Ouvrez un nouveau document Word
2. Collez les notes brutes ci-dessus
3. Cliquez sur le bouton Copilot dans le ruban
4. Tapez la consigne :

> "Transforme ces notes brutes en un rapport trimestriel T3 professionnel et structuré pour le comité de direction. Utilise des sections avec titres (Performance commerciale, Ressources humaines, Projets stratégiques, Perspectives T4). Adopte un ton formel et factuel."

5. Relisez le résultat généré par Copilot
6. Sélectionnez la section "Perspectives T4" et demandez à Copilot de "développer avec des recommandations concrètes"
7. Sélectionnez tout le document et demandez "Transformer les chiffres clés en tableau récapitulatif"
8. Ajustez la mise en forme et les détails manuellement

---

## 3. Copilot dans Excel

### 3.1 Fonctions principales

| Fonction | Description |
|----------|-------------|
| **Analyser les données** | Poser des questions en langage naturel sur les données |
| **Créer des formules** | Décrire le calcul souhaité, Copilot génère la formule |
| **Générer des graphiques** | Créer des visualisations à partir d'une description |
| **Identifier des tendances** | Repérer des patterns, anomalies, corrélations |
| **Mettre en forme** | Mises en forme conditionnelles, tris, filtres |

> **Prérequis important** : Les données doivent être dans un tableau Excel formaté (Ctrl+T) pour que Copilot puisse les analyser correctement.

### 3.2 Exercice : Analyser un budget prévisionnel

**Objectif** : Analyser un budget prévisionnel et identifier les écarts avec le réalisé.

**Données de départ** (à saisir dans un tableau Excel formaté) :

| Poste budgétaire | Budget prévu (EUR) | Réalisé (EUR) |
|-----------------|-------------------|--------------|
| Salaires | 450 000 | 462 000 |
| Locaux | 120 000 | 118 500 |
| Marketing | 80 000 | 95 000 |
| IT / Logiciels | 65 000 | 72 000 |
| Déplacements | 40 000 | 28 000 |
| Formation | 25 000 | 18 000 |
| Fournitures | 15 000 | 14 200 |
| Divers | 20 000 | 31 500 |

**Étapes** :

1. Saisissez les données et formatez-les en tableau (Ctrl+T)
2. Cliquez sur le bouton Copilot
3. Demandez : "Calcule l'écart en valeur et en pourcentage entre le budget prévu et le réalisé pour chaque poste"
4. Demandez : "Quels postes dépassent le budget de plus de 10% ?"
5. Demandez : "Crée un graphique en barres comparant budget prévu et réalisé pour chaque poste"
6. Demandez : "Ajoute une mise en forme conditionnelle : rouge si le réalisé dépasse le prévu de plus de 10%, vert si le réalisé est inférieur au prévu"
7. Vérifiez chaque calcul manuellement

---

## 4. Copilot dans PowerPoint

### 4.1 Fonctions principales

| Fonction | Description |
|----------|-------------|
| **Créer à partir d'un document** | Générer un deck à partir d'un fichier Word ou d'un PDF |
| **Créer à partir d'un plan** | Générer une présentation à partir d'un texte structuré |
| **Créer de zéro** | Décrire le sujet et le nombre de slides souhaité |
| **Résumer une présentation** | Obtenir les points clés d'un deck existant |
| **Ajouter une slide** | Insérer une slide sur un sujet spécifique |
| **Organiser** | Réorganiser les slides selon une logique narrative |

### 4.2 Exercice : Créer un deck pour un comité de direction

**Objectif** : Créer une présentation de 8 slides pour un comité de direction (CODIR).

**Consigne pour Copilot** :

> "Crée une présentation de 8 slides pour un comité de direction trimestriel. Structure : 1) Page de titre (Bilan T3 2025 — Entreprise AlphaTech), 2) Sommaire, 3) Chiffres clés du trimestre, 4) Performance commerciale, 5) Avancement des projets stratégiques, 6) Ressources humaines, 7) Points de vigilance et risques, 8) Feuille de route T4. Utilise un style professionnel et sobre."

**Étapes** :

1. Ouvrez un nouveau PowerPoint
2. Cliquez sur le bouton Copilot
3. Collez la consigne ci-dessus
4. Examinez les 8 slides générées
5. Sur la slide "Chiffres clés" : demandez "Ajoute un tableau avec CA, marge, nombre de clients, taux de satisfaction"
6. Demandez "Référence le fichier /Rapport-T3.docx pour compléter avec les vrais chiffres" (si disponible)
7. Ajustez les contenus, couleurs et mise en page

> **Astuce** : Si vous avez déjà le rapport Word de l'exercice précédent (FICHE-36 section 2), vous pouvez dire à Copilot "Crée une présentation à partir de ce document Word" en le référençant avec `/`.

---

## 5. Copilot dans Outlook

### 5.1 Fonctions principales

| Fonction | Description |
|----------|-------------|
| **Résumer un fil d'emails** | Synthétise les échanges longs en quelques points |
| **Rédiger une réponse** | Génère un brouillon de réponse contextuel |
| **Coaching de ton** | Vérifie si le ton est approprié avant l'envoi |
| **Préparer une réunion** | Résume les emails liés à une réunion à venir |
| **Rédiger un nouvel email** | Création de message à partir d'une consigne |

### 5.2 Exercice : Rédiger un email diplomatique de refus

**Objectif** : Rédiger un email professionnel et diplomatique pour décliner la proposition d'un fournisseur.

**Contexte** : Le fournisseur DataServ a proposé un contrat de maintenance IT à 48 000 EUR/an. Votre entreprise a choisi un concurrent car le prix est trop élevé, mais vous souhaitez maintenir la relation pour d'éventuelles collaborations futures.

**Étapes** :

1. Ouvrez un nouveau message dans Outlook
2. Cliquez sur l'icone Copilot dans le compositeur
3. Tapez la consigne :

> "Rédige un email poli et diplomatique à M. Leroy (directeur commercial chez DataServ) pour décliner sa proposition de contrat de maintenance IT à 48 000 EUR/an. Nous avons choisi un autre prestataire pour des raisons budgétaires. Nous souhaitons rester en contact pour de futurs projets. Ton professionnel et bienveillant."

4. Relisez le brouillon généré
5. Utilisez le "Coaching de ton" pour vérifier que l'email est bien diplomatique
6. Testez "Raccourcir" si l'email est trop long
7. Ajustez les détails personnels avant envoi

```
+---------------------------------------------------------------+
|  Nouveau message                                              |
|---------------------------------------------------------------|
|  À : p.leroy@dataserv.fr                                     |
|  Objet : Suite à votre proposition — Contrat maintenance IT   |
|---------------------------------------------------------------|
|                                                               |
|  [★ Copilot : Rédiger avec Copilot]                           |
|                                                               |
|  Bonjour Monsieur Leroy,                                      |
|                                                               |
|  [Contenu généré par Copilot]                                 |
|                                                               |
|  [Envoyer]  [★ Coaching] [★ Raccourcir] [★ Reformuler]       |
+---------------------------------------------------------------+
```

---

## 6. Copilot dans Teams

### 6.1 Résumé de réunion

Pendant et après une réunion Teams :

| Fonctionnalité | Description | Comment activer |
|----------------|-------------|----------------|
| **Résumé en temps réel** | Points discutés pendant la réunion | Cliquer sur Copilot pendant la réunion |
| **Points clés** | Synthèse des décisions prises | Automatique en fin de réunion |
| **Actions identifiées** | Liste des tâches assignées avec responsable | Automatique (si transcription activée) |
| **Questions manquées** | Rattraper ce qui a été dit pendant votre absence | "Qu'ai-je manqué ?" dans le panneau Copilot |

> **Prérequis** : La transcription doit être activée pour que Copilot puisse analyser la réunion.

### 6.2 Copilot Chat — Assistant transversal

Le **Copilot Chat** dans Teams fonctionne comme un assistant personnel transversal :

- Posez des questions sur vos emails récents : "Résume les emails de cette semaine sur le projet Alpha"
- Cherchez dans vos fichiers : "Trouve le dernier rapport de ventes dans mon OneDrive"
- Préparez vos réunions : "Quels sont les sujets discutés lors de la dernière réunion avec l'équipe marketing ?"
- Rédigez des messages : "Écris un message pour l'équipe annonçant le report de la deadline au 15 mars"

---

## 7. Tableau récapitulatif

| Application | Fonction Copilot | Accès | Remarques |
|-------------|-----------------|-------|-----------|
| **Word** | Rédaction, résumé, reformulation, tableau | Bouton Copilot dans le ruban + panneau latéral | Fonctionne mieux avec des consignes détaillées |
| **Excel** | Formules, analyse, graphiques, tendances | Bouton Copilot (données en tableau formaté requis) | Données doivent être en Tableau Excel (Ctrl+T) |
| **PowerPoint** | Création de deck, slides, résumé | Bouton Copilot dans le ruban | Peut référencer des fichiers Word/PDF |
| **Outlook** | Résumé, rédaction, coaching de ton | Icone Copilot dans le compositeur | Excellent pour les emails diplomatiques |
| **Teams** | Résumé réunion, actions, Copilot Chat | Icone Copilot pendant/après réunion + Chat | Transcription requise pour les réunions |
| **OneNote** | Résumé de notes, liste de tâches | Bouton Copilot dans le ruban | Utile pour les cahiers de notes volumineux |

---

## 8. Comparaison Gemini vs Copilot

| Critère | Gemini (Google Workspace) | Copilot (Microsoft 365) |
|---------|--------------------------|------------------------|
| **Prix** | Inclus dans certains abonnements Workspace (ou add-on) | 30 USD/utilisateur/mois (en plus de la licence M365) |
| **Rédaction (Docs/Word)** | Bon, résultats fluides en français | Très bon, excellent en reformulation |
| **Tableur (Sheets/Excel)** | Correct, en progression | Bon, mais requiert un tableau formaté |
| **Présentations (Slides/PPT)** | Correct, images génératives | Très bon, référence des fichiers existants |
| **Email (Gmail/Outlook)** | Bon, suggestions contextuelles | Très bon, coaching de ton unique |
| **Réunions (Meet/Teams)** | Résumé basique | Résumé avancé + actions + Copilot Chat |
| **Intégration écosystème** | Forte dans l'écosystème Google | Forte dans l'écosystème Microsoft |
| **Assistant transversal** | Gemini (app dédiée + intégré) | Copilot Chat dans Teams (transversal) |
| **Qualité du français** | Très bonne | Très bonne |
| **Référence fichiers** | Limitée (Google Drive) | Excellente (OneDrive + SharePoint) |
| **Génération d'images** | Oui (dans Slides) | Limitée (via Designer) |

### En résumé

- **Gemini** : Meilleur rapport qualité/prix si vous êtes déjà dans l'écosystème Google. Plus accessible.
- **Copilot** : Plus puissant pour la productivité bureautique avancée, particulièrement en entreprise avec SharePoint/Teams. Plus cher.
- **Recommandation** : Utilisez l'IA intégrée à votre suite existante plutôt que de changer d'écosystème.

---

## 9. Limites et coût

### Coût par utilisateur

| Solution | Licence de base | Add-on IA | Total mensuel/utilisateur |
|----------|----------------|-----------|--------------------------|
| Google Workspace Business Standard | ~12 EUR/mois | Gemini souvent inclus | ~12-20 EUR/mois |
| Google Workspace Business Plus | ~18 EUR/mois | Gemini inclus | ~18 EUR/mois |
| Microsoft 365 E3 | ~36 EUR/mois | +30 EUR Copilot | ~66 EUR/mois |
| Microsoft 365 Business Premium | ~22 EUR/mois | +30 EUR Copilot | ~52 EUR/mois |

> **Note** : Les prix sont indicatifs et susceptibles d'évoluer. Vérifiez les tarifs actuels sur les sites officiels.

### ROI estimé

Le retour sur investissement dépend de l'usage :

| Profil utilisateur | Gain de temps estimé | ROI mensuel estimé |
|-------------------|---------------------|-------------------|
| Utilisateur occasionnel (1-2h/semaine avec l'IA) | 2-4h/mois | Faible — le coût peut ne pas être justifié |
| Utilisateur régulier (1h/jour avec l'IA) | 8-15h/mois | Positif — rentabilisé dès le 2e mois |
| Utilisateur intensif (rédaction, analyse, réunions) | 15-25h/mois | Très positif — fort levier de productivité |

### Limites communes

- Les deux solutions nécessitent un temps d'apprentissage (2-4 semaines d'usage régulier)
- Les résultats dépendent fortement de la qualité des prompts
- La vérification humaine reste indispensable
- Les données traitées restent dans le périmètre de votre tenant, mais consultez votre DPO
- Les fonctionnalités évoluent rapidement (mises à jour mensuelles)

---

> **Fiche 36** | Formation IA Tertiaire — Module 2 | Session 8 : Intégration Google Workspace / Microsoft 365

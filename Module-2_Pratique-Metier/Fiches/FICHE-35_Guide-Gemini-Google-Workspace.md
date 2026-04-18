# Formation IA pour les Métiers du Tertiaire

> **Fiche de référence — Session 8**
> Module 2 — Pratique Métier | FICHE-35 : Guide Gemini dans Google Workspace

---

## 1. Prérequis

Avant de commencer, assurez-vous de disposer des éléments suivants :

| Élément | Détail |
|---------|--------|
| **Compte Google Workspace** | Version Business Standard, Business Plus, Enterprise, ou Education Plus avec Gemini activé |
| **Navigateur** | Google Chrome (version récente recommandée) |
| **Gemini activé** | L'administrateur Workspace doit avoir activé Gemini pour votre organisation |
| **Alternative** | Version d'essai Google Workspace 14 jours (avec fonctionnalités Gemini incluses) |

> **Note formateur** : Si les participants n'ont pas accès à Gemini, préparez des captures d'écran ou une démonstration en direct depuis votre propre compte.

### Vérifier l'activation de Gemini

1. Ouvrez Google Docs, Sheets ou Gmail
2. Cherchez l'icone Gemini (étoile stylisée) dans la barre d'outils
3. Si l'icone n'apparaît pas, contactez votre administrateur Workspace

---

## 2. Gemini dans Google Docs

### 2.1 Activer Gemini dans un document

Pour accéder à Gemini dans Google Docs :

- **Méthode 1** : Cliquez sur l'icone Gemini (étoile) dans la barre d'outils latérale
- **Méthode 2** : Tapez `@` dans le document puis sélectionnez "Aidez-moi à écrire"
- **Méthode 3** : Clic droit sur du texte sélectionné, puis "Gemini" dans le menu contextuel

```
+---------------------------------------------------------------+
|  Fichier  Edition  Affichage  Insertion  Format  Outils  ...  |
|---------------------------------------------------------------|
|  B  I  U  ...  |  [★ Gemini]  |  Normal  |  Police  |  ...   |
|---------------------------------------------------------------|
|                                                               |
|  Mon document                                                 |
|                                                               |
|  [  ★ Aidez-moi à écrire...                               ]  |
|  |  Tapez votre demande ici                                |  |
|  |  Ex: "Rédiger une note sur le télétravail"              |  |
|  [  [Générer]                                              ]  |
|                                                               |
+---------------------------------------------------------------+
```

### 2.2 Fonctions principales

| Fonction | Description | Comment y accéder |
|----------|-------------|-------------------|
| **Aidez-moi à écrire** | Génère du texte à partir d'une consigne | Icone Gemini ou `@` |
| **Reformuler** | Propose des variantes d'un texte sélectionné | Sélectionner le texte puis clic sur Gemini |
| **Résumer** | Crée un résumé concis d'un long passage | Sélectionner le texte, "Résumer" |
| **Allonger** | Développe un texte trop court avec plus de détails | Sélectionner le texte, "Allonger" |
| **Raccourcir** | Condense un texte trop long | Sélectionner le texte, "Raccourcir" |
| **Changer le ton** | Formel, décontracté, professionnel, etc. | Sélectionner le texte, "Changer le ton" |

### 2.3 Exercice guidé : Rédiger une note de service

**Objectif** : Rédiger une note de service sur la nouvelle politique de télétravail de l'entreprise.

**Étapes** :

1. Ouvrez un nouveau Google Doc
2. Cliquez sur l'icone Gemini ou tapez `@` puis "Aidez-moi à écrire"
3. Tapez la consigne suivante :

> "Rédige une note de service annonçant la nouvelle politique de télétravail de l'entreprise TechSolutions. Les collaborateurs peuvent désormais télétravailler 3 jours par semaine (mardi à jeudi au choix). La mise en place est effective au 1er mars 2025. Un accord individuel doit être signé avec le manager."

4. Cliquez sur **Générer**
5. Relisez le texte proposé par Gemini
6. Sélectionnez le texte et demandez à Gemini de **changer le ton** vers "formel"
7. Ajustez manuellement les éléments spécifiques (noms, dates, coordonnées)

**Résultat attendu** : Une note de service structurée avec en-tête, objet, corps de texte et signature.

```
+---------------------------------------------------------------+
|  NOTE DE SERVICE                                              |
|  TechSolutions — Direction des Ressources Humaines            |
|---------------------------------------------------------------|
|  Objet : Nouvelle politique de télétravail                    |
|  Date : [date du jour]                                        |
|  Destinataires : Ensemble des collaborateurs                  |
|---------------------------------------------------------------|
|                                                               |
|  Madame, Monsieur,                                            |
|                                                               |
|  Nous avons le plaisir de vous informer de la mise en place   |
|  d'une nouvelle politique de télétravail...                    |
|  [Contenu généré par Gemini, revu par l'utilisateur]          |
|                                                               |
|  Cordialement,                                                |
|  La Direction des Ressources Humaines                         |
+---------------------------------------------------------------+
```

---

## 3. Gemini dans Google Sheets

### 3.1 Fonctions principales

| Fonction | Description |
|----------|-------------|
| **Insérer des formules** | Décrivez en langage naturel ce que vous voulez calculer, Gemini propose la formule |
| **Analyser des données** | Posez des questions sur vos données et obtenez des réponses en langage naturel |
| **Créer des graphiques** | Demandez un type de graphique et Gemini le génère |
| **Organiser les données** | Tri, filtres, mises en forme conditionnelles via une consigne textuelle |

### 3.2 Accéder à Gemini dans Sheets

1. Ouvrez un Google Sheet contenant des données
2. Cliquez sur l'icone Gemini dans la barre latérale droite
3. Posez votre question ou formulez votre demande

```
+-------------------------------------------------------------------+
|  A         |  B         |  C         |  D         | [Panel   ]    |
|------------|------------|------------|------------|[Gemini   ]    |
|  Mois      |  Ventes    |  Objectif  |  Écart     |[          ]   |
|  Janvier   |  45 000    |  50 000    |  -5 000    |[ ★ Posez  ]   |
|  Février   |  52 000    |  50 000    |  +2 000    |[ votre    ]   |
|  Mars      |  48 000    |  55 000    |  -7 000    |[ question ]   |
|  Avril     |  61 000    |  55 000    |  +6 000    |[          ]   |
|  ...       |  ...       |  ...       |  ...       |[ [Envoyer]]   |
+-------------------------------------------------------------------+
```

### 3.3 Exercice : Analyser un tableau de ventes

**Objectif** : Analyser les données de ventes mensuelles et créer un graphique de tendance.

**Données de départ** (à saisir ou copier dans un Sheet) :

| Mois | Ventes (EUR) | Objectif (EUR) |
|------|-------------|----------------|
| Janvier | 45 000 | 50 000 |
| Février | 52 000 | 50 000 |
| Mars | 48 000 | 55 000 |
| Avril | 61 000 | 55 000 |
| Mai | 58 000 | 60 000 |
| Juin | 67 000 | 60 000 |

**Étapes** :

1. Saisissez les données dans un Google Sheet
2. Ouvrez le panneau Gemini
3. Demandez : "Calcule l'écart entre les ventes et l'objectif pour chaque mois en colonne D"
4. Demandez : "Crée un graphique en courbes montrant les ventes et les objectifs sur 6 mois"
5. Demandez : "Quel est le mois avec la meilleure performance ? Quelle est la tendance générale ?"
6. Vérifiez les résultats manuellement

---

## 4. Gemini dans Google Slides

### 4.1 Fonctions principales

| Fonction | Description |
|----------|-------------|
| **Générer une présentation** | Créer des slides à partir d'une description textuelle |
| **Créer des images** | Générer des visuels directement dans les slides |
| **Résumer des slides** | Obtenir un résumé d'une présentation existante |
| **Mettre en forme** | Propositions de design et de mise en page |

### 4.2 Exercice : Créer 5 slides de présentation produit

**Objectif** : Créer une mini-présentation pour le lancement d'un nouveau produit.

**Consigne pour Gemini** :

> "Crée une présentation de 5 slides pour le lancement du produit EcoClean, un nettoyant ménager écologique. Slide 1 : titre et accroche. Slide 2 : le problème (produits chimiques nocifs). Slide 3 : la solution EcoClean (composition naturelle). Slide 4 : les avantages (3 points clés). Slide 5 : disponibilité et prix."

**Étapes** :

1. Ouvrez un nouveau Google Slides
2. Cliquez sur l'icone Gemini
3. Collez la consigne ci-dessus
4. Examinez les slides générées
5. Demandez à Gemini de "Générer une image illustrant un produit ménager écologique" pour la slide 3
6. Ajustez les textes et la mise en forme manuellement

---

## 5. Gemini dans Gmail

### 5.1 Fonctions principales

| Fonction | Description |
|----------|-------------|
| **Rédiger un email** | Générer un brouillon à partir d'une consigne courte |
| **Résumer un fil de discussion** | Obtenir les points clés d'un échange long |
| **Suggérer des réponses** | Propositions contextuelles de réponse |
| **Reformuler** | Modifier le ton ou la longueur d'un brouillon |
| **Formaliser** | Transformer un brouillon informel en email professionnel |

### 5.2 Exercice : Rédiger un email de relance commerciale

**Objectif** : Rédiger un email de relance suite à une proposition commerciale restée sans réponse.

**Étapes** :

1. Ouvrez Gmail et cliquez sur "Nouveau message"
2. Cliquez sur l'icone Gemini (étoile) dans la fenêtre de rédaction
3. Tapez la consigne :

> "Rédige un email de relance commerciale poli mais engageant à un prospect (Mme Durand, directrice achats chez LogiPro) à qui nous avons envoyé une proposition il y a 10 jours pour notre solution de gestion des stocks. Propose un rendez-vous téléphonique cette semaine."

4. Relisez et ajustez le texte généré
5. Testez "Raccourcir" pour obtenir une version plus concise
6. Testez "Changer le ton" vers "plus décontracté" puis "plus formel"
7. Choisissez la version qui convient le mieux

```
+---------------------------------------------------------------+
|  Nouveau message                                     [- X]    |
|---------------------------------------------------------------|
|  À : m.durand@logipro.fr                                      |
|  Objet : Suite à notre proposition — Solution GestionStock     |
|---------------------------------------------------------------|
|                                                               |
|  [★ Aidez-moi à écrire]                                      |
|                                                               |
|  Bonjour Madame Durand,                                       |
|                                                               |
|  [Contenu généré par Gemini]                                  |
|                                                               |
|  [Envoyer]  [★ Reformuler] [★ Raccourcir] [★ Ton]            |
+---------------------------------------------------------------+
```

---

## 6. Gemini dans Google Meet (Bonus)

> **Disponibilité** : Cette fonctionnalité nécessite un abonnement Google Workspace Business Standard ou supérieur avec Gemini activé.

### Fonctionnalités principales

| Fonction | Description | Quand l'utiliser |
|----------|-------------|-----------------|
| **Résumé automatique** | Résumé de la réunion envoyé après la fin | Après chaque réunion importante |
| **Notes en temps réel** | Prise de notes automatique pendant la réunion | Réunions longues ou complexes |
| **Actions à suivre** | Identification automatique des tâches assignées | Réunions de projet |
| **Traduction en temps réel** | Sous-titres traduits dans plusieurs langues | Réunions internationales |

### Comment activer

1. Lancez ou rejoignez un Google Meet
2. Cliquez sur l'icone Gemini (en bas à droite de l'écran)
3. Activez "Prendre des notes avec Gemini"
4. En fin de réunion, le résumé est envoyé par email et ajouté à l'événement Calendar

---

## 7. Tableau récapitulatif

| Application | Fonction Gemini | Raccourci / Accès | Niveau de maturité |
|-------------|----------------|-------------------|-------------------|
| **Google Docs** | Rédaction, reformulation, résumé, changement de ton | Icone Gemini ou `@` | Mature |
| **Google Sheets** | Formules, analyse de données, graphiques | Panneau latéral Gemini | En progression |
| **Google Slides** | Génération de slides, création d'images | Icone Gemini | En progression |
| **Gmail** | Rédaction, résumé de fils, suggestions de réponse | Icone Gemini dans le compositeur | Mature |
| **Google Meet** | Résumé de réunion, notes, actions | Icone Gemini dans Meet | Récent |
| **Google Chat** | Assistant conversationnel intégré | `@Gemini` dans un espace | En progression |
| **Google Drive** | Résumé de documents, recherche intelligente | Panneau latéral | Récent |

**Légende niveaux de maturité** :
- **Mature** : fonctionnalité stable, résultats fiables dans la majorité des cas
- **En progression** : fonctionnel mais résultats parfois inégaux
- **Récent** : déployé récemment, peut évoluer rapidement

---

## 8. Limites actuelles de Gemini dans Workspace

### Ce que Gemini ne fait pas encore bien

| Limitation | Détail |
|-----------|--------|
| **Calculs complexes** | Dans Sheets, les formules générées peuvent contenir des erreurs sur des calculs avancés |
| **Mise en forme avancée** | Les documents générés nécessitent souvent des ajustements manuels de mise en page |
| **Contexte long** | Gemini peut perdre le fil sur des documents très longs (>20 pages) |
| **Données en temps réel** | Pas d'accès à des données externes actualisées (cours de bourse, etc.) |
| **Langues** | Le français est bien supporté mais certaines nuances peuvent être manquées |
| **Images dans Slides** | La génération d'images est encore limitée en qualité et en pertinence |

### Données confidentielles : points d'attention

> **Important** : Les données traitées par Gemini dans Google Workspace restent dans l'environnement Workspace de votre organisation. Google indique ne pas utiliser ces données pour entraîner ses modèles. Cependant :

- Vérifiez la politique de confidentialité de votre organisation
- Ne saisissez pas de données ultra-sensibles (mots de passe, numéros de carte bancaire)
- Consultez votre DPO (Délégué à la Protection des Données) en cas de doute
- Les administrateurs Workspace peuvent désactiver Gemini pour certains utilisateurs ou groupes

---

> **Fiche 35** | Formation IA Tertiaire — Module 2 | Session 8 : Intégration Google Workspace / Microsoft 365

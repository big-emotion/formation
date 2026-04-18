# Formation IA pour les Métiers du Tertiaire — Guide pas-à-pas — Session 9

# FICHE 40 — Guide de Démarrage Make : Pas-à-Pas

---

## 1. Qu'est-ce que Make ?

**Make** (anciennement Integromat) est une **plateforme d'automatisation no-code**. Elle permet de connecter des applications entre elles et de créer des workflows automatisés, sans écrire une seule ligne de code.

> **Analogie visuelle** : Imaginez un organigramme que vous dessinez sur un tableau blanc, avec des boîtes reliées par des flèches. Chaque boîte représente une action (lire un email, ajouter une ligne dans un tableur, envoyer un message...). Maintenant, imaginez que cet organigramme **s'exécute tout seul**, automatiquement, dès qu'un événement se produit. C'est exactement ce que fait Make.

**Ce que Make permet concrètement** :
- Recevoir un email → extraire les pièces jointes → les sauvegarder dans Google Drive
- Nouvelle entrée dans un formulaire → envoyer un email de confirmation → ajouter dans un CRM
- Nouvelle ligne dans un tableur → appeler une API d'IA → écrire la réponse dans le tableur

---

## 2. Créer un compte

### Étape 1 — Aller sur le site

Ouvrez votre navigateur et rendez-vous sur : **https://www.make.com**

### Étape 2 — Inscription gratuite

1. Cliquez sur le bouton **"Get started free"** (en haut à droite)
2. Remplissez le formulaire :
   - Adresse email professionnelle
   - Mot de passe (minimum 8 caractères)
   - Pays : France
3. Acceptez les conditions d'utilisation
4. Cliquez sur **"Sign up"**

### Étape 3 — Confirmation email

1. Ouvrez votre boîte email
2. Cherchez l'email de Make (vérifiez les spams si besoin)
3. Cliquez sur le lien de confirmation
4. Vous êtes redirigé vers le tableau de bord Make

> **Plan Free** : 1 000 opérations par mois, 2 scénarios actifs. Largement suffisant pour cette formation.

---

## 3. Découvrir l'interface

### Schéma ASCII de l'interface Make

```
+-----------------------------------------------------------------------+
|  MAKE         [Scenarios] [Templates] [Connections]    [Mon Compte]   |
+-----------------------------------------------------------------------+
|                                                                       |
|  +-------------------+    +---------------------------------------+   |
|  |                   |    |                                       |   |
|  |    PANNEAU        |    |         CANVAS (Éditeur visuel)       |   |
|  |    LATÉRAL        |    |                                       |   |
|  |                   |    |    [Trigger] ---> [Module] ---> [Fin] |   |
|  |  - Mes scénarios  |    |        O----------->O--------->O     |   |
|  |  - Templates      |    |                                       |   |
|  |  - Historique     |    |                                       |   |
|  |                   |    |                                       |   |
|  +-------------------+    +---------------------------------------+   |
|                                                                       |
|  [Run once]  [Scheduling: OFF]    [Sauvegarder]    [Paramètres]       |
+-----------------------------------------------------------------------+
```

### Les zones principales

| Zone | Rôle | Emplacement |
|------|-------|-------------|
| **Dashboard** | Liste de vos scénarios, historique des exécutions | Page d'accueil après connexion |
| **Canvas (Éditeur visuel)** | Zone de travail où vous construisez votre workflow | Centre de l'écran |
| **Modules** | Les briques d'action que vous ajoutez au canvas | Clic sur le "+" ou sur le cercle vide |
| **Connexions (flèches)** | Les liens entre les modules, montrant le flux de données | Lignes entre les modules |
| **Panneau de configuration** | Paramétrage détaillé de chaque module | S'ouvre à droite quand vous cliquez sur un module |

---

## 4. Vocabulaire Make

Avant de commencer, familiarisez-vous avec les termes que vous rencontrerez :

| Terme Make | Définition | Exemple concret |
|-----------|-----------|-----------------|
| **Scénario** | Un workflow automatisé complet | "Quand un email arrive → l'analyser → répondre" |
| **Module** | Une action unitaire dans le scénario | "Lire une ligne Google Sheets", "Envoyer un email" |
| **Connexion** | Le lien d'authentification entre votre compte (Google, Gmail...) et Make | Autoriser Make à accéder à votre Google Drive |
| **Trigger** | Le déclencheur qui lance le scénario | "Nouvelle ligne ajoutée", "Nouvel email reçu" |
| **Opération** | Une exécution d'un module (c'est ce que compte le plan gratuit) | Un scénario avec 3 modules = 3 opérations par exécution |
| **Route** | Un embranchement conditionnel (comme un "Si... Alors...") | Si montant > 1000 € → alerte manager, sinon → traitement normal |
| **Filtre** | Une condition entre deux modules pour continuer ou non | Continuer seulement si le champ "Statut" = "Urgent" |
| **Itérateur** | Une boucle qui traite chaque élément d'une liste | Traiter chaque ligne d'un fichier CSV une par une |
| **Agrégateur** | Regroupe plusieurs éléments en un seul | Rassembler tous les résultats en un seul document |
| **Mapping** | Associer un champ de sortie d'un module à un champ d'entrée du suivant | Le champ "Email" de Google Sheets → le champ "Destinataire" de Gmail |

---

## 5. Premier scénario guidé

### Objectif

> **Quand une nouvelle ligne est ajoutée dans Google Sheets → Envoyer un email de confirmation.**
>
> Cas d'usage : Un formulaire d'inscription alimente un tableur. Chaque nouvel inscrit reçoit automatiquement un email de bienvenue.

### Prérequis

- Un compte Make (étape 2 ci-dessus)
- Un compte Google (Gmail + Google Sheets)
- Un Google Sheet avec au minimum les colonnes : **Nom**, **Email**, **Date d'inscription**

### Étape 1 — Créer un nouveau scénario

1. Depuis le Dashboard, cliquez sur **"Create a new scenario"**
2. Vous arrivez sur un canvas vide avec un cercle central marqué "+"
3. **Sauvegardez** immédiatement avec un nom explicite : `Session9_EmailConfirmation`

### Étape 2 — Ajouter le module Google Sheets : "Watch New Rows"

1. Cliquez sur le cercle **"+"** au centre du canvas
2. Dans la barre de recherche, tapez **"Google Sheets"**
3. Sélectionnez **Google Sheets**
4. Dans la liste des actions, choisissez **"Watch New Rows"**
   - C'est un **trigger** (icône horloge) : il surveille l'apparition de nouvelles lignes

### Étape 3 — Connecter son compte Google

1. Le panneau de configuration s'ouvre à droite
2. Dans le champ **"Connection"**, cliquez sur **"Add"**
3. Nommez la connexion : `Mon Google perso` (ou pro)
4. Cliquez sur **"Sign in with Google"**
5. Autorisez Make à accéder à Google Sheets (cochez les cases nécessaires)
6. La connexion apparaît en vert : vous êtes connecté

### Étape 4 — Sélectionner le spreadsheet et la feuille

1. **Spreadsheet** : sélectionnez votre Google Sheet dans la liste déroulante
2. **Sheet** : sélectionnez la feuille (ex: "Feuille 1")
3. **Contains headers** : choisissez **"Yes"** (votre première ligne contient les titres)
4. **Row limit** : laissez la valeur par défaut (ou mettez 10 pour les tests)
5. Cliquez sur **"OK"** pour valider

### Étape 5 — Ajouter le module Email : "Send an Email"

1. Survolez le module Google Sheets : un petit **"+"** apparaît à droite
2. Cliquez dessus pour ajouter le module suivant
3. Recherchez **"Email"**
4. Sélectionnez le module **Email** (le module natif Make, pas Gmail)
5. Choisissez l'action **"Send an Email"**

> **Pourquoi le module Email natif et pas Gmail ?** Pour cet exercice, le module Email natif est plus simple et ne nécessite pas d'autorisation Google supplémentaire. En production, vous pourriez utiliser le module Gmail.

### Étape 6 — Mapper les champs

C'est l'étape clé : vous allez utiliser les données de Google Sheets dans votre email.

1. **To (destinataire)** : Cliquez dans le champ, puis dans le panneau qui apparaît, sélectionnez la variable **Email** (issue du module Google Sheets)
2. **Subject (objet)** : Tapez `Confirmation d'inscription — ` puis insérez la variable **Nom**
3. **Content (corps)** : Rédigez le message :

```
Bonjour {{Nom}},

Nous avons bien reçu votre inscription du {{Date d'inscription}}.

Votre demande est en cours de traitement. Nous reviendrons vers vous sous 48h.

Cordialement,
L'équipe Formation
```

> **Les doubles accolades `{{...}}`** représentent le mapping visuel de Make. Dans l'interface, vous verrez des pastilles colorées à la place — elles correspondent aux champs du module précédent.

4. Configurez le **SMTP** (serveur d'envoi) si c'est la première fois, ou utilisez les paramètres par défaut de Make
5. Cliquez sur **"OK"**

### Étape 7 — Tester ("Run once")

1. **Ajoutez d'abord une ligne de test** dans votre Google Sheet :
   | Nom | Email | Date d'inscription |
   |-----|-------|--------------------|
   | Jean Dupont | votre-email@test.com | 06/02/2026 |

2. Revenez dans Make et cliquez sur le bouton **"Run once"** (en bas à gauche)
3. Make exécute le scénario une seule fois
4. **Observez les bulles vertes** sur chaque module : elles indiquent le nombre d'opérations traitées
5. Cliquez sur chaque bulle pour voir les données en entrée et en sortie
6. **Vérifiez votre boîte email** : vous devriez avoir reçu l'email de confirmation

### Étape 8 — Activer le scénario (scheduling)

1. Une fois le test réussi, activez le **Scheduling** (bouton en bas)
2. Choisissez la fréquence de vérification :
   - **Every 15 minutes** (par défaut sur le plan gratuit)
   - Vous pouvez choisir un intervalle plus court sur les plans payants
3. Basculez le toggle sur **"ON"**
4. Cliquez sur **"Save"**

Votre scénario est maintenant **actif**. Chaque nouvelle ligne ajoutée dans Google Sheets déclenchera automatiquement l'envoi d'un email.

---

## 6. Les 5 erreurs fréquentes sur Make (et comment les résoudre)

| # | Erreur | Symptôme | Solution |
|---|--------|----------|----------|
| 1 | **Connexion expirée** | Message "Connection lost" ou "401 Unauthorized" | Allez dans Connections, supprimez la connexion et recréez-la. Réautorisez l'accès. |
| 2 | **Mapping incorrect** | Le module reçoit des données vides ou incorrectes | Vérifiez que vous mappez le bon champ. Cliquez sur la bulle de sortie du module précédent pour voir les données disponibles. |
| 3 | **Scénario qui ne se déclenche pas** | Aucune exécution malgré de nouvelles données | Vérifiez que le Scheduling est ON. Vérifiez que le trigger est bien configuré. Testez avec "Run once" d'abord. |
| 4 | **Quota d'opérations dépassé** | Message "Operation limit reached" | Vous avez atteint les 1000 opérations du plan gratuit. Attendez le renouvellement mensuel ou passez à un plan payant. |
| 5 | **Erreur JSON / données mal formatées** | Message "Invalid JSON" ou "Unexpected token" | Si vous utilisez le module HTTP, vérifiez la syntaxe de votre JSON (guillemets doubles, pas de virgule après le dernier élément). Utilisez un validateur JSON en ligne. |

### Bonnes pratiques pour éviter les erreurs

- **Sauvegardez souvent** : Make ne sauvegarde pas automatiquement
- **Testez étape par étape** : utilisez "Run once" après chaque nouveau module
- **Nommez vos scénarios** clairement : `[Projet]_[Action]_[Version]`
- **Consultez l'historique** : le menu "History" montre toutes les exécutions passées avec le détail des erreurs
- **Commencez simple** : un trigger + un module, puis ajoutez de la complexité progressivement

---

## 7. Ressources

### Documentation officielle
- **Make Help Center** : https://www.make.com/en/help
- **Make Academy** : https://academy.make.com (cours gratuits en ligne)
- **Make Community** : https://community.make.com (forum d'entraide)

### Tutoriels vidéo recommandés
- Chaîne YouTube officielle Make : tutoriels pas-à-pas pour débutants
- Rechercher sur YouTube : "Make Integromat tutorial français" pour des tutoriels en français

### Pour aller plus loin
- **Templates Make** : https://www.make.com/en/templates (scénarios prêts à l'emploi, à adapter)
- **Intégrations disponibles** : https://www.make.com/en/integrations (plus de 1500 applications connectables)

---

> **Récapitulatif** : Vous savez maintenant créer un compte Make, naviguer dans l'interface, comprendre le vocabulaire, et construire votre premier scénario automatisé. Dans les fiches suivantes, nous ajouterons de l'Intelligence Artificielle à ces scénarios grâce aux APIs.

# Formation IA pour les Métiers du Tertiaire

> **Fiche de référence — Session 8**
> Module 2 — Pratique Métier | FICHE-37 : 10 Workflows Hybrides IA + Bureautique

---

## Introduction

Cette fiche présente **10 workflows concrets** combinant des outils d'IA externe (ChatGPT, Claude) avec des outils bureautiques (Google Workspace, Microsoft 365). Chaque workflow est conçu pour un métier du tertiaire et détaille les étapes, les outils, le temps estimé et le niveau de difficulté.

**Légende des niveaux de difficulté** :
- Niveau 1 : Débutant, aucune compétence IA préalable requise
- Niveau 2 : Intermédiaire, nécessite une maîtrise de base du prompting
- Niveau 3 : Avancé, nécessite une bonne maîtrise du prompting et des outils

---

## Workflow 1 — Rédaction de rapport mensuel

| | |
|---|---|
| **Métier** | Gestion / Administration |
| **Objectif** | Transformer des notes brutes en un rapport mensuel professionnel |
| **Difficulté** | Niveau 1 |
| **Temps sans IA** | 3-4 heures |
| **Temps avec IA** | 45 min — 1 heure |

### Étapes

| Étape | Action | Outil |
|-------|--------|-------|
| 1 | Rassembler les notes brutes, chiffres clés, retours d'équipe | Notes, emails, fichiers internes |
| 2 | Coller les notes dans Claude avec le prompt : "Structure ces notes en rapport mensuel professionnel avec introduction, sections thématiques, chiffres clés mis en valeur, et conclusion avec recommandations." | **Claude** |
| 3 | Copier le texte structuré dans Google Docs, ajuster la mise en forme (titres, tableaux, logo) | **Google Docs** |
| 4 | Relire, corriger les éventuelles erreurs factuelles, ajouter les pièces jointes | Manuel |
| 5 | Exporter en PDF et diffuser | **Google Docs** > Fichier > Télécharger > PDF |

> **Astuce** : Créez un modèle de prompt réutilisable chaque mois en ne changeant que les données.

---

## Workflow 2 — Analyse de données clients

| | |
|---|---|
| **Métier** | Commercial / Vente |
| **Objectif** | Extraire des insights d'une base clients et préparer une présentation |
| **Difficulté** | Niveau 2 |
| **Temps sans IA** | 4-5 heures |
| **Temps avec IA** | 1h30 — 2 heures |

### Étapes

| Étape | Action | Outil |
|-------|--------|-------|
| 1 | Exporter la base clients du CRM en format CSV | **CRM** (Salesforce, HubSpot, Pipedrive...) |
| 2 | Coller un échantillon des données dans ChatGPT avec le prompt : "Analyse ces données clients. Identifie les segments les plus rentables, le panier moyen par catégorie, les tendances sur les 6 derniers mois. Propose 3 recommandations commerciales." | **ChatGPT** (GPT-4) |
| 3 | Créer les graphiques correspondants dans Google Sheets (barres, camembert, courbes de tendance) | **Google Sheets** |
| 4 | Créer 5 slides de synthèse dans Google Slides avec les graphiques et les recommandations | **Google Slides** |

> **Attention** : Ne collez jamais de données personnelles clients (noms, emails, téléphones) dans ChatGPT. Anonymisez les données avant toute analyse par IA externe.

---

## Workflow 3 — Préparation de réunion

| | |
|---|---|
| **Métier** | Gestion / Tous métiers |
| **Objectif** | Préparer efficacement une réunion avec brief, support et ordre du jour |
| **Difficulté** | Niveau 1 |
| **Temps sans IA** | 2-3 heures |
| **Temps avec IA** | 30 — 45 minutes |

### Étapes

| Étape | Action | Outil |
|-------|--------|-------|
| 1 | Définir l'objectif de la réunion et la liste des participants | Manuel |
| 2 | Demander à Claude : "Prépare un ordre du jour structuré pour une réunion de 1h sur [sujet]. Participants : [liste]. Propose aussi 3 questions clés à aborder et un brief de contexte de 10 lignes." | **Claude** |
| 3 | Mettre en forme l'ordre du jour et le brief dans Google Docs, ajouter les documents de référence en annexe | **Google Docs** |
| 4 | Envoyer l'invitation avec l'ordre du jour en pièce jointe via Calendar/Meet | **Google Calendar** / **Meet** ou **Teams** |
| 5 | Pendant la réunion, utiliser Gemini/Copilot pour la prise de notes automatique | **Google Meet** ou **Teams** |

---

## Workflow 4 — Campagne emailing

| | |
|---|---|
| **Métier** | Marketing / Communication |
| **Objectif** | Créer une séquence de 3 emails pour une campagne marketing |
| **Difficulté** | Niveau 2 |
| **Temps sans IA** | 4-6 heures |
| **Temps avec IA** | 1h30 — 2 heures |

### Étapes

| Étape | Action | Outil |
|-------|--------|-------|
| 1 | Rédiger le brief de campagne : cible, objectif, ton, offre, CTA souhaité | Manuel |
| 2 | Demander à ChatGPT : "Rédige une séquence de 3 emails marketing pour [brief]. Email 1 : présentation de l'offre. Email 2 : rappel avec témoignage client. Email 3 : dernière chance avec urgence. Chaque email : objet accrocheur, corps concis, CTA clair." | **ChatGPT** |
| 3 | Copier les emails dans Google Docs pour relecture et validation par l'équipe (mode suggestion) | **Google Docs** |
| 4 | Intégrer les emails validés dans l'outil d'emailing, programmer l'envoi | **Mailchimp**, **Brevo**, **ActiveCampaign**... |
| 5 | Analyser les résultats (taux d'ouverture, clics) et demander à ChatGPT des suggestions d'optimisation | **ChatGPT** + outil emailing |

---

## Workflow 5 — Réponse à un appel d'offres

| | |
|---|---|
| **Métier** | Commercial / Direction |
| **Objectif** | Analyser un cahier des charges et rédiger une réponse structurée |
| **Difficulté** | Niveau 3 |
| **Temps sans IA** | 2-3 jours |
| **Temps avec IA** | 1 journée |

### Étapes

| Étape | Action | Outil |
|-------|--------|-------|
| 1 | Charger le cahier des charges PDF dans Claude (ou copier les sections clés) avec le prompt : "Analyse ce cahier des charges. Identifie les critères de sélection, les livrables attendus, les contraintes, et les points d'attention. Propose un plan de réponse structuré." | **Claude** |
| 2 | Valider le plan de réponse avec l'équipe commerciale | Manuel |
| 3 | Rédiger chaque section de la réponse dans Google Docs en utilisant Claude pour les parties techniques et les argumentaires | **Claude** + **Google Docs** |
| 4 | Créer le support de soutenance orale dans Google Slides (10-15 slides) | **Google Slides** (avec Gemini ou manuellement) |
| 5 | Relecture finale, vérification de cohérence, ajout des références et annexes | Manuel + **Google Docs** |

> **Important** : Vérifiez que le cahier des charges ne contient pas de clause de confidentialité interdisant le partage avec des outils IA externes. Si c'est le cas, utilisez uniquement Gemini/Copilot (données dans votre tenant).

---

## Workflow 6 — Onboarding d'un nouveau collaborateur

| | |
|---|---|
| **Métier** | Ressources Humaines |
| **Objectif** | Créer un parcours d'intégration complet et personnalisé |
| **Difficulté** | Niveau 1 |
| **Temps sans IA** | 3-4 heures |
| **Temps avec IA** | 1 — 1h30 |

### Étapes

| Étape | Action | Outil |
|-------|--------|-------|
| 1 | Récupérer la fiche de poste et les informations du nouveau collaborateur | Dossier RH |
| 2 | Demander à ChatGPT : "Crée un planning d'onboarding sur 4 semaines pour un [poste] dans une entreprise de [secteur]. Inclus : découverte de l'entreprise, formation outils, rencontres équipe, objectifs 30/60/90 jours, checklist administrative." | **ChatGPT** |
| 3 | Transférer le planning dans Google Sheets avec dates, responsables et statut de réalisation | **Google Sheets** |
| 4 | Rédiger les emails d'accueil (J-7, J-1, Jour J) avec ChatGPT puis les programmer dans Gmail | **ChatGPT** + **Gmail** |
| 5 | Créer le livret d'accueil dans Google Docs à partir du contenu existant enrichi par l'IA | **Google Docs** |

---

## Workflow 7 — Veille concurrentielle

| | |
|---|---|
| **Métier** | Marketing / Stratégie |
| **Objectif** | Réaliser une veille concurrentielle structurée et actionnable |
| **Difficulté** | Niveau 2 |
| **Temps sans IA** | 1-2 jours |
| **Temps avec IA** | 3 — 4 heures |

### Étapes

| Étape | Action | Outil |
|-------|--------|-------|
| 1 | Collecter les informations sur les concurrents : sites web, communiqués, réseaux sociaux, articles de presse | **Perplexity** + navigation web |
| 2 | Compiler les informations et demander à ChatGPT : "Synthétise ces informations sur nos 5 concurrents. Pour chacun : positionnement, forces, faiblesses, dernières actualités, menaces pour notre activité. Propose un tableau comparatif." | **ChatGPT** |
| 3 | Créer le tableau comparatif dans Google Sheets avec des indicateurs visuels | **Google Sheets** |
| 4 | Préparer 5-8 slides de restitution pour la direction avec les insights clés et recommandations stratégiques | **Google Slides** |
| 5 | Mettre en place une veille automatisée (Google Alerts, RSS) pour les mises à jour futures | **Google Alerts** + RSS |

---

## Workflow 8 — Budget prévisionnel

| | |
|---|---|
| **Métier** | Finance / Contrôle de gestion |
| **Objectif** | Construire un budget prévisionnel N+1 à partir des données N |
| **Difficulté** | Niveau 3 |
| **Temps sans IA** | 2-3 jours |
| **Temps avec IA** | 1 journée |

### Étapes

| Étape | Action | Outil |
|-------|--------|-------|
| 1 | Exporter les données financières N depuis Google Sheets (ou le système comptable) | **Google Sheets** / ERP |
| 2 | Copier les données clés dans ChatGPT avec le prompt : "Voici les données financières de l'année N. Propose des hypothèses de budget N+1 réalistes avec 3 scénarios (optimiste, réaliste, pessimiste). Justifie chaque hypothèse. Identifie les postes à surveiller." | **ChatGPT** |
| 3 | Construire le modèle de budget dans Google Sheets avec les 3 scénarios, formules de calcul et mises en forme conditionnelles | **Google Sheets** |
| 4 | Créer la présentation pour la DAF (8-10 slides) avec graphiques, hypothèses et recommandations | **Google Slides** |
| 5 | Préparer les réponses aux questions potentielles avec Claude : "Quelles questions le DAF pourrait-il poser sur ce budget ? Prépare des réponses argumentées." | **Claude** |

> **Attention** : Ne partagez jamais de données financières confidentielles avec des IA externes sans l'accord de votre direction financière.

---

## Workflow 9 — Gestion des réclamations clients

| | |
|---|---|
| **Métier** | Service client / Gestion |
| **Objectif** | Traiter efficacement les réclamations clients avec analyse de sentiment |
| **Difficulté** | Niveau 1 |
| **Temps sans IA** | 30-45 min par réclamation |
| **Temps avec IA** | 10-15 min par réclamation |

### Étapes

| Étape | Action | Outil |
|-------|--------|-------|
| 1 | Recevoir l'email de réclamation du client | **Gmail** / **Outlook** |
| 2 | Copier le message dans Claude avec le prompt : "Analyse cet email de réclamation client. Identifie : le problème principal, le niveau d'urgence (1-5), le sentiment (positif/neutre/négatif/très négatif), les attentes du client. Propose une réponse empathique et professionnelle avec une solution concrète." | **Claude** |
| 3 | Adapter la réponse proposée, personnaliser et envoyer via Gmail | **Gmail** |
| 4 | Consigner la réclamation dans le tableau de suivi (date, client, problème, sentiment, solution, statut) | **Google Sheets** |
| 5 | En fin de mois, analyser le tableau de suivi avec ChatGPT pour identifier les tendances et problèmes récurrents | **ChatGPT** + **Google Sheets** |

---

## Workflow 10 — Revue de performance

| | |
|---|---|
| **Métier** | Ressources Humaines / Management |
| **Objectif** | Préparer et structurer un entretien de performance |
| **Difficulté** | Niveau 2 |
| **Temps sans IA** | 2-3 heures par collaborateur |
| **Temps avec IA** | 45 min — 1 heure par collaborateur |

### Étapes

| Étape | Action | Outil |
|-------|--------|-------|
| 1 | Récupérer l'auto-évaluation du collaborateur et les données de performance (KPIs, projets réalisés) | Dossier RH / SIRH |
| 2 | Coller l'auto-évaluation dans ChatGPT avec le prompt : "Synthétise cette auto-évaluation. Identifie les points forts, les axes d'amélioration, les incohérences éventuelles. Propose 3 questions d'approfondissement pour l'entretien et 3 suggestions d'objectifs SMART pour la période suivante." | **ChatGPT** |
| 3 | Structurer le document d'entretien dans Google Docs : bilan de la période, échanges, objectifs fixés, plan de développement | **Google Docs** |
| 4 | Après l'entretien, compléter le document avec les décisions prises et le faire signer | **Google Docs** |
| 5 | Mettre à jour le tableau de suivi RH avec les objectifs, les formations prévues et la prochaine date d'entretien | **Google Sheets** |

> **Attention** : Les données de performance des collaborateurs sont des données personnelles sensibles. Ne les partagez jamais avec des IA externes sans anonymisation préalable et accord de votre DPO.

---

## Tableau de synthèse des 10 workflows

| N | Workflow | Métier | Outils IA | Outils bureautiques | Temps sans IA | Temps avec IA | Niveau |
|---|---------|--------|-----------|---------------------|---------------|---------------|--------|
| 1 | Rapport mensuel | Gestion | Claude | Docs, PDF | 3-4h | 45min-1h | Niveau 1 |
| 2 | Analyse clients | Commercial | ChatGPT | Sheets, Slides | 4-5h | 1h30-2h | Niveau 2 |
| 3 | Préparation réunion | Tous | Claude | Docs, Meet/Teams | 2-3h | 30-45min | Niveau 1 |
| 4 | Campagne emailing | Marketing | ChatGPT | Docs, outil emailing | 4-6h | 1h30-2h | Niveau 2 |
| 5 | Réponse appel d'offres | Commercial | Claude | Docs, Slides | 2-3 jours | 1 jour | Niveau 3 |
| 6 | Onboarding | RH | ChatGPT | Sheets, Docs, Gmail | 3-4h | 1-1h30 | Niveau 1 |
| 7 | Veille concurrentielle | Marketing | ChatGPT, Perplexity | Sheets, Slides | 1-2 jours | 3-4h | Niveau 2 |
| 8 | Budget prévisionnel | Finance | ChatGPT, Claude | Sheets, Slides | 2-3 jours | 1 jour | Niveau 3 |
| 9 | Gestion réclamations | Gestion | Claude | Gmail, Sheets | 30-45min/récl. | 10-15min/récl. | Niveau 1 |
| 10 | Revue de performance | RH | ChatGPT | Docs, Sheets | 2-3h/collab. | 45min-1h/collab. | Niveau 2 |

---

## Bonnes pratiques communes à tous les workflows

1. **Toujours relire et vérifier** les outputs de l'IA avant de les utiliser ou diffuser
2. **Anonymiser les données sensibles** avant de les partager avec des IA externes (ChatGPT, Claude)
3. **Sauvegarder les prompts efficaces** dans un document partagé pour capitaliser sur l'expérience
4. **Combiner les IA** : utilisez Claude pour l'analyse/rédaction longue et ChatGPT pour les tâches créatives/marketing
5. **Documenter le workflow** pour le rendre reproductible par d'autres collaborateurs
6. **Mesurer le gain de temps** réel pour justifier l'investissement auprès de la direction

---

> **Fiche 37** | Formation IA Tertiaire — Module 2 | Session 8 : Intégration Google Workspace / Microsoft 365

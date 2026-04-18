# SLIDES-03 — Agents IA et Prompting de Base

> **Session 3** — Jour 2, matin (9h00-12h30)
> **Durée** : 3h30 | **Niveau** : Débutant → Intermédiaire
> **Objectifs** : Définir un agent IA, appliquer la méthode CREA, rédiger des prompts professionnels

---

## BLOC 1 — QU'EST-CE QU'UN AGENT IA ? (1h00)

---

### Slide 1 — Page de titre

# Agents IA et Prompting de Base
## Session 3 — Du chatbot à l'agent intelligent

Formation IA pour les Métiers du Tertiaire
Jour 2 — Matin

---

### Slide 2 — Objectifs de la session

## Ce que vous saurez faire à la fin de cette session

1. **Définir** ce qu'est un agent IA et le distinguer d'un chatbot
2. **Identifier** les composants d'un agent IA
3. **Appliquer** la méthode CREA pour structurer vos prompts
4. **Rédiger** des prompts efficaces pour votre métier

---

### Slide 3 — Rappel du jour 1

## Où en sommes-nous ?

✅ Jour 1 matin : Les fondamentaux de l'IA
✅ Jour 1 après-midi : Les LLM en pratique (ChatGPT, Claude, Gemini)
👉 **Aujourd'hui** : On passe au niveau supérieur — les agents IA et le prompting structuré

---

### Slide 4 — L'évolution des assistants numériques

## Du chatbot à l'agent IA : une évolution en 3 étapes

| Génération | Technologie | Capacité |
|-----------|-------------|----------|
| **Chatbot classique** | Arbres de décision | Répond à des questions prédéfinies |
| **LLM conversationnel** | GPT, Claude, Gemini | Génère du texte, comprend le contexte |
| **Agent IA** | LLM + Outils + Mémoire | Raisonne, agit, utilise des outils |

---

### Slide 5 — Le chatbot classique

## Le chatbot classique — Le répondeur automatique

**Comment ça marche ?**
- Des réponses pré-écrites par des humains
- Un arbre de décision : SI le client dit X → répondre Y
- Aucune compréhension réelle du langage

**Exemple typique :**
> "Pour le service commercial, tapez 1. Pour le SAV, tapez 2."

**Limites :**
- Ne comprend que les cas prévus
- Incapable de gérer l'imprévu
- Frustrant pour l'utilisateur

---

### Slide 6 — Le LLM conversationnel

## Le LLM conversationnel — L'expert en conversation

**Comment ça marche ?**
- Comprend le langage naturel
- Génère des réponses originales et contextuelles
- S'adapte au ton et au style demandé

**Ce que ChatGPT/Claude font bien :**
- Rédiger, résumer, traduire, expliquer
- Répondre à des questions ouvertes
- Maintenir une conversation cohérente

**Ce qu'ils ne font PAS (seuls) :**
- Aller chercher des informations en temps réel
- Exécuter des actions (envoyer un email, modifier un fichier)
- Se souvenir de vous entre les conversations

---

### Slide 7 — L'agent IA

## L'agent IA — L'assistant qui agit

**Définition :**
> Un agent IA est un système qui utilise un LLM pour **raisonner**, **planifier** et **exécuter des actions** de manière autonome afin d'atteindre un objectif.

**La différence clé :**
- Le LLM **parle**
- L'agent IA **parle ET agit**

---

### Slide 8 — Analogie : le stagiaire vs l'employé autonome

## Comprendre la différence avec une analogie

| | LLM seul | Agent IA |
|--|---------|----------|
| **Analogie** | Un stagiaire brillant qui attend vos instructions | Un employé expérimenté qui prend des initiatives |
| **Vous dites** | "Rédige-moi cet email" | "Gère la communication avec ce client" |
| **Il fait** | Rédige l'email | Recherche l'historique du client, rédige l'email, l'adapte au contexte, propose un suivi |

---

### Slide 9 — Anatomie d'un agent IA

## Les 4 composants d'un agent IA

```
┌─────────────────────────────────────┐
│          INSTRUCTIONS SYSTÈME       │
│    (La mission, les règles)         │
├─────────────────────────────────────┤
│                                     │
│    ┌───────────────────────┐        │
│    │   MODÈLE DE LANGAGE   │        │
│    │   (Le "cerveau")      │        │
│    │   GPT-4, Claude, etc. │        │
│    └───────────────────────┘        │
│         ▲           ▼               │
│    ┌─────────┐  ┌──────────┐        │
│    │ MÉMOIRE │  │  OUTILS  │        │
│    │(Contexte│  │(Actions) │        │
│    │ données)│  │          │        │
│    └─────────┘  └──────────┘        │
│                                     │
└─────────────────────────────────────┘
```

---

### Slide 10 — Le modèle de langage (le cerveau)

## Composant 1 : Le Modèle de Langage

**C'est le "cerveau" de l'agent.**

- Comprend les instructions en langage naturel
- Raisonne sur les problèmes
- Génère des réponses et des plans d'action
- Décide quels outils utiliser et quand

**Les modèles utilisés :**
- GPT-4o (OpenAI)
- Claude 3.5 Sonnet (Anthropic)
- Gemini Pro (Google)
- Mistral Large (Mistral AI)

---

### Slide 11 — Les outils (les mains)

## Composant 2 : Les Outils

**Ce sont les "mains" de l'agent — ce qui lui permet d'agir.**

Exemples d'outils :
- 🔍 **Recherche web** : chercher des informations en temps réel
- 📊 **Analyse de données** : lire et analyser des fichiers CSV/Excel
- 📧 **Email** : lire, rédiger et envoyer des emails
- 📄 **Documents** : lire, modifier et créer des documents
- 🗓️ **Calendrier** : consulter et créer des événements
- 🔗 **APIs** : se connecter à d'autres logiciels (CRM, ERP...)

---

### Slide 12 — La mémoire (le contexte)

## Composant 3 : La Mémoire

**C'est ce qui permet à l'agent de se souvenir et de s'améliorer.**

| Type de mémoire | Description | Exemple |
|----------------|-------------|---------|
| **Conversation** | Le fil de la discussion en cours | "Vous m'avez dit préférer un ton formel" |
| **Base de connaissances** | Vos documents de référence | Convention collective, procédures internes |
| **Mémoire longue** | Ce qu'il retient entre les sessions | "M. Dupont est responsable marketing" |

---

### Slide 13 — Les instructions système (la mission)

## Composant 4 : Les Instructions Système

**C'est la "fiche de poste" de l'agent — sa mission et ses règles.**

Exemple d'instructions système pour un agent "Assistant RH" :
```
Tu es un assistant RH expert en droit du travail français.
Tu réponds aux questions des salariés sur la convention collective Syntec.
Tu ne donnes jamais de conseil juridique définitif.
Tu recommandes toujours de consulter le service RH pour les cas complexes.
Tu réponds en français, de manière claire et bienveillante.
```

---

### Slide 14 — Exemples concrets d'agents IA dans le tertiaire

## Des agents IA que vous connaissez peut-être déjà

| Agent | Usage | Composants |
|-------|-------|-----------|
| **ChatGPT avec GPTs** | Assistant personnalisé | LLM + instructions + documents |
| **Claude Projects** | Analyse de documents | LLM + base de connaissances |
| **Intercom / Zendesk AI** | Support client | LLM + historique client + FAQ |
| **Reclaim.ai / Motion** | Planification | LLM + calendrier + règles |
| **NotebookLM** | Recherche documentaire | LLM + vos documents uploadés |
| **Microsoft Copilot** | Suite bureautique | LLM + Word/Excel/PowerPoint |

---

### Slide 15 — Démonstration en direct

## 🖥️ Démonstration : Créer un GPT personnalisé

**Objectif :** Créer un agent "Assistant FAQ RH" en 10 minutes

**Étapes :**
1. Accéder au GPT Builder dans ChatGPT
2. Définir les instructions système
3. Uploader un document de référence (extrait convention collective)
4. Configurer les capacités (recherche, analyse)
5. Tester avec 3 questions types

*[Le formateur fait la démonstration en direct]*

---

### Slide 16 — Ce qu'il faut retenir

## Résumé : Chatbot vs LLM vs Agent IA

| | Chatbot | LLM | Agent IA |
|--|---------|-----|----------|
| Comprend le langage | ❌ | ✅ | ✅ |
| Génère du contenu | ❌ | ✅ | ✅ |
| Utilise des outils | ❌ | ❌ | ✅ |
| Agit de manière autonome | ❌ | ❌ | ✅ |
| A une mémoire persistante | ❌ | Limitée | ✅ |
| Suit des instructions complexes | ❌ | Partiellement | ✅ |

---

## BLOC 2 — LA MÉTHODE CREA (1h00)

---

### Slide 17 — Transition

## Maintenant que vous comprenez les agents IA...

Il est temps d'apprendre à **communiquer efficacement** avec eux.

La qualité de ce que l'IA produit dépend à **80% de la qualité de votre prompt.**

> Un bon prompt = un bon résultat
> Un mauvais prompt = un résultat décevant

---

### Slide 18 — Le problème du prompting intuitif

## Pourquoi vos premiers prompts ne marchent pas bien ?

**Prompt typique d'un débutant :**
> "Fais-moi un email pour un client"

**Ce qui manque :**
- Qui êtes-vous ?
- Quel type de client ?
- Quel est l'objectif de l'email ?
- Quel ton ? Quelle longueur ?
- Quel format de sortie ?

**Résultat :** Un email générique, inutilisable en l'état.

---

### Slide 19 — Introduction à la méthode CREA

## La méthode CREA : votre framework de prompting

```
╔═══════════════════════════════════════╗
║                                       ║
║   C — CONTEXTE                        ║
║   Qui êtes-vous ? Quelle situation ?  ║
║                                       ║
║   R — RÔLE                            ║
║   Quel rôle doit jouer l'IA ?         ║
║                                       ║
║   E — EXPLICITE                       ║
║   Quel format, ton, contraintes ?     ║
║                                       ║
║   A — ACTION                          ║
║   Que doit faire concrètement l'IA ?  ║
║                                       ║
╚═══════════════════════════════════════╝
```

---

### Slide 20 — C comme Contexte

## C — CONTEXTE : Plantez le décor

**Question à se poser :** "Dans quelle situation suis-je ?"

**Ce qu'il faut inclure :**
- Votre fonction / votre entreprise
- Le secteur d'activité
- La taille de l'entreprise
- La situation spécifique (lancement, crise, routine...)
- Le destinataire ou le public cible

**Exemple :**
> "Je suis responsable marketing dans une PME de 50 salariés, secteur B2B, industrie agroalimentaire. Nous lançons un nouveau produit bio destiné aux restaurateurs."

---

### Slide 21 — R comme Rôle

## R — RÔLE : Donnez une identité à l'IA

**Question à se poser :** "Quel expert me serait le plus utile ?"

**Ce qu'il faut inclure :**
- Le métier ou l'expertise de l'IA
- Son niveau d'expérience
- Sa spécialisation éventuelle

**Exemples de rôles :**
| Métier | Rôle possible |
|--------|--------------|
| RH | "Tu es un consultant RH expert en recrutement tech" |
| Marketing | "Tu es un copywriter spécialisé en B2B industriel" |
| Finance | "Tu es un contrôleur de gestion avec 15 ans d'expérience" |
| Commercial | "Tu es un coach commercial spécialiste du cold emailing" |
| Gestion | "Tu es un assistant de direction expérimenté" |

---

### Slide 22 — E comme Explicite

## E — EXPLICITE : Soyez précis sur le format

**Question à se poser :** "À quoi doit ressembler le résultat ?"

**Ce qu'il faut préciser :**
- **Format** : paragraphe, liste à puces, tableau, email, rapport...
- **Longueur** : "en 200 mots", "en 5 points", "en 1 page"
- **Ton** : formel, conversationnel, expert, pédagogique...
- **Langue** : français, anglais, les deux...
- **Contraintes** : "ne mentionne pas X", "inclus toujours Y"

**Exemple :**
> "Rédige en français, ton professionnel mais accessible, maximum 200 mots, format avec des puces, inclus un appel à l'action à la fin."

---

### Slide 23 — A comme Action

## A — ACTION : Dites exactement ce que vous voulez

**Question à se poser :** "Quelle est la tâche concrète ?"

**Ce qu'il faut inclure :**
- Le verbe d'action (rédige, analyse, génère, compare, résume, traduis...)
- L'objet précis (un email, une fiche, 3 idées, un plan...)
- Le critère de succès (si pertinent)

**Exemple :**
> "Génère 3 accroches de campagne emailing pour notre nouveau produit bio. Chaque accroche doit être percutante, mentionner le bénéfice principal et faire moins de 50 caractères."

---

### Slide 24 — La méthode CREA en action — Exemple complet

## Exemple complet : prompt CREA pour le Marketing

**Sans CREA :**
> "Fais-moi un post LinkedIn"

**Avec CREA :**

> **[C]** Je suis responsable marketing dans une PME B2B agroalimentaire (50 salariés). Nous lançons un nouveau produit bio pour les restaurateurs.
>
> **[R]** Tu es un expert en social media marketing B2B, spécialisé dans le secteur food & beverage.
>
> **[E]** Rédige en français, ton professionnel mais engageant, entre 150 et 200 mots, avec des emojis pertinents et 3 hashtags. Inclus un appel à l'action.
>
> **[A]** Rédige un post LinkedIn annonçant le lancement de notre gamme de sauces bio "TerraVerde", en mettant en avant la traçabilité et le rapport qualité-prix.

---

### Slide 25 — Comparaison des résultats

## Le résultat : sans CREA vs avec CREA

| | Sans CREA | Avec CREA |
|--|-----------|-----------|
| **Pertinence** | Générique, pas adapté au secteur | Ciblé B2B agroalimentaire |
| **Ton** | Aléatoire | Professionnel et engageant |
| **Format** | Trop long ou trop court | 150-200 mots, structuré |
| **Utilisabilité** | Nécessite beaucoup de retouches | Publiable avec ajustements mineurs |
| **Temps gagné** | ~5 min de retouches | ~1 min de relecture |

---

### Slide 26 — CREA appliqué aux RH

## Exemple CREA — Ressources Humaines

**Contexte :** Je suis DRH dans un cabinet de conseil en management (120 salariés). Nous cherchons un consultant senior en stratégie.

**Rôle :** Tu es un expert en rédaction d'offres d'emploi, spécialisé dans le secteur du conseil.

**Explicite :** Rédige en français, ton attractif et professionnel, format structuré avec sections (entreprise, missions, profil, avantages), entre 400 et 500 mots.

**Action :** Rédige une offre d'emploi pour un poste de Consultant Senior en Stratégie, en mettant en avant notre culture d'entreprise collaborative et nos opportunités de carrière.

---

### Slide 27 — CREA appliqué à la Finance

## Exemple CREA — Finance

**Contexte :** Je suis contrôleur de gestion dans une ETI industrielle (300 salariés). Le CA du Q3 a baissé de 8% par rapport au Q2.

**Rôle :** Tu es un analyste financier senior spécialisé dans l'industrie manufacturière.

**Explicite :** Rédige en français, ton factuel et analytique, format mémo de 300 mots maximum avec 3 sections : constat, analyse, recommandations.

**Action :** Rédige un mémo de synthèse pour le CODIR expliquant les causes probables de cette baisse et proposant 3 axes d'amélioration pour le Q4.

---

### Slide 28 — CREA appliqué au Commercial

## Exemple CREA — Commercial

**Contexte :** Je suis commercial B2B dans une ESN (entreprise de services numériques). Je prospecte des PME qui n'ont pas encore digitalisé leur processus RH.

**Rôle :** Tu es un expert en prospection B2B et cold emailing, avec une expertise dans la vente de solutions SaaS.

**Explicite :** Rédige en français, ton direct mais respectueux, email de 80 à 100 mots maximum, avec un objet accrocheur de moins de 50 caractères.

**Action :** Rédige un email de premier contact pour un DRH de PME (50-200 salariés) qui utilise encore Excel pour gérer ses congés et absences. L'objectif est d'obtenir un rendez-vous de 15 minutes.

---

### Slide 29 — CREA appliqué à la Gestion

## Exemple CREA — Gestion / Assistanat

**Contexte :** Je suis assistante de direction dans une entreprise de services (80 salariés). Je viens de prendre des notes manuscrites lors d'un CODIR de 2h.

**Rôle :** Tu es un expert en rédaction de comptes-rendus professionnels, rigoureux et synthétique.

**Explicite :** Rédige en français, ton formel, format compte-rendu structuré avec : date, participants, ordre du jour, décisions prises, actions à mener (responsable + échéance).

**Action :** À partir des notes que je vais te fournir, rédige un compte-rendu de réunion professionnel prêt à être envoyé aux participants.

---

### Slide 30 — Les erreurs courantes avec CREA

## Les pièges à éviter

| Erreur | Problème | Solution |
|--------|----------|----------|
| **Contexte trop vague** | "Je travaille dans une entreprise" | Précisez le secteur, la taille, votre poste |
| **Rôle non pertinent** | "Tu es un assistant" | Donnez un rôle d'expert spécialisé |
| **Pas assez explicite** | "Fais quelque chose de bien" | Précisez format, longueur, ton |
| **Action ambiguë** | "Aide-moi avec mon projet" | Utilisez un verbe d'action précis |
| **Trop d'informations** | Prompt de 500 mots | Allez à l'essentiel, 100-200 mots suffisent |

---

### Slide 31 — L'itération : la clé du succès

## Un bon prompt se construit en 2-3 itérations

**Étape 1 :** Envoyez votre prompt CREA
**Étape 2 :** Analysez la réponse — qu'est-ce qui manque ou ne va pas ?
**Étape 3 :** Affinez avec des instructions complémentaires

**Prompts d'itération utiles :**
- "C'est trop long, réduis à 150 mots en gardant les points clés"
- "Le ton est trop familier, adopte un ton plus corporate"
- "Ajoute des chiffres concrets pour renforcer l'argumentation"
- "Reformule le paragraphe 2, il n'est pas assez clair"
- "Propose 3 variantes de l'accroche"

---

## BLOC 3 — ATELIER PRATIQUE (1h15)

---

### Slide 32 — Consignes de l'atelier

## 🛠️ Atelier : Rédigez vos prompts CREA

### Exercice 1 — Individuel (20 min)
Rédigez **3 prompts CREA** liés à votre métier au quotidien.

**Consignes :**
- Choisissez 3 tâches réelles de votre travail
- Pour chaque tâche, rédigez un prompt structuré C-R-E-A
- Testez chaque prompt sur ChatGPT ou Claude
- Notez la qualité de la réponse (1 à 5)

---

### Slide 33 — Idées de prompts par métier

## Besoin d'inspiration ? Voici des idées par métier

| Métier | Idées de prompts |
|--------|-----------------|
| **RH** | Offre d'emploi, réponse à candidature, plan d'intégration, email de refus bienveillant |
| **Marketing** | Post réseaux sociaux, newsletter, brief créatif, analyse de concurrence |
| **Finance** | Commentaire de gestion, explication d'écart, synthèse de rapport, note de frais |
| **Commercial** | Email de prospection, argumentaire produit, fiche rendez-vous, proposition commerciale |
| **Gestion** | Compte-rendu, note de service, planning, convocation réunion |

---

### Slide 34 — Exercice 2 : Test croisé

## 🛠️ Exercice 2 — En binômes (20 min)

1. **Échangez** vos 3 prompts avec votre voisin(e)
2. **Testez** les prompts de votre partenaire sur ChatGPT ou Claude
3. **Évaluez** chaque résultat avec la grille fournie :

| Critère | Note /5 |
|---------|---------|
| Le contexte est-il suffisant ? | /5 |
| Le rôle est-il pertinent ? | /5 |
| Les contraintes sont-elles claires ? | /5 |
| L'action est-elle précise ? | /5 |
| Le résultat est-il utilisable ? | /5 |

4. **Discutez** : comment améliorer les prompts de l'autre ?

---

### Slide 35 — Exercice 3 : Partage collectif

## 🛠️ Exercice 3 — Collectif (20 min)

**Les meilleurs prompts sont partagés et analysés ensemble.**

Pour chaque prompt présenté, on se pose 3 questions :
1. **Pourquoi** ce prompt fonctionne-t-il bien ?
2. **Comment** pourrait-on l'améliorer encore ?
3. **Peut-on** le transformer en template réutilisable ?

*Le formateur sélectionne 4-5 prompts représentatifs de différents métiers.*

---

### Slide 36 — Créer des templates réutilisables

## Transformez vos meilleurs prompts en templates

**Un template = un prompt avec des variables à remplir**

```
[CONTEXTE] Je suis {votre_poste} dans une entreprise de
{taille} salariés, secteur {secteur}. {situation_spécifique}.

[RÔLE] Tu es un {expert_spécialisé} avec {expérience}.

[EXPLICITE] Rédige en {langue}, ton {ton}, format {format},
{longueur}. {contraintes_spécifiques}.

[ACTION] {verbe_action} {objet_précis} en mettant en avant
{points_clés}.
```

**Conseil :** Sauvegardez vos templates dans un document partagé ou dans les instructions d'un GPT personnalisé.

---

## BLOC 4 — ÉVALUATION INTERMÉDIAIRE (15 min)

---

### Slide 37 — Évaluation niveau débutant

## 📝 QCM — Évaluation Niveau Débutant

**20 questions** couvrant les Sessions 1 à 3 :
- 7 questions sur les fondamentaux de l'IA (Session 1)
- 6 questions sur les LLM (Session 2)
- 7 questions sur les agents IA et le prompting (Session 3)

**Seuil de validation :** 12/20 minimum

**Durée :** 15 minutes

*Distribution du QCM (FICHE-12)*

---

### Slide 38 — Correction collective

## Correction du QCM

*[Le formateur corrige les questions une par une, en prenant le temps d'expliquer les réponses qui posent le plus de difficultés]*

**Points clés à retenir :**
- Un agent IA ≠ un chatbot ≠ un LLM simple
- La méthode CREA structure vos interactions avec l'IA
- Le prompt est l'interface entre vous et l'IA : sa qualité détermine la qualité du résultat

---

### Slide 39 — Synthèse de la session

## Ce que nous avons vu aujourd'hui

| Concept | Point clé |
|---------|-----------|
| **Agent IA** | Un LLM + des outils + une mémoire + des instructions |
| **4 composants** | Modèle, outils, mémoire, instructions système |
| **Méthode CREA** | Contexte, Rôle, Explicite, Action |
| **Itération** | Un bon résultat = 2-3 échanges, pas 1 seul prompt |
| **Templates** | Sauvegardez vos prompts efficaces pour les réutiliser |

---

### Slide 40 — Transition vers l'après-midi

## Cet après-midi : Prompting Avancé

**Au programme de la Session 4 :**
- Few-shot prompting : donner des exemples à l'IA
- Chain-of-thought : faire raisonner l'IA étape par étape
- Chaînes de prompts : enchaîner plusieurs prompts pour des tâches complexes
- Structuration avancée des outputs

**Conseil :** Gardez vos prompts CREA du matin, nous les améliorerons cet après-midi !

---

## SLIDES BONUS — Pour enrichir si besoin

---

### Slide 41 — Glossaire agents IA

## Glossaire : Les termes clés des agents IA

| Terme | Définition simple |
|-------|------------------|
| **Agent** | Programme IA qui raisonne et agit de façon autonome |
| **Prompt** | L'instruction que vous donnez à l'IA |
| **Instructions système** | Les règles permanentes de l'agent |
| **Outil (Tool)** | Une capacité d'action de l'agent (recherche, calcul...) |
| **RAG** | Technique pour que l'IA utilise vos propres documents |
| **Hallucination** | Quand l'IA invente une information fausse |
| **Token** | L'unité de texte traitée par le LLM |

---

### Slide 42 — Les limites des agents IA

## Ce que les agents IA ne savent PAS faire (encore)

- ❌ **Comprendre vraiment** : ils simulent la compréhension, ne la possèdent pas
- ❌ **Garantir l'exactitude** : ils peuvent halluciner (inventer des informations)
- ❌ **Remplacer l'expertise humaine** : ils sont un outil, pas un expert
- ❌ **Gérer l'émotion** : ils n'ont pas d'empathie réelle
- ❌ **Prendre des décisions éthiques** : le jugement final reste humain

**Règle d'or :** L'IA est votre assistant, pas votre remplaçant. Vous restez responsable de ce que vous produisez avec son aide.

---

### Slide 43 — Le futur des agents IA

## Où vont les agents IA ? Tendances 2025-2026

- **Agents multi-modaux** : texte + image + audio + vidéo dans un même agent
- **Agents collaboratifs** : plusieurs agents qui travaillent ensemble
- **Agents d'entreprise** : intégrés aux systèmes internes (ERP, CRM, SIRH)
- **Agents spécialisés par métier** : un agent RH, un agent Finance, un agent Legal...
- **Orchestration** : des plateformes pour gérer ses agents IA comme une équipe

---

### Slide 44 — Récapitulatif CREA — Aide-mémoire

## Aide-mémoire CREA — À garder sous la main

```
╔══════════════════════════════════════════════════╗
║                                                  ║
║  C  CONTEXTE   → Qui suis-je ? Quelle situation?║
║                                                  ║
║  R  RÔLE       → Quel expert me faut-il ?        ║
║                                                  ║
║  E  EXPLICITE  → Format, ton, longueur,          ║
║                  contraintes ?                    ║
║                                                  ║
║  A  ACTION     → Quel verbe d'action +           ║
║                  quel objet précis ?              ║
║                                                  ║
╚══════════════════════════════════════════════════╝
```

**Astuce :** Commencez toujours par le Contexte, terminez toujours par l'Action.

---

### Slide 45 — Ressources complémentaires

## Pour aller plus loin

**Fiches distribuées :**
- FICHE-09 : La méthode CREA — Guide pratique (2 pages)
- FICHE-10 : 20 prompts modèles par métier (4 pages)
- FICHE-11 : Grille d'évaluation de la qualité d'un prompt

**À explorer :**
- Le GPT Builder de ChatGPT (version gratuite limitée, version Plus complète)
- Les Projects de Claude (claude.ai)
- NotebookLM de Google (gratuit)

---

*Fin de SLIDES-03 — 45 slides (+ bonus si nécessaire)*

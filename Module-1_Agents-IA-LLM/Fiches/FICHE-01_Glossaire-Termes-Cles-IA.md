# FICHE-01 — Glossaire des Termes Clés de l'IA

> **Formation IA pour les Métiers du Tertiaire**
> Fiche de référence — À conserver tout au long de la formation

---

## Les Fondamentaux

| Terme | Définition | Exemple concret |
|-------|-----------|-----------------|
| **Intelligence Artificielle (IA)** | Ensemble de technologies permettant à des machines de simuler des capacités cognitives humaines (compréhension, raisonnement, apprentissage) | Un filtre anti-spam qui apprend à reconnaître les emails indésirables |
| **IA faible (étroite)** | IA spécialisée dans une tâche précise. C'est l'IA qui existe aujourd'hui | ChatGPT génère du texte, mais ne peut pas conduire une voiture |
| **IA forte (générale)** | IA hypothétique capable de réaliser n'importe quelle tâche intellectuelle humaine. N'existe pas encore | Concept de science-fiction (HAL 9000, Jarvis) |
| **IA générative** | Sous-catégorie de l'IA capable de créer du contenu nouveau : texte, images, audio, vidéo, code | ChatGPT rédige un email, DALL-E crée une image |

---

## Machine Learning & Deep Learning

| Terme | Définition | Exemple concret |
|-------|-----------|-----------------|
| **Machine Learning (ML)** | Méthode d'IA où l'ordinateur apprend à partir de données, sans être explicitement programmé pour chaque cas | Netflix qui recommande des films basé sur vos habitudes |
| **Apprentissage supervisé** | Le modèle apprend à partir d'exemples étiquetés (input → output connu) | Apprendre à détecter les spams à partir d'exemples de spams et non-spams |
| **Apprentissage non supervisé** | Le modèle trouve des patterns dans des données non étiquetées | Segmenter automatiquement les clients en groupes similaires |
| **Deep Learning** | Sous-ensemble du ML utilisant des réseaux de neurones à plusieurs couches, capable de traiter des données très complexes | Reconnaissance faciale, traduction automatique |
| **Réseau de neurones** | Architecture informatique inspirée (très librement) du cerveau humain, avec des couches de "neurones" interconnectés | Le moteur derrière la reconnaissance vocale de Siri |
| **Entraînement** | Processus par lequel un modèle apprend à partir de données. Peut durer des jours/semaines et coûter des millions | GPT-4 a été entraîné sur des milliards de textes |
| **Données d'entraînement** | L'ensemble des données utilisées pour entraîner un modèle | Livres, articles, sites web, conversations... |

---

## LLM et IA Générative

| Terme | Définition | Exemple concret |
|-------|-----------|-----------------|
| **LLM (Large Language Model)** | Grand modèle de langage — un type de réseau de neurones entraîné sur d'immenses quantités de texte pour comprendre et générer du langage | GPT-4, Claude, Gemini, Mistral |
| **Token** | L'unité de texte traitée par un LLM. Un mot = 1 à 3 tokens environ. Les espaces et la ponctuation sont aussi des tokens | "Bonjour" = 1 token, "Intelligence artificielle" = 3-4 tokens |
| **Fenêtre de contexte** | La quantité de texte qu'un LLM peut "voir" en une fois. Mesurée en tokens | GPT-4o : 128 000 tokens (~300 pages), Claude : 200 000 tokens (~500 pages) |
| **Prompt** | L'instruction ou la question que vous donnez à l'IA | "Rédige un email de prospection pour un DRH de PME" |
| **Complétion / Réponse** | Le texte généré par le LLM en réponse à votre prompt | L'email rédigé par ChatGPT |
| **Température** | Paramètre qui contrôle la "créativité" des réponses. Basse = prévisible. Haute = créatif/aléatoire | Température 0 = toujours la même réponse. Température 1 = réponses variées |
| **Hallucination** | Quand le LLM génère des informations fausses ou inventées, présentées comme vraies | Citer un article scientifique qui n'existe pas |
| **Fine-tuning** | Processus d'adaptation d'un modèle pré-entraîné à une tâche spécifique avec des données supplémentaires | Adapter GPT pour qu'il parle comme votre marque |

---

## Agents IA et Outils

| Terme | Définition | Exemple concret |
|-------|-----------|-----------------|
| **Agent IA** | Système utilisant un LLM pour raisonner, planifier et exécuter des actions de manière autonome | Un agent qui recherche des infos, analyse un doc, puis rédige un rapport |
| **Chatbot** | Programme de conversation, souvent basé sur des règles prédéfinies (plus simple qu'un agent IA) | Le chat d'assistance de votre banque en ligne |
| **Instructions système** | Les règles et la "personnalité" permanentes données à un agent IA | "Tu es un assistant RH, tu réponds toujours en français" |
| **RAG (Retrieval-Augmented Generation)** | Technique permettant au LLM de consulter vos propres documents avant de répondre | Uploader la convention collective dans Claude pour qu'il y réponde |
| **API (Application Programming Interface)** | Interface permettant à deux logiciels de communiquer entre eux | Connecter ChatGPT à Google Sheets via Make |
| **No-code** | Outils permettant de créer des automatisations sans écrire de code | Make, Zapier, n8n |
| **Workflow** | Séquence d'étapes automatisées connectant plusieurs outils | "Quand je reçois un email → l'IA le résume → résumé envoyé sur Slack" |
| **GPT personnalisé (Custom GPT)** | Un assistant ChatGPT configuré avec des instructions et documents spécifiques | Un GPT "Assistant FAQ RH" avec votre convention collective |

---

## Prompting

| Terme | Définition | Exemple concret |
|-------|-----------|-----------------|
| **Méthode CREA** | Framework de prompting : Contexte, Rôle, Explicite, Action | Voir FICHE-09 pour le guide complet |
| **Zero-shot** | Donner une instruction sans fournir d'exemple | "Traduis ce texte en anglais" |
| **Few-shot** | Fournir 2-3 exemples du résultat attendu avant la demande | "Voici 2 exemples de fiches produit. Crée-en une 3ème sur le même modèle" |
| **Chain-of-thought** | Demander au LLM de raisonner étape par étape | "Analyse ce problème étape par étape avant de proposer une solution" |
| **Chaîne de prompts** | Séquence de plusieurs prompts où la sortie de l'un sert d'entrée au suivant | Prompt 1 : analyser → Prompt 2 : structurer → Prompt 3 : rédiger |
| **Itération** | Affiner la réponse de l'IA par des échanges successifs | "C'est trop long, réduis à 150 mots" → "Change le ton pour plus formel" |

---

## Éthique et Cadre Légal

| Terme | Définition | Exemple concret |
|-------|-----------|-----------------|
| **Biais algorithmique** | Discrimination involontaire dans les résultats de l'IA, héritée des données d'entraînement | Un outil de screening CV qui défavorise certains profils |
| **RGPD** | Règlement Général sur la Protection des Données (Europe, 2018) | Interdiction de saisir des données personnelles de clients dans ChatGPT sans précaution |
| **AI Act** | Règlement européen sur l'IA (2024), classant les systèmes IA par niveau de risque | Les systèmes de scoring social = interdits. Les chatbots = risque limité |
| **Propriété intellectuelle** | Question juridique : qui est l'auteur d'un contenu généré par l'IA ? | Un texte marketing généré par ChatGPT vous appartient-il ? (débat en cours) |
| **Open source** | Modèle dont le code/poids est publiquement accessible | Mistral, LLaMA (Meta) — à l'opposé de GPT-4 (propriétaire) |

# FICHE-16 — Le RAG Expliqué Simplement

> **Formation IA pour les Métiers du Tertiaire**
> Fiche infographique — Session 5 (1 page)

---

## Le problème

```
╔══════════════════════════════════════════════════════════╗
║                                                          ║
║   Vous : "Quelle est notre politique de télétravail ?"   ║
║                                                          ║
║   ChatGPT : "En général, les entreprises proposent       ║
║   2 à 3 jours de télétravail par semaine..."             ║
║                                                          ║
║   ❌ Réponse GÉNÉRIQUE — Il ne connaît pas VOTRE         ║
║   accord d'entreprise !                                  ║
║                                                          ║
╚══════════════════════════════════════════════════════════╝
```

**Les LLM connaissent le monde... mais PAS votre entreprise.**
Ils n'ont jamais lu votre convention collective, vos procédures internes, vos rapports ou vos fiches produit.

---

## La solution : le RAG

**RAG = Retrieval-Augmented Generation**
(Génération Augmentée par la Récupération)

En français : **on donne vos documents à l'IA pour qu'elle réponde en se basant dessus.**

---

## Comment ça marche ? En 3 étapes

```
ÉTAPE 1 : INDEXATION                    ÉTAPE 2 : RECHERCHE
Vos documents sont                      Quand vous posez une question,
découpés et indexés                      le système cherche les passages
                                        pertinents dans vos documents

┌──────────┐                            ┌──────────────────┐
│ Accord   │                            │ "Quelle est      │
│ télé-    │──→ 📦 Morceaux 1,2,3      │  notre politique  │
│ travail  │                            │  de télétravail?" │
├──────────┤                            └────────┬─────────┘
│ Convention│──→ 📦 Morceaux 4,5,6               │
│ collective│                                    ▼
├──────────┤                            🔍 Recherche dans
│ Procédures│──→ 📦 Morceaux 7,8,9     les morceaux indexés
│ internes │                                    │
└──────────┘                                    ▼
                                        📦 Morceaux 1, 2
                                        (les plus pertinents)


ÉTAPE 3 : GÉNÉRATION

Le LLM reçoit votre question + les morceaux pertinents
et génère une réponse BASÉE SUR VOS DOCUMENTS

┌────────────────────────────────────────┐
│                                        │
│  Question + Morceaux pertinents        │
│         ↓                              │
│     🧠 LLM                            │
│         ↓                              │
│  "Selon notre accord d'entreprise      │
│   signé le 15/01/2024, les salariés    │
│   peuvent télétravailler 3 jours       │
│   par semaine, sous réserve de         │
│   l'accord du manager..."             │
│                                        │
│  ✅ Réponse SPÉCIFIQUE à votre         │
│  entreprise, avec la bonne source !    │
│                                        │
└────────────────────────────────────────┘
```

---

## L'analogie de la bibliothèque

| Sans RAG | Avec RAG |
|----------|----------|
| Vous demandez à un expert qui n'a jamais mis les pieds dans votre entreprise | Vous demandez à un expert qui a d'abord consulté votre bibliothèque interne |
| Il répond avec des connaissances générales | Il répond en citant VOS documents |
| "En général, les entreprises font..." | "Selon votre accord du 15/01/2024, article 3..." |

---

## Les outils RAG accessibles SANS code

| Outil | Comment faire du RAG | Niveau |
|-------|---------------------|--------|
| **ChatGPT** | Uploader un fichier dans la conversation | Débutant |
| **ChatGPT (GPT Builder)** | Créer un GPT avec des documents de référence | Intermédiaire |
| **Claude** | Uploader des documents dans la conversation | Débutant |
| **Claude Projects** | Créer un Project avec une base documentaire permanente | Intermédiaire |
| **NotebookLM (Google)** | Uploader jusqu'à 50 sources, poser des questions | Débutant |

---

## Conseils pratiques

**Pour de meilleurs résultats avec le RAG :**

1. **Documents propres** : PDF avec du texte (pas des scans/images), documents bien structurés
2. **Soyez spécifique** : "Que dit l'article 5 de notre accord ?" plutôt que "Parle-moi du télétravail"
3. **Vérifiez les sources** : demandez à l'IA de citer le passage exact du document
4. **Limites** : les très longs documents (>200 pages) peuvent être mal traités — découpez-les

---

## Ce que le RAG ne fait PAS

- ❌ Remplacer la lecture humaine pour les décisions importantes
- ❌ Garantir que l'IA a bien compris un document complexe (contrat, texte de loi)
- ❌ Mettre à jour automatiquement quand vos documents changent (il faut re-uploader)
- ❌ Protéger la confidentialité — attention à ce que vous uploadez et où

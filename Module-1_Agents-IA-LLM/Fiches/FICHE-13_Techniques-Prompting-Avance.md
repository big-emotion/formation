# FICHE-13 — Techniques de Prompting Avancé — Résumé Visuel

> **Formation IA pour les Métiers du Tertiaire**
> Fiche de référence — Session 4 (2 pages)

---

## Vue d'ensemble des techniques

```
                    TECHNIQUES DE PROMPTING
                    ═══════════════════════

    BASIQUE                          AVANCÉ
    ───────                          ──────
    ┌─────────────┐                  ┌──────────────────┐
    │ Zero-shot   │ ──── évolue ──→  │ Few-shot         │
    │ (pas        │                  │ (avec exemples)  │
    │ d'exemple)  │                  │                  │
    └─────────────┘                  └──────────────────┘

    ┌─────────────┐                  ┌──────────────────┐
    │ Prompt      │ ──── évolue ──→  │ Chain-of-thought │
    │ direct      │                  │ (raisonnement    │
    │             │                  │  étape par étape)│
    └─────────────┘                  └──────────────────┘

    ┌─────────────┐                  ┌──────────────────┐
    │ Un seul     │ ──── évolue ──→  │ Chaîne de        │
    │ prompt      │                  │ prompts          │
    │             │                  │ (séquentiel)     │
    └─────────────┘                  └──────────────────┘
```

---

## Technique 1 : Few-Shot Prompting

**Principe :** Fournir 2-3 exemples du résultat attendu avant de faire la demande.

### Quand l'utiliser ?
- Quand vous voulez un format très spécifique
- Quand le ton ou le style doit suivre un modèle précis
- Quand le zero-shot donne des résultats incohérents

### Exemple concret — Classification d'emails :

```
Classe ces emails selon leur urgence (haute, moyenne, basse) :

Exemple 1 : "Le serveur est en panne, impossible de travailler" → Haute
Exemple 2 : "Pouvez-vous mettre à jour la liste de diffusion ?" → Basse
Exemple 3 : "Le client Durand menace de résilier son contrat demain" → Haute

Maintenant, classe cet email :
"Nous aimerions organiser un team building le mois prochain"
```

### Formule :
```
Voici [N] exemples de [tâche] :

Exemple 1 : [entrée] → [sortie attendue]
Exemple 2 : [entrée] → [sortie attendue]
Exemple 3 : [entrée] → [sortie attendue]

Maintenant, fais la même chose pour : [nouvelle entrée]
```

---

## Technique 2 : Chain-of-Thought (CoT)

**Principe :** Demander à l'IA de raisonner étape par étape avant de donner sa réponse finale.

### Quand l'utiliser ?
- Analyse de données ou de situations complexes
- Prise de décision multi-critères
- Résolution de problèmes
- Quand vous voulez comprendre le raisonnement de l'IA

### Exemple concret — Analyse commerciale :

**Sans CoT :**
> "Notre CA a baissé de 15% ce trimestre. Que faire ?"
> → Réponse superficielle avec des recommandations génériques

**Avec CoT :**
> "Notre CA a baissé de 15% ce trimestre alors que le marché a progressé de 3%. Analyse cette situation étape par étape :
> 1. Quelles sont les causes possibles (internes et externes) ?
> 2. Quels sont les indicateurs à vérifier en priorité ?
> 3. Quelles actions correctives proposerais-tu ?
> Raisonne de manière structurée avant de donner tes recommandations finales."

### Formules à utiliser :
- "Raisonne étape par étape avant de répondre"
- "Analyse ce problème point par point"
- "Explique ton raisonnement avant de conclure"
- "Décompose cette question en sous-questions"

---

## Technique 3 : Prompting Négatif

**Principe :** Dire ce que l'on NE veut PAS dans la réponse.

### Quand l'utiliser ?
- Quand l'IA a tendance à ajouter des éléments indésirables
- Pour affiner le ton (pas trop formel, pas trop familier)
- Pour exclure certains sujets ou concurrents

### Exemples de contraintes négatives :

| Besoin | Formulation |
|--------|------------|
| Pas de blabla | "Ne commence pas par 'Bien sûr !' ou 'Absolument !'" |
| Pas de jargon | "Évite tout jargon technique, écris pour un non-spécialiste" |
| Pas de concurrents | "Ne mentionne pas les entreprises X, Y et Z" |
| Pas trop long | "Ne dépasse pas 150 mots, même si le sujet est complexe" |
| Pas de listes | "Rédige en paragraphes fluides, pas de listes à puces" |
| Pas d'intro générique | "Commence directement par le contenu, pas de phrase d'introduction" |

---

## Technique 4 : Structuration des Outputs

**Principe :** Demander un format de sortie précis et structuré.

### Formats courants :

**Tableau :**
> "Présente ta réponse sous forme de tableau avec les colonnes : Critère | Avantages | Inconvénients | Note /5"

**Sections numérotées :**
> "Structure ta réponse en 4 sections : 1) Contexte, 2) Analyse, 3) Recommandations, 4) Prochaines étapes"

**Format email :**
> "Présente sous forme d'email prêt à envoyer avec Objet, Corps du message et Signature"

**Format fiche :**
> "Présente sous forme de fiche recto-verso : recto = synthèse, verso = détails"

---

## Technique 5 : Chaînes de Prompts

**Principe :** Décomposer une tâche complexe en plusieurs prompts séquentiels.

### Méthodologie en 4 étapes :

```
┌───────────────┐     ┌───────────────┐     ┌───────────────┐     ┌───────────────┐
│   PROMPT 1    │     │   PROMPT 2    │     │   PROMPT 3    │     │   PROMPT 4    │
│               │     │               │     │               │     │               │
│  Analyser /   │────→│  Structurer / │────→│   Rédiger /   │────→│  Vérifier /   │
│  Comprendre   │     │  Organiser    │     │   Produire    │     │  Affiner      │
│               │     │               │     │               │     │               │
│  Sortie :     │     │  Sortie :     │     │  Sortie :     │     │  Sortie :     │
│  Liste/Analyse│     │  Plan/Struct. │     │  Brouillon    │     │  Version      │
│               │     │               │     │               │     │  finale       │
└───────────────┘     └───────────────┘     └───────────────┘     └───────────────┘
```

### Quand l'utiliser ?
- Tâches complexes nécessitant plus de 300 mots de sortie
- Quand vous avez besoin de contrôler chaque étape
- Quand un seul prompt donne des résultats médiocres
- Production de documents complets (rapports, propositions, plans)

### Avantages :
- Meilleure qualité à chaque étape
- Possibilité de corriger le tir en cours de route
- Résultat final plus cohérent et complet

---

## Tableau récapitulatif : quelle technique pour quel besoin ?

| Besoin | Technique recommandée |
|--------|----------------------|
| L'IA ne comprend pas le format que je veux | **Few-shot** (donner des exemples) |
| J'ai besoin d'une analyse approfondie | **Chain-of-thought** (raisonnement étape par étape) |
| L'IA ajoute des éléments indésirables | **Prompting négatif** (dire ce qu'on ne veut pas) |
| Je veux un format de sortie précis | **Structuration** (spécifier le format) |
| La tâche est trop complexe pour 1 prompt | **Chaîne de prompts** (décomposer en étapes) |
| Je veux le meilleur résultat possible | **Combiner** toutes les techniques ! |

---

## Astuce finale : combiner les techniques

Le prompt le plus efficace combine souvent plusieurs techniques :

```
[CREA de base]
+ [Few-shot : 1-2 exemples]
+ [Chain-of-thought : "raisonne étape par étape"]
+ [Prompting négatif : "ne fais pas X"]
+ [Structuration : "format tableau avec colonnes X, Y, Z"]
```

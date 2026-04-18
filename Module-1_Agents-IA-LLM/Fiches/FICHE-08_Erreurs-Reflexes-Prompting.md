# FICHE-08 — Les 5 Erreurs et 5 Réflexes du Prompting

> **Formation IA pour les Métiers du Tertiaire**
> Fiche de référence recto-verso (1 page)

---

## ❌ LES 5 ERREURS DU DÉBUTANT

### Erreur 1 : Le prompt trop vague

| ❌ Mauvais prompt | ✅ Bon prompt |
|-------------------|--------------|
| "Fais-moi un email" | "Rédige un email de 100 mots, ton professionnel, pour informer nos clients du changement d'horaires d'ouverture à partir du 1er mars" |

**Pourquoi c'est un problème :** L'IA n'a pas de contexte et produit un résultat générique inutilisable.

---

### Erreur 2 : Pas de contexte

| ❌ Mauvais prompt | ✅ Bon prompt |
|-------------------|--------------|
| "Écris un post LinkedIn" | "Je suis responsable marketing dans une PME agroalimentaire B2B. Écris un post LinkedIn de 150 mots pour annoncer le lancement de notre nouvelle gamme bio destinée aux restaurateurs" |

**Pourquoi c'est un problème :** Sans savoir qui vous êtes, votre secteur, votre cible, l'IA ne peut pas produire un contenu pertinent.

---

### Erreur 3 : Attendre la perfection au premier essai

| ❌ Mauvaise pratique | ✅ Bonne pratique |
|---------------------|------------------|
| Envoyer 1 prompt, être déçu, abandonner | Envoyer 1 prompt, analyser la réponse, affiner en 2-3 échanges |

**Pourquoi c'est un problème :** Un bon résultat se construit en 2-3 itérations. La première réponse est un brouillon, pas un produit fini.

**Prompts d'itération utiles :**
- "C'est trop long, réduis à 150 mots"
- "Le ton est trop familier, passe en mode corporate"
- "Ajoute des chiffres concrets"
- "Propose 3 variantes"

---

### Erreur 4 : Saisir des données sensibles

| ❌ Dangereux | ✅ Sécurisé |
|-------------|------------|
| "Voici la fiche de paie de Jean Dupont, né le 15/03/1985, n° sécu 1 85 03 75..." | "Voici un exemple anonymisé de fiche de paie. Aide-moi à créer un modèle d'explication des lignes de paie" |

**Ce qu'il ne faut JAMAIS saisir :**
- Données personnelles nominatives (nom + données sensibles)
- Numéros de sécurité sociale, RIB, numéros de carte
- Résultats financiers non publiés
- Secrets commerciaux, brevets en cours
- Mots de passe, identifiants

---

### Erreur 5 : Accepter la réponse sans vérifier

| ❌ Dangereux | ✅ Prudent |
|-------------|----------|
| Copier-coller la réponse telle quelle dans un document officiel | Relire, vérifier les faits et chiffres, adapter au contexte, puis valider |

**Les LLM peuvent :**
- Inventer des chiffres qui semblent plausibles
- Citer des études ou articles qui n'existent pas
- Donner des informations juridiques obsolètes
- Présenter des opinions comme des faits

**Règle d'or :** Plus l'enjeu est important, plus la vérification doit être rigoureuse.

---

## ✅ LES 5 RÉFLEXES À ADOPTER

### Réflexe 1 : Donner du contexte

Avant chaque prompt, répondez mentalement à :
- **Qui suis-je ?** (poste, entreprise, secteur)
- **Quelle est la situation ?** (lancement, problème, routine)
- **Pour qui ?** (destinataire, public cible)

> **Formule :** "Je suis [poste] dans [entreprise/secteur]. [Situation]. Le destinataire est [public]."

---

### Réflexe 2 : Être spécifique

Précisez toujours :
- Le **format** souhaité (email, tableau, liste, rapport...)
- La **longueur** (nombre de mots, de points, de pages)
- Le **ton** (formel, conversationnel, expert, pédagogique)
- Les **contraintes** (ce qu'il faut inclure ou exclure)

> **Formule :** "Format [X], [Y] mots, ton [Z]. Inclus [A]. N'inclus pas [B]."

---

### Réflexe 3 : Itérer

Ne vous arrêtez jamais à la première réponse. Affinez :

```
Prompt initial → Réponse brute
     ↓
"Réduis à 200 mots" → Version courte
     ↓
"Ajoute un appel à l'action" → Version enrichie
     ↓
"Propose 2 variantes du titre" → Options finales
     ↓
✅ Résultat utilisable
```

---

### Réflexe 4 : Vérifier les faits

**Checklist de vérification :**
- [ ] Les chiffres cités sont-ils plausibles ?
- [ ] Les dates mentionnées sont-elles correctes ?
- [ ] Les sources citées existent-elles vraiment ?
- [ ] Les informations juridiques sont-elles à jour ?
- [ ] Le contenu est-il cohérent avec ce que je sais du sujet ?

**Si c'est pour un usage officiel** (document client, publication, rapport) : faites toujours relire par un expert humain du domaine.

---

### Réflexe 5 : Sauvegarder ses prompts efficaces

Créez un document "Mes Prompts" avec vos meilleures formulations :

| Tâche | Mon prompt optimisé | LLM recommandé |
|-------|-------------------|----------------|
| Offre d'emploi | [prompt sauvegardé] | Claude |
| Post LinkedIn | [prompt sauvegardé] | ChatGPT |
| Synthèse de rapport | [prompt sauvegardé] | Claude |
| Email de prospection | [prompt sauvegardé] | ChatGPT |

**Avantage :** Vous ne repartez jamais de zéro. Chaque nouveau prompt est une amélioration du précédent.

---

## En résumé

```
╔═══════════════════════════════════════════════╗
║                                               ║
║  ❌ ÉVITEZ                  ✅ ADOPTEZ        ║
║                                               ║
║  Prompts vagues    →    Contexte riche        ║
║  Pas de contexte   →    Méthode CREA          ║
║  1 seul essai      →    2-3 itérations        ║
║  Données sensibles →    Données anonymisées   ║
║  Copier sans lire  →    Toujours vérifier     ║
║                                               ║
╚═══════════════════════════════════════════════╝
```

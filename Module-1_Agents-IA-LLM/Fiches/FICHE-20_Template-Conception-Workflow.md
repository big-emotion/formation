# FICHE-20 — Template de Conception de Workflow sur Papier

> **Formation IA pour les Métiers du Tertiaire**
> Fiche d'exercice — Session 5 (1 page)

---

## Informations

**Nom :** _________________________________ **Métier :** _____________
**Date :** _________________________________ **Outil prévu :** ________

---

## 1. Le problème à résoudre

**Quelle tâche répétitive souhaitez-vous automatiser ?**

___________________________________________________________________

**Combien de temps cette tâche vous prend actuellement (par semaine) ?**

_______ heures/semaine

**Combien de fois par semaine/mois réalisez-vous cette tâche ?**

_______ fois par _____________

---

## 2. Le déclencheur (Trigger)

**Qu'est-ce qui lance cette tâche ?**

☐ Réception d'un email
☐ Nouveau fichier dans un dossier
☐ Nouvelle ligne dans un tableur
☐ Soumission d'un formulaire
☐ Heure/jour fixe (planifié)
☐ Autre : _________________________________

**Application source :** _________________________________

---

## 3. Les étapes du workflow

Dessinez ou décrivez chaque étape :

```
┌─────────────────┐
│  DÉCLENCHEUR     │
│                  │
│ ________________ │
│ ________________ │
└────────┬─────────┘
         │
         ▼
┌─────────────────┐
│  ÉTAPE 1         │
│                  │
│ ________________ │
│ App: __________ │
└────────┬─────────┘
         │
         ▼
┌─────────────────┐     ┌─────────────────┐
│  CONDITION ?     │     │                  │
│                  │──→  │  SI NON :        │
│ ________________ │     │  ________________│
└────────┬─────────┘     └──────────────────┘
         │ SI OUI
         ▼
┌─────────────────┐
│  ÉTAPE 2 (IA)    │
│                  │
│ Prompt :         │
│ ________________ │
│ ________________ │
│ App: __________ │
└────────┬─────────┘
         │
         ▼
┌─────────────────┐
│  ÉTAPE 3         │
│                  │
│ ________________ │
│ App: __________ │
└────────┬─────────┘
         │
         ▼
┌─────────────────┐
│  RÉSULTAT FINAL  │
│                  │
│ ________________ │
│ ________________ │
└──────────────────┘
```

---

## 4. L'étape IA

**Quel LLM utiliserez-vous ?** ☐ ChatGPT (API) ☐ Claude (API) ☐ Autre

**Quel est le prompt que l'IA exécutera ?**

___________________________________________________________________

___________________________________________________________________

___________________________________________________________________

**Quel résultat l'IA doit-elle produire ?**

___________________________________________________________________

---

## 5. Applications connectées

| Étape | Application | Ce qu'elle fait |
|-------|------------|----------------|
| Déclencheur | | |
| Étape 1 | | |
| Étape 2 (IA) | | |
| Étape 3 | | |
| Résultat | | |

---

## 6. Résultat attendu

**Quel est le livrable final de ce workflow ?**

___________________________________________________________________

**Temps estimé gagné par semaine :** _______ heures

**Ce workflow nécessite-t-il une validation humaine avant la sortie ?**

☐ Oui, systématiquement ☐ Oui, par échantillonnage ☐ Non, entièrement automatisé

---

## Validation par le formateur

☐ Le problème est bien identifié et pertinent
☐ Le déclencheur est réaliste et disponible
☐ L'étape IA est bien définie (prompt clair)
☐ Le workflow est réalisable en 1h30 d'atelier
☐ Les applications nécessaires sont accessibles

**Commentaire du formateur :**

___________________________________________________________________

# Workflow de contribution — Formation IA Tertiaire

> Langue du contenu pédagogique : **français**.
> Langue des commits, PRs et issues : **français**.

---

## Source de vérité

Le **[tableau maître Notion](https://www.notion.so/346a0481e72d81ed8030ef9fee52a965)** pilote les statuts de validation.
GitHub est l'outil de **review** (diff, commentaires inline, approvals) — pas l'outil de pilotage.

Après chaque merge, l'auteur de la PR met à jour le statut de la fiche dans Notion.

---

## Principe

Chaque fiche ou deck est validé via une Pull Request relue par au moins 2 co-fondateurs.
Le merge sur `main` = fiche validée v1.0.

---

## Workflow

### 1. Prendre une issue

Une issue existe pour chaque fiche/deck. Avant de commencer :

- S'assigner l'issue correspondante sur GitHub
- Passer son statut à `En cours` dans le tableau maître Notion

### 2. Créer une branche

```bash
git checkout -b revue/fiche-09
# ou pour une nouvelle fiche
git checkout -b nouveau/fiche-54
```

Une branche = une fiche (ou un petit groupe cohérent de 3 fiches liées maximum).

### 3. Ouvrir la PR

- Titre : `FICHE-NN — Titre court de la modification`
- Le template est chargé automatiquement → remplir la checklist auteur
- Lier l'issue via `Closes #NN`
- Ajouter le label : `module-1`, `module-2`, `evaluations`, `admin` ou `marketing`

### 4. Review

- **2 approvals requis** (dont 1 obligatoire via CODEOWNERS)
- L'auteur ne peut pas approuver sa propre PR
- Les relecteurs cochent la checklist des 5 critères dans le template
- Si *changes requested* → l'auteur pousse les corrections et relance la review

### 5. Merge

- Squash merge (un commit propre par fiche dans l'historique de `main`)
- La branche est supprimée automatiquement
- **L'auteur met à jour le statut dans le tableau maître Notion**

---

## Règle d'arbitrage

Si désaccord après 2 allers-retours → point hebdo du vendredi (1h), décision tranchée par **@PLACEHOLDER-JN**.
Le commentaire de merge mentionne l'arbitrage. La colonne "Décision tranchée" du tableau Notion est remplie.

---

## Décisions de périmètre

Toute discussion *"faut-il inclure X dans v1.0 ?"* se fait dans Notion, pas dans les PRs.
Les PRs traitent du **contenu**, pas du scope.

---

## Cas particuliers

### Fichiers .pptx

Git ne produit pas de diff lisible sur les binaires. Pour relire un deck :

1. Télécharger le `.pptx` depuis la PR (ou via LFS local)
2. Relire localement
3. Commenter sur la PR en citant le numéro de slide (ex : *"Slide 7 : incohérent avec FICHE-12"*)

### Captures d'écran d'outils IA

Stocker dans `Module-X/assets/` et référencer en chemin relatif. Git LFS gère le versioning.

---

## Backlog v1.1

Toute idée hors scope v1.0 → ouvrir une issue avec le template **Backlog v1.1** (label `v1.1-backlog`).
Pas de PR spéculative, pas de modification sans issue liée.

---

## Branch protection (rappel)

`main` est protégée :

- 2 approvals requis
- CODEOWNERS review requise
- Pas de push direct, pas de force push
- Branches à jour avec `main` avant merge

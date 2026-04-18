# FICHE-22 — Cas d'Usage RH — Prompts Modèles

> **Formation IA pour les Métiers du Tertiaire**
> Fiche de référence — Session 6 (3 pages)

---

## Cartographie des cas d'usage IA en RH

| Domaine | Cas d'usage | Outil recommandé | Difficulté |
|---------|------------|-------------------|------------|
| **Recrutement** | Rédaction d'offres d'emploi | ChatGPT / Claude | Débutant |
| | Screening et analyse de CV | Claude (longs docs) | Intermédiaire |
| | Préparation d'entretiens (questions STAR) | ChatGPT / Claude | Débutant |
| | Réponses aux candidats (acceptation/refus) | ChatGPT | Débutant |
| **Administration** | Rédaction de notes de service | ChatGPT / Claude | Débutant |
| | Réponses FAQ salariés | GPT personnalisé | Intermédiaire |
| | Génération de courriers (attestations, etc.) | ChatGPT | Débutant |
| **Formation** | Création de parcours de formation | Claude | Intermédiaire |
| | Rédaction de fiches pédagogiques | ChatGPT / Claude | Intermédiaire |
| | Évaluation et feedback 360 | ChatGPT | Intermédiaire |
| **QVT / Marque employeur** | Rédaction de posts marque employeur | ChatGPT | Débutant |
| | Analyse d'enquêtes de satisfaction | ChatGPT (Code Interpreter) | Avancé |
| | Plan d'intégration (onboarding) | Claude | Intermédiaire |

---

## Prompts détaillés pour les ateliers

### Atelier RH-1 : Fiche de poste → Offre d'emploi

**Étape 1 — Structurer la fiche de poste :**
```
[C] Je suis DRH dans une ESN de 120 salariés (Paris, convention Syntec).
Mon manager data me dit : "J'ai besoin d'un data analyst senior,
Python + SQL, capable de présenter au CODIR, budget 55-65K€."

[R] Tu es un consultant senior en recrutement tech, spécialisé ESN.

[E] Format fiche de poste structurée : intitulé, rattachement hiérarchique,
contexte du recrutement, missions principales (6-8 puces), compétences
techniques requises, compétences comportementales (soft skills),
formation/expérience, rémunération et avantages. En français, ton RH pro.

[A] Transforme ce brief informel en une fiche de poste structurée et
complète, prête à être validée par le manager.
```

**Étape 2 — Transformer en offre attractive :**
```
À partir de cette fiche de poste, rédige une offre d'emploi de 400-500 mots,
ton attractif et moderne, destinée à LinkedIn et Indeed.

Mets en avant :
- La culture d'entreprise (environnement agile, projets variés)
- Les avantages (télétravail 3j/semaine, 12 RTT, tickets restaurant 10€)
- Les perspectives d'évolution

Structure : accroche, l'entreprise (50 mots), les missions, le profil, ce
qu'on offre, process de recrutement.

Ne commence PAS par "Nous recherchons" — trouve un hook plus engageant.
```

---

### Atelier RH-2 : Screening de CV

**Prompt pour l'analyse comparative :**
```
[C] Je recrute un Chargé de Communication Digitale pour notre PME
industrielle (80 salariés, B2B). Voici la fiche de poste : [résumé des
critères clés : 3 ans d'expérience min, maîtrise réseaux sociaux B2B,
création de contenu, reporting, anglais courant].

[R] Tu es un recruteur expert utilisant une approche structurée
d'évaluation des candidatures.

[E] Pour chaque CV, évalue sur 5 critères : adéquation expérience (/5),
compétences techniques (/5), formation (/5), soft skills décelables (/5),
adéquation culturelle (/5). Format tableau comparatif. Sois objectif et
factuel — base-toi uniquement sur ce qui est écrit dans le CV.

[A] Analyse les 5 CV ci-dessous et classe-les par pertinence pour ce poste.
Pour chaque candidat, donne une note globale /25 et une recommandation :
"Entretien", "À approfondir" ou "Ne correspond pas". Explicite ton
raisonnement pour chaque note.

[Coller les 5 CV]
```

**Prompt de suivi — vérification des biais :**
```
Relis ton analyse et vérifie :
1. As-tu pénalisé un candidat pour des raisons non liées aux compétences
   (âge, genre, origine, type d'école) ?
2. Tes critères sont-ils appliqués de manière identique à chaque CV ?
3. Y a-t-il des biais potentiels dans ton évaluation ?
Corrige si nécessaire et fournis l'analyse révisée.
```

---

### Atelier RH-3 : Questions d'entretien STAR

**Prompt :**
```
[C] Je vais interviewer des candidats pour le poste de Chargé de
Communication Digitale (PME industrielle B2B, 80 salariés). Les
compétences clés à évaluer sont : gestion de projet, créativité,
autonomie, communication, résistance au stress.

[R] Tu es un expert en entretiens structurés et en évaluation
comportementale (méthode STAR : Situation, Tâche, Action, Résultat).

[E] Format tableau avec colonnes : Compétence évaluée | Question STAR
complète | Ce qu'on cherche dans une bonne réponse | Signal d'alerte
(mauvaise réponse). Génère 2 questions par compétence = 10 questions total.

[A] Crée une grille d'entretien structurée. Les questions doivent
commencer par "Racontez-moi une situation où..." ou "Donnez-moi un
exemple concret de..." pour pousser le candidat à donner des réponses
factuelles et non théoriques.
```

---

## Précautions spécifiques RH

| Risque | Précaution |
|--------|-----------|
| **Biais de recrutement** | Ne jamais utiliser l'IA comme seul critère de sélection. Toujours vérifier les évaluations. Demander à l'IA de vérifier ses propres biais. |
| **RGPD / Données personnelles** | Ne jamais saisir de vrais noms + données sensibles. Anonymiser les CV avant upload. |
| **Non-discrimination** | Vérifier que les offres d'emploi ne contiennent pas de critères discriminants. L'IA peut reproduire des biais de genre ou d'âge. |
| **Droit du travail** | L'IA ne remplace pas un juriste. Toujours faire valider les textes juridiques (règlement intérieur, sanctions, licenciement). |
| **Confidentialité** | Ne pas uploader de dossiers disciplinaires, données médicales, ou informations salariales nominatives. |

# FICHE-15 — 5 Exemples de Chaînes de Prompts par Métier

> **Formation IA pour les Métiers du Tertiaire**
> Fiche de référence — Session 4 (4 pages)

---

## 1. RH — Chaîne "Processus de recrutement complet"

**Objectif :** Passer d'un besoin de recrutement à un kit complet (offre + grille d'entretien + scorecard)

```
Prompt 1 → Prompt 2 → Prompt 3 → Prompt 4
Fiche de    Offre       Questions    Scorecard
poste       d'emploi    d'entretien  d'évaluation
```

### Prompt 1 — Fiche de poste structurée
> **[C]** Je suis DRH dans une ESN de 150 salariés. Mon manager du pôle data me dit "J'ai besoin d'un data analyst senior, quelqu'un qui sait faire du Python et du SQL, qui peut présenter des résultats au CODIR, budget 55-65K€."
>
> **[R]** Tu es un consultant en recrutement spécialisé en profils tech/data.
>
> **[E]** Format fiche de poste structurée : intitulé, rattachement, missions principales (6-8), compétences techniques requises, compétences comportementales, expérience, rémunération.
>
> **[A]** Transforme ce brief informel en une fiche de poste structurée et complète.

### Prompt 2 — Offre d'emploi attractive
> À partir de la fiche de poste ci-dessus, rédige une offre d'emploi de 400 mots, ton attractif et moderne, destinée à être publiée sur LinkedIn. Mets en avant la culture d'entreprise (environnement agile, projets variés, formation continue) et les avantages (télétravail 3j/semaine, RTT, tickets restaurant).

### Prompt 3 — Grille de questions d'entretien
> À partir de cette fiche de poste, génère 12 questions d'entretien structurées : 4 questions techniques (Python, SQL, data viz), 4 questions comportementales (méthode STAR : Situation, Tâche, Action, Résultat), 4 questions de motivation/fit culturel. Pour chaque question, indique ce qu'on cherche dans la réponse.

### Prompt 4 — Scorecard de comparaison
> Crée une scorecard d'évaluation pour comparer les candidats. Format tableau avec : 10 critères évalués (issus de la fiche de poste), note de 1 à 5 pour chaque critère, pondération (certains critères comptent plus que d'autres), formule de score final. La scorecard doit pouvoir accueillir 5 candidats côte à côte.

---

## 2. Marketing — Chaîne "Lancement produit multicanal"

**Objectif :** Créer un kit de lancement complet (message clé → contenu LinkedIn → article blog → newsletter)

```
Prompt 1 → Prompt 2 → Prompt 3 → Prompt 4
Message     Post        Article     Newsletter
clé +       LinkedIn    blog        + objets
angles                              A/B
```

### Prompt 1 — Stratégie de message
> **[C]** Je suis responsable marketing chez TechSolutions, éditeur SaaS B2B (80 salariés). Nous lançons "SmartBoard", un outil de tableau de bord automatisé pour les DAF de PME. Prix : 199€/mois. Avantage principal : les rapports qui prenaient 2 jours se font en 2 heures.
>
> **[R]** Tu es un stratège en marketing produit B2B SaaS.
>
> **[A]** Propose 5 angles de communication différents pour ce lancement, avec pour chacun : l'angle, le message clé en 1 phrase, le persona cible, le canal idéal.

### Prompt 2 — Post LinkedIn
> En utilisant l'angle n°[X] ci-dessus, rédige un post LinkedIn de 150-200 mots. Ton : expert mais accessible. Inclus un hook accrocheur en première ligne, une anecdote ou un chiffre marquant, et un appel à l'action (lien vers démo). Ajoute 3 hashtags pertinents.

### Prompt 3 — Article blog
> En développant le même angle, rédige un article de blog de 600 mots pour notre site. Structure : titre accrocheur (H1), introduction avec le pain point des DAF (100 mots), le problème détaillé (150 mots), notre solution SmartBoard (200 mots), un cas d'usage concret (100 mots), conclusion + CTA (50 mots). Inclus des sous-titres H2 et H3. Ton expert et pédagogique.

### Prompt 4 — Newsletter de lancement
> À partir de l'article ci-dessus, crée une newsletter de 300 mots. Propose 5 objets d'email (< 50 caractères, optimisés pour le taux d'ouverture), un pré-header (< 90 caractères), et le corps du mail avec : accroche, résumé de la valeur ajoutée, 1 témoignage client fictif, CTA "Réserver ma démo".

---

## 3. Finance — Chaîne "Rapport de gestion mensuel"

**Objectif :** Transformer des données brutes en un rapport de gestion prêt pour le CODIR

```
Prompt 1 → Prompt 2 → Prompt 3 → Prompt 4
Analyse     Commentaire  Alertes     Email de
des         de gestion   et plan     synthèse
données                  d'action    CODIR
```

### Prompt 1 — Analyse des données
> **[C]** Je suis contrôleur de gestion dans une PME industrielle (200 salariés). Voici nos chiffres du mois de janvier :
> - CA réalisé : 1,2M€ (budget : 1,4M€, N-1 : 1,3M€)
> - Marge brute : 42% (budget : 45%, N-1 : 44%)
> - Charges de personnel : 520K€ (budget : 500K€)
> - Charges externes : 180K€ (budget : 150K€)
>
> **[R]** Tu es un analyste financier senior dans l'industrie.
>
> **[A]** Analyse ces chiffres étape par étape : calcule les écarts budget/réalisé et N/N-1 en valeur et en %, identifie les 3 alertes principales, et classe-les par ordre de gravité.

### Prompt 2 — Commentaire de gestion
> À partir de ton analyse, rédige un commentaire de gestion de 300 mots pour le reporting mensuel. Structure : synthèse en 3 phrases, analyse des écarts significatifs (>5%), facteurs explicatifs probables, perspectives pour le mois suivant. Ton factuel, pas alarmiste.

### Prompt 3 — Plan d'action
> Pour chaque alerte identifiée, propose un plan d'action concret. Format tableau : Alerte / Cause probable / Action corrective / Responsable suggéré / Délai / Indicateur de suivi / Impact attendu.

### Prompt 4 — Email de synthèse pour le CODIR
> Rédige un email de synthèse de 150 mots adressé au Directeur Général et aux membres du CODIR. L'email doit résumer les 3 points clés du mois, les 2 actions prioritaires, et proposer 1 sujet à inscrire à l'ordre du jour du prochain CODIR. Ton professionnel, synthétique, orienté décision.

---

## 4. Commercial — Chaîne "Prospection ciblée"

**Objectif :** Préparer une campagne de prospection complète (ICP → emails → relances → objections)

```
Prompt 1 → Prompt 2 → Prompt 3 → Prompt 4
ICP et      Cold email  Séquence   Traitement
personas    initial     de relance  objections
```

### Prompt 1 — Profil client idéal (ICP)
> **[C]** Je vends une solution de SIRH (système d'information RH) en SaaS, 99€/mois par utilisateur. Nos clients actuels sont surtout des PME de 50 à 200 salariés dans le tertiaire. Notre force : la simplicité et le déploiement en 48h.
>
> **[R]** Tu es un consultant en stratégie commerciale B2B SaaS.
>
> **[A]** Définis notre ICP (Ideal Customer Profile) : taille entreprise, secteur, interlocuteur décisionnaire, budget type, pain points principaux, signaux d'achat. Crée aussi 2 personas détaillés (DRH PME et DAF PME).

### Prompt 2 — Cold email initial
> En ciblant le persona DRH de PME, rédige un cold email de 80 mots. Commence par un pain point spécifique (pas une question générique), mentionne un bénéfice chiffré, et termine par un CTA soft (pas "Achetez maintenant" mais "15 min pour vous montrer comment ?"). Propose 5 objets d'email < 50 caractères.

### Prompt 3 — Séquence de 3 relances
> Le prospect n'a pas répondu au premier email. Rédige 3 emails de relance :
> - J+3 : nouvel angle de valeur ajoutée (60 mots)
> - J+7 : preuve sociale / cas client similaire (70 mots)
> - J+14 : "break-up email" bienveillant (50 mots)
> Chaque email avec un objet unique. Le ton progresse de "valeur" à "urgence douce" à "dernier contact".

### Prompt 4 — Guide de traitement des objections
> À partir de l'ICP et des personas, identifie les 7 objections les plus fréquentes que nous risquons d'entendre. Pour chaque objection, propose une réponse de 2-3 phrases suivant la méthode : Accueillir → Reformuler → Répondre → Relancer. Format tableau.

---

## 5. Gestion — Chaîne "Organisation de séminaire"

**Objectif :** Planifier un séminaire d'entreprise de A à Z

```
Prompt 1 → Prompt 2 → Prompt 3 → Prompt 4
Programme   Checklist   Email         Budget
détaillé    logistique  invitation    prévisionnel
```

### Prompt 1 — Programme
> **[C]** Je suis assistante de direction dans une entreprise de services (100 salariés). Je dois organiser le séminaire annuel de 2 jours (vendredi-samedi) pour 80 personnes. Thème : "Innovation et collaboration". Budget total : 15 000€. Lieu : à 1h de Paris.
>
> **[R]** Tu es un organisateur d'événements corporate expérimenté.
>
> **[A]** Crée un programme détaillé pour les 2 jours : horaires, activités (alterner sérieux et ludique), intervenants suggérés, format des ateliers. Inclus les pauses et repas.

### Prompt 2 — Checklist logistique
> À partir de ce programme, crée une checklist logistique exhaustive en format tableau : Tâche / Responsable / Deadline (J-30 à J) / Statut / Budget alloué. Couvre : lieu, transport, hébergement, restauration, matériel technique, goodies, communication interne, assurances.

### Prompt 3 — Email d'invitation
> Rédige un email d'invitation à envoyer aux 100 collaborateurs. Ton enthousiaste mais professionnel, 200 mots. Inclus : les dates, le lieu, le thème, les 3 temps forts, les informations pratiques, un lien fictif vers un formulaire d'inscription (allergies, transport). Propose 3 objets d'email engageants.

### Prompt 4 — Budget prévisionnel
> Crée un budget prévisionnel détaillé pour cet événement dans la limite de 15 000€. Format tableau : Poste de dépense / Description / Coût unitaire / Quantité / Total / % du budget. Postes à couvrir : lieu, restauration (2 déjeuners + 1 dîner + pauses), hébergement (1 nuit), transport (bus), matériel, animation, imprévus (10%). Propose 2 scénarios : économique et confortable.

---

## Conseils pour construire vos propres chaînes

1. **Commencez par le livrable final** : qu'est-ce que vous voulez obtenir ?
2. **Remontez les étapes** : de quoi ai-je besoin à l'étape précédente ?
3. **3-5 prompts suffisent** généralement — au-delà, c'est trop complexe
4. **Vérifiez à chaque étape** : la sortie est-elle correcte avant de passer au prompt suivant ?
5. **Sauvegardez vos chaînes** qui fonctionnent bien — elles sont réutilisables !

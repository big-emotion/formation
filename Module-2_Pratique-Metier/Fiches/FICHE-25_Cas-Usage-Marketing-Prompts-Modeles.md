# FICHE-25 — Cas d'Usage Marketing : Prompts Modèles

> **Formation IA pour les Métiers du Tertiaire**
> Module 2 — Pratique Métier | Session 6 — Ateliers RH & Marketing
> Ateliers Marketing : MKT-1, MKT-2, MKT-3

---

## 1. Cartographie des cas d'usage Marketing avec l'IA

Le tableau ci-dessous recense les tâches marketing courantes, le temps estimé sans et avec assistance IA, et le gain de productivité attendu.

| # | Tâche Marketing | Temps sans IA | Temps avec IA | Gain estimé | Niveau de maîtrise IA requis |
|---|---|---|---|---|---|
| 1 | Rédaction d'un article de blog SEO (800 mots) | 3 h | 45 min | ~75 % | Intermédiaire |
| 2 | Création d'un post LinkedIn engageant | 45 min | 10 min | ~78 % | Débutant |
| 3 | Conception d'une newsletter complète | 2 h 30 | 40 min | ~73 % | Intermédiaire |
| 4 | Analyse concurrentielle (3 concurrents) | 1 journée | 2 h | ~75 % | Avancé |
| 5 | Création d'un buyer persona B2B détaillé | 3 h | 30 min | ~83 % | Intermédiaire |
| 6 | Rédaction de 10 objets d'email A/B | 1 h | 10 min | ~83 % | Débutant |
| 7 | Brief créatif pour campagne | 2 h | 30 min | ~75 % | Intermédiaire |
| 8 | Matrice SWOT commentée | 2 h | 30 min | ~75 % | Intermédiaire |
| 9 | Adaptation multicanal d'un contenu unique | 2 h | 25 min | ~79 % | Intermédiaire |
| 10 | Veille sectorielle synthétisée | 2 h/semaine | 30 min/semaine | ~75 % | Avancé |

> **Point clé** : L'IA est un accélérateur de production, pas un remplacement du jugement marketing. Le temps gagné doit être réinvesti dans la stratégie, la relecture critique et la relation client.

---

## 2. Les 3 ateliers marketing — Prompts CREA

### Rappel : la méthode CREA

| Lettre | Signification | Description |
|---|---|---|
| **C** | Contexte | Qui êtes-vous ? Quel est l'environnement métier ? |
| **R** | Rôle | Quel rôle l'IA doit-elle jouer ? |
| **E** | Exécution | Que doit-elle produire ? Format, longueur, structure ? |
| **A** | Ajustement | Contraintes, ton, limites, critères de qualité ? |

---

## Atelier MKT-1 — Chaîne de contenu multicanal

### Contexte de l'exercice

Vous êtes Chargé(e) de Communication Digitale chez AgroTech Solutions. Vous devez créer une chaîne de contenus cohérente pour le lancement de la gamme de sauces bio "Terroir Pro" destinée aux professionnels de la restauration.

**Livrables attendus :**
1. Un post LinkedIn (150-200 mots)
2. Un article de blog SEO (800 mots)
3. Une newsletter
4. 2 variantes A/B d'objet d'email pour la newsletter

> Consultez la **FICHE-26** (Brief Lancement Produit) pour les détails complets du produit et de la stratégie.

---

### Prompt CREA — Étape 1 : Post LinkedIn

```
CONTEXTE :
Je suis Chargé(e) de Communication Digitale chez AgroTech Solutions, PME
agroalimentaire B2B basée à Lyon (80 salariés). Nous lançons "Terroir Pro",
une nouvelle gamme de 6 sauces bio (tomate-basilic, poivron-espelette,
champignons forestiers, curry-coco, provençale, moutarde à l'ancienne)
destinée aux professionnels de la restauration (chefs de cuisine en
collectivité, traiteurs, restauration rapide premium).
Certifications : Bio AB, origine France, sans conservateurs.
Positionnement : premium, +15-20 % vs gamme standard, justifié par la
qualité des ingrédients et les certifications.

RÔLE :
Tu es un expert en communication B2B LinkedIn spécialisé dans le secteur
agroalimentaire.

EXÉCUTION :
Rédige un post LinkedIn de 150 à 200 mots pour annoncer le lancement de
la gamme Terroir Pro. Le post doit :
- Commencer par une accroche forte (question ou statistique)
- Présenter les bénéfices clés pour les professionnels (gain de temps,
  qualité, certifications)
- Inclure un appel à l'action (demande d'échantillon gratuit)
- Proposer 3 à 5 hashtags pertinents
- Utiliser des sauts de ligne pour la lisibilité mobile

AJUSTEMENT :
- Ton : professionnel mais accessible, pas corporate froid
- Pas de superlatifs excessifs ("révolutionnaire", "incroyable")
- Pas de claims santé (réglementation)
- Mentionner les certifications Bio AB et origine France
- Valoriser le terroir et le savoir-faire français
- Ne pas mentionner le prix
```

---

### Prompt CREA — Étape 2 : Article de blog SEO

```
CONTEXTE :
Je suis Chargé(e) de Communication Digitale chez AgroTech Solutions, PME
agroalimentaire B2B basée à Lyon. Notre blog s'adresse aux professionnels
de la restauration et de l'agroalimentaire. Nous lançons "Terroir Pro",
gamme de 6 sauces bio pour la restauration professionnelle.
Mot-clé principal ciblé : "sauces bio professionnelles restauration"
Mots-clés secondaires : "fournisseur sauces bio CHR", "sauces certifiées
restauration collective", "gamme bio professionnels cuisine"

RÔLE :
Tu es un rédacteur web SEO spécialisé dans le contenu B2B agroalimentaire.

EXÉCUTION :
Rédige un article de blog de 800 mots structuré ainsi :
1. Titre H1 optimisé SEO (intégrant le mot-clé principal)
2. Introduction (100 mots) — contextualiser la tendance bio en restauration
   professionnelle
3. H2 : Pourquoi le bio s'impose en restauration professionnelle (200 mots)
   — chiffres de marché, attentes des convives, réglementation EGalim
4. H2 : Terroir Pro — une gamme pensée pour les professionnels (250 mots)
   — présentation des 6 références, certifications, avantages pratiques
   (format, conservation, praticité en cuisine)
5. H2 : Comment intégrer les sauces bio dans votre carte (150 mots)
   — conseils pratiques, exemples de plats
6. Conclusion + CTA (100 mots) — demande d'échantillon

AJUSTEMENT :
- Ton expert mais accessible, pas de jargon marketing
- Intégrer naturellement les mots-clés (pas de keyword stuffing)
- Proposer une méta-description de 155 caractères maximum
- Suggérer 3 liens internes possibles (thématiques, pas d'URL)
- Pas de claims santé, mentionner les certifications factuellement
- Inclure au moins 2 données chiffrées (marché bio en RHD)
- Format : paragraphes courts, listes à puces quand pertinent
```

---

### Prompt CREA — Étape 3 : Newsletter

```
CONTEXTE :
Je suis Chargé(e) de Communication Digitale chez AgroTech Solutions. Notre
newsletter mensuelle est envoyée à 2 000 contacts professionnels (chefs de
cuisine, responsables achats, directeurs de restauration collective,
traiteurs). Taux d'ouverture habituel : 22 %. Outil : Mailchimp.

RÔLE :
Tu es un expert en email marketing B2B spécialisé dans le secteur food
professionnel.

EXÉCUTION :
Conçois une newsletter pour annoncer le lancement de Terroir Pro. Structure :
1. Pré-header (texte d'aperçu, max 80 caractères)
2. Section héro : titre accrocheur + paragraphe d'introduction (50 mots)
3. Section produit : présentation de la gamme avec les 6 références
   (format liste, 2-3 lignes par sauce maximum)
4. Section bénéfices : 3 bénéfices clés illustrés (certifications,
   praticité, goût terroir)
5. Témoignage fictif : citation courte d'un chef qui a testé la gamme
6. CTA principal : "Demandez votre kit de dégustation gratuit"
7. CTA secondaire : lien vers l'article de blog
8. Footer : réseaux sociaux, lien de désinscription

AJUSTEMENT :
- Longueur totale : 400 mots maximum (newsletter, pas article)
- Ton : chaleureux et professionnel, donner envie de goûter
- Indiquer entre crochets [IMAGE : description] les visuels à insérer
- Pas de claims santé
- Penser au rendu mobile (phrases courtes, CTA clairs)
- Mentionner le salon SIRHA si pertinent (contexte saisonnier)
```

---

### Prompt CREA — Étape 4 : Variantes A/B d'objet d'email

```
CONTEXTE :
Newsletter de lancement de la gamme Terroir Pro (sauces bio pour
professionnels de la restauration) envoyée à 2 000 contacts B2B
(restauration collective, traiteurs, CHR).
Historique : les objets qui fonctionnent le mieux pour notre audience
contiennent des chiffres, des questions, ou mentionnent un avantage
concret. Taux d'ouverture cible : > 25 %.

RÔLE :
Tu es un spécialiste de l'email marketing B2B et de l'optimisation des
taux d'ouverture.

EXÉCUTION :
Propose 2 variantes d'objet d'email pour un test A/B :
- Variante A : approche "bénéfice concret" (axée sur la praticité ou la
  qualité)
- Variante B : approche "curiosité / question" (qui pousse à ouvrir)

Pour chaque variante, fournis :
1. L'objet (max 50 caractères, émoji optionnel)
2. Le pré-header associé (max 80 caractères)
3. Une justification de 2 lignes expliquant le mécanisme psychologique
   utilisé

AJUSTEMENT :
- Éviter les mots spam (gratuit, offre exceptionnelle, urgent)
- Rester professionnel (B2B, pas B2C)
- Tester des longueurs différentes entre A et B
- Prendre en compte l'affichage tronqué sur mobile (< 35 caractères visibles)
```

---

### Points de vigilance — MKT-1

| Risque | Ce qu'il faut vérifier |
|---|---|
| Incohérence entre canaux | Le message clé, le positionnement et le CTA sont-ils alignés sur les 4 contenus ? |
| Ton inadapté | LinkedIn est plus formel que la newsletter : l'IA a-t-elle adapté le registre ? |
| Claims santé | Aucune allégation santé ne doit figurer dans les contenus (réglementation EU) |
| SEO artificiel | L'article de blog intègre-t-il les mots-clés naturellement ? Pas de keyword stuffing ? |
| Généricité | Les contenus sont-ils spécifiques au secteur agroalimentaire B2B ou trop génériques ? |
| Données inventées | L'IA a-t-elle inventé des chiffres ? Vérifier toute statistique citée |

### Critères de validation — MKT-1

- [ ] Cohérence du message clé sur les 4 contenus
- [ ] Ton adapté à chaque canal (LinkedIn, blog, email)
- [ ] Aucune allégation santé
- [ ] Certifications correctement mentionnées (Bio AB, origine France)
- [ ] CTA clair et actionnable sur chaque contenu
- [ ] Article de blog structuré avec H1/H2 et mots-clés intégrés
- [ ] Newsletter < 400 mots avec indications visuelles
- [ ] Objets email < 50 caractères, sans mots spam
- [ ] Contenu spécifique au secteur (pas générique)

---

## Atelier MKT-2 — Analyse concurrentielle + Matrice SWOT

### Contexte de l'exercice

AgroTech Solutions souhaite positionner sa gamme Terroir Pro sur le marché des solutions alimentaires bio pour la restauration professionnelle. Vous devez analyser 3 concurrents fictifs et construire une matrice SWOT.

**Les 3 concurrents fictifs :**

| Concurrent | Description | Forces apparentes |
|---|---|---|
| **BioChef France** | ETI (300 salariés), gamme bio complète pour la restauration, implantation nationale, présent depuis 10 ans | Notoriété, gamme large, force commerciale |
| **Les Ateliers du Goût** | PME artisanale (40 salariés), sauces premium locales, circuit court, Auvergne-Rhône-Alpes | Authenticité, circuit court, prix premium assumé |
| **NutriPro Solutions** | Start-up (20 salariés), sauces bio et fonctionnelles (faible teneur en sel, enrichies), approche santé/nutrition | Innovation, positionnement santé, levée de fonds récente |

---

### Prompt CREA — Analyse concurrentielle

```
CONTEXTE :
Je suis responsable marketing chez AgroTech Solutions, PME agroalimentaire
B2B basée à Lyon (80 salariés). Nous lançons "Terroir Pro", gamme de
6 sauces bio pour les professionnels de la restauration.
Notre marché : sauces et condiments bio pour la restauration professionnelle
en France.
Notre cible : chefs de cuisine en restauration collective, traiteurs,
restauration rapide premium.

Voici les 3 concurrents à analyser :

1. BioChef France — ETI de 300 salariés, gamme bio complète pour la
   restauration, implantation nationale, 10 ans d'existence. Gamme de
   30+ références. CA estimé : 25 M€. Présent dans toutes les centrales
   d'achat.

2. Les Ateliers du Goût — PME artisanale de 40 salariés en Auvergne,
   sauces premium locales en circuit court. 12 références. CA estimé :
   3 M€. Forte identité terroir, prix élevés.

3. NutriPro Solutions — Start-up de 20 salariés, sauces bio et
   fonctionnelles (faible sel, enrichies en protéines). 8 références.
   Levée de fonds de 2 M€. Positionnement santé et innovation.

AgroTech Solutions : 80 salariés, 6 références Terroir Pro, CA gamme
sauces estimé 1,5 M€ (première année). Forces : certifications Bio AB
et origine France, connaissance du réseau CHR, relation de proximité
avec les clients.

RÔLE :
Tu es un consultant en stratégie marketing spécialisé dans l'agroalimentaire
B2B.

EXÉCUTION :
Produis une analyse structurée en 3 parties :

1. TABLEAU COMPARATIF (colonnes : critère / AgroTech / BioChef / Ateliers
   du Goût / NutriPro)
   Critères : taille, gamme, positionnement prix, certifications, canaux
   de distribution, force commerciale, présence digitale, innovation,
   notoriété.

2. MATRICE SWOT D'AGROTECH SOLUTIONS (format tableau 2x2)
   - Forces (internes, positives)
   - Faiblesses (internes, négatives)
   - Opportunités (externes, positives)
   - Menaces (externes, négatives)
   Minimum 4 éléments par quadrant, classés par importance.

3. RECOMMANDATIONS STRATÉGIQUES (5 recommandations concrètes et
   actionnables pour se différencier)

AJUSTEMENT :
- Rester réaliste par rapport à la taille PME d'AgroTech (pas de
  recommandations nécessitant des budgets de grand groupe)
- Chaque recommandation doit être liée à un élément de la SWOT
- Identifier clairement le principal avantage concurrentiel d'AgroTech
- Ne pas inventer de données de marché non plausibles
- Format structuré avec tableaux Markdown
```

---

### Points de vigilance — MKT-2

| Risque | Ce qu'il faut vérifier |
|---|---|
| Données fictives présentées comme réelles | L'IA peut inventer des parts de marché ou des CA : tout chiffre doit être identifié comme estimation |
| SWOT déséquilibrée | L'IA a tendance à sous-estimer les faiblesses et menaces : vérifier l'honnêteté de l'analyse |
| Recommandations irréalistes | Les recommandations sont-elles adaptées au budget et aux ressources d'une PME de 80 salariés ? |
| Manque de spécificité sectorielle | L'analyse est-elle ancrée dans le secteur agroalimentaire B2B ou trop générique ? |
| Biais de confirmation | L'IA peut être trop positive envers AgroTech : challenger les conclusions |

### Critères de validation — MKT-2

- [ ] Tableau comparatif complet avec les 4 acteurs
- [ ] SWOT équilibrée (au moins 4 éléments par quadrant)
- [ ] Forces et faiblesses clairement différenciées des opportunités et menaces
- [ ] Recommandations concrètes et actionnables pour une PME
- [ ] Chaque recommandation liée à un élément de la SWOT
- [ ] Données clairement identifiées comme estimations/fictives
- [ ] Avantage concurrentiel principal identifié
- [ ] Analyse spécifique au marché agroalimentaire B2B

---

## Atelier MKT-3 — Création de Buyer Personas B2B

### Contexte de l'exercice

Pour affiner sa stratégie de contenu et son discours commercial, AgroTech Solutions a besoin de 2 buyer personas détaillés représentant ses cibles prioritaires.

**Les 2 personas à créer :**
1. **Persona 1** : Directeur/Directrice Qualité dans une entreprise IAA (industrie agroalimentaire) de taille intermédiaire
2. **Persona 2** : Chef cuisinier d'une collectivité (restauration scolaire, hospitalière ou d'entreprise)

> Utilisez le **template de la FICHE-27** pour structurer vos personas.

---

### Prompt CREA — Persona 1 : Directeur Qualité IAA

```
CONTEXTE :
Je suis responsable marketing chez AgroTech Solutions, PME agroalimentaire
B2B basée à Lyon. Nous vendons des sauces et condiments bio certifiés
(Bio AB, origine France, sans conservateurs) aux professionnels de la
restauration et de l'agroalimentaire.
Je dois créer un buyer persona détaillé pour notre cible "Directeur
Qualité" dans l'industrie agroalimentaire.

RÔLE :
Tu es un expert en marketing B2B et en création de personas, avec une
connaissance approfondie du secteur agroalimentaire français.

EXÉCUTION :
Crée un buyer persona complet selon la structure suivante :
1. Avatar : description physique et vestimentaire en 2 lignes
2. Identité : nom fictif, âge (40-55 ans), poste exact, type d'entreprise,
   taille (150-500 salariés), localisation
3. Parcours : formation (ingénieur agro ou équivalent), expérience (15+ ans)
4. Responsabilités quotidiennes : 5 à 7 tâches concrètes
5. Objectifs professionnels : 3 objectifs prioritaires
6. Frustrations / pain points : 5 frustrations liées à son quotidien et
   à ses fournisseurs
7. Critères de décision d'achat : 5 critères classés par ordre de priorité
   quand il choisit un fournisseur d'ingrédients
8. Sources d'information : où il s'informe (presse, salons, réseaux,
   associations professionnelles)
9. Objections typiques : 3-4 objections qu'il formulerait face à un
   nouveau fournisseur de sauces bio
10. Citation représentative : une phrase qu'il pourrait dire en réunion
11. Canaux de contact préférés : par ordre de préférence

AJUSTEMENT :
- Le persona doit être réaliste et ancré dans le quotidien du secteur IAA
  français
- Les frustrations doivent refléter des problèmes réels (traçabilité,
  audits, réglementation, fiabilité fournisseurs)
- Les critères d'achat doivent refléter la logique d'un acheteur B2B
  industriel (pas d'un consommateur final)
- Inclure des détails spécifiques au secteur (normes IFS/BRC, cahiers des
  charges, audits)
- Le persona doit être actionnable : en le lisant, un commercial doit
  savoir comment adapter son discours
```

---

### Prompt CREA — Persona 2 : Chef cuisinier collectivité

```
CONTEXTE :
Je suis responsable marketing chez AgroTech Solutions, PME agroalimentaire
B2B basée à Lyon. Nous vendons des sauces et condiments bio certifiés
(Bio AB, origine France, sans conservateurs) aux professionnels de la
restauration et de l'agroalimentaire.
Je dois créer un buyer persona détaillé pour notre cible "Chef cuisinier
en restauration collective".

RÔLE :
Tu es un expert en marketing B2B et en création de personas, avec une
connaissance approfondie du secteur de la restauration collective en France.

EXÉCUTION :
Crée un buyer persona complet selon la même structure :
1. Avatar : description physique et vestimentaire en 2 lignes
2. Identité : nom fictif, âge (35-50 ans), poste exact, type de
   collectivité (scolaire, hospitalière ou entreprise), nombre de
   couverts/jour, localisation
3. Parcours : formation (CAP/BEP cuisine ou BTS hôtellerie-restauration),
   expérience (10+ ans, dont passage en restauration traditionnelle)
4. Responsabilités quotidiennes : 5 à 7 tâches concrètes
5. Objectifs professionnels : 3 objectifs prioritaires
6. Frustrations / pain points : 5 frustrations liées à son quotidien et
   à ses fournisseurs
7. Critères de décision d'achat : 5 critères classés par ordre de priorité
   quand il choisit un nouveau fournisseur d'ingrédients
8. Sources d'information : où il s'informe (salons, pairs, réseaux,
   groupements d'achats)
9. Objections typiques : 3-4 objections qu'il formulerait face à un
   fournisseur de sauces bio premium
10. Citation représentative : une phrase qu'il pourrait dire à un
    commercial
11. Canaux de contact préférés : par ordre de préférence

AJUSTEMENT :
- Le persona doit refléter la réalité de la restauration collective
  française (contraintes budget, loi EGalim, volumes)
- Les frustrations doivent être concrètes (budget serré, pression sur
  le bio obligatoire, manque de temps, turnover en cuisine)
- Le rapport au digital est différent du Directeur Qualité : ce persona
  est moins connecté, plus terrain
- Les critères d'achat intègrent le rapport qualité-prix et la praticité
  (formats, DLC, facilité de stockage)
- Le persona doit être actionnable pour adapter le discours commercial
```

---

### Points de vigilance — MKT-3

| Risque | Ce qu'il faut vérifier |
|---|---|
| Persona trop stéréotypé | L'IA a-t-elle produit un persona nuancé ou un cliché ? Les détails sont-ils crédibles ? |
| Manque de spécificité sectorielle | Les frustrations et critères d'achat sont-ils bien ancrés dans le secteur agroalimentaire/restauration ? |
| Persona non actionnable | En lisant le persona, un commercial saurait-il comment adapter son approche ? |
| Biais de genre | L'IA attribue-t-elle systématiquement un genre ? A-t-on interrogé ce choix ? |
| Déconnexion terrain | Les responsabilités quotidiennes sont-elles réalistes ou trop théoriques ? |

### Critères de validation — MKT-3

- [ ] Persona complet (toutes les sections remplies)
- [ ] Informations réalistes et cohérentes avec le secteur
- [ ] Frustrations concrètes et spécifiques (pas génériques)
- [ ] Critères d'achat ordonnés par priorité
- [ ] Objections crédibles face à un nouveau fournisseur
- [ ] Citation représentative authentique
- [ ] Persona actionnable pour l'équipe commerciale
- [ ] Différences claires entre les 2 personas (pas de copier-coller)
- [ ] Conformité avec le template FICHE-27

---

## 3. Synthèse — Conseils transversaux pour les 3 ateliers

### Ce que l'IA fait bien en marketing

- Structurer un contenu selon un plan donné
- Adapter un message à différents canaux à partir d'un brief unique
- Générer rapidement des variantes et des alternatives
- Proposer une première version de persona basée sur des archétypes sectoriels
- Identifier des angles de différenciation dans une analyse concurrentielle

### Ce que l'IA fait moins bien

- Inventer des données de marché fiables (toujours vérifier)
- Capturer la voix authentique d'une marque (nécessite itérations)
- Évaluer la faisabilité opérationnelle des recommandations
- Comprendre les subtilités relationnelles du B2B (confiance, réseau, long cycle de vente)
- Produire un contenu véritablement original et différenciant sans brief précis

### Checklist qualité pour tout contenu marketing généré par IA

- [ ] Les faits et chiffres sont-ils vérifiés ou clairement identifiés comme estimations ?
- [ ] Le ton est-il cohérent avec l'identité de marque ?
- [ ] Le contenu apporte-t-il une valeur réelle au lecteur cible ?
- [ ] Les CTA sont-ils clairs, uniques et actionnables ?
- [ ] Le contenu respecte-t-il la réglementation (claims santé, RGPD, etc.) ?
- [ ] Un expert métier a-t-il relu et validé le contenu ?
- [ ] Le contenu est-il suffisamment spécifique pour se différencier de la concurrence ?

---

*FICHE-25 — Formation IA pour les Métiers du Tertiaire — Module 2 — Session 6*

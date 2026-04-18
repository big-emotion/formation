# FICHE-31 : Cas d'Usage Commercial -- Prompts Modeles

**Formation IA pour les Metiers du Tertiaire**
Fiche d'exercice -- Atelier Commercial, Session 7

> Entreprise fil rouge : **AgroTech Solutions**, PME agroalimentaire B2B, 80 salaries, Lyon.
> Specialisee dans les solutions de tracabilite et les produits alimentaires pour professionnels.

---

## 1. Cartographie des cas d'usage commerciaux avec l'IA

| Tache | Temps sans IA | Temps avec IA | Gain estime |
|---|---|---|---|
| Creation d'une sequence emailing B2B (ICP + 4 emails + objets A/B) | 4 h | 1 h | ~75 % |
| Preparation de rendez-vous prospect (recherche + plan de decouverte) | 2 h | 30 min | ~75 % |
| Redaction d'une proposition commerciale personnalisee | 3 h | 1 h | ~65 % |
| Analyse d'un appel d'offres et redaction de reponse | 6 h | 2 h | ~65 % |
| Creation de supports de presentation (plan + contenu des slides) | 3 h | 45 min | ~75 % |
| Script de qualification telephonique | 1 h 30 | 20 min | ~80 % |
| Analyse concurrentielle (synthese de sources publiques) | 4 h | 1 h | ~75 % |
| Redaction d'etude de cas client (case study) | 3 h | 45 min | ~75 % |

> **Rappel** : L'IA produit des drafts qui doivent etre personnalises, verifies et adaptes. Un email commercial envoye tel quel par l'IA est moins performant qu'un email retravaille par le commercial.

---

## 2. Atelier COM-1 : Sequence emailing B2B complete

**Duree** : 25 minutes
**Objectif** : Creer une sequence de prospection complete (ICP + cold email + 3 relances + objets A/B) pour le segment restauration collective.
**Prerequis** : FICHE-32 (scenario de campagne)

### 2.1 Prompt CREA complet

```
[CONTEXTE]
Tu travailles pour AgroTech Solutions, PME agroalimentaire B2B basee a Lyon
(80 salaries). L'entreprise lance une campagne de prospection email pour
developper le segment restauration collective.

Informations cles :
- Offre : gamme "Terroir Pro" = sauces bio artisanales + solutions de
  tracabilite integrees (QR code sur chaque lot)
- Cibles : directeurs/responsables achats dans la restauration collective
  (hopitaux, cantines scolaires, EHPAD, restaurants d'entreprise)
- Arguments : certifications bio (AB + Eurofeuille), origine France
  100 %, tracabilite complete de la fourche a l'assiette, gain de temps
  en cuisine (produits prets a l'emploi), conformite reglementaire
  (nouvelle norme etiquetage)
- Preuve sociale : 15 clients existants en restauration collective,
  NPS de 8.2/10
- Budget : email uniquement (pas de pub payante)
- Objectif : 30 RDV qualifies en 2 mois

[ROLE]
Tu es un expert en growth marketing B2B avec 8 ans d'experience dans
l'agroalimentaire. Tu maitrises les techniques de cold emailing ethique
et tu connais les contraintes d'achat de la restauration collective
(marches publics, budgets contraints, exigences qualite).

[EXECUTION]
Produis les elements suivants dans l'ordre :

1. **ICP (Ideal Customer Profile)** detaille :
   - Titre de poste et niveau hierarchique
   - Taille d'entreprise / type de structure
   - Enjeux et douleurs principaux (top 5)
   - Criteres de decision d'achat
   - Objections previsibles (top 3)

2. **Email 1 -- Premier contact (cold email)** :
   - 2 variantes d'objet A/B (< 50 caracteres chacune)
   - Corps : max 120 mots, structure AIDA
   - CTA : proposition de RDV de 20 min
   - Signature avec preuve sociale

3. **Email 2 -- Relance J+3** :
   - 2 variantes d'objet A/B
   - Corps : max 80 mots, apporter une valeur ajoutee (chiffre cle
     ou etude de cas)
   - CTA souple

4. **Email 3 -- Relance J+7** :
   - 2 variantes d'objet A/B
   - Corps : max 80 mots, angle different (actualite reglementaire)
   - CTA avec proposition de contenu (guide, webinaire)

5. **Email 4 -- Derniere relance J+14** :
   - 2 variantes d'objet A/B
   - Corps : max 60 mots, message de cloture bienveillant
   - CTA : laisser la porte ouverte

[ATTENDU]
- Ton : professionnel mais humain, pas de jargon marketing excessif
- Chaque email doit pouvoir fonctionner de maniere independante
  (le prospect n'a peut-etre pas lu les precedents)
- Les objets doivent susciter la curiosite sans etre clickbait
- Inclure des variables de personnalisation : {prenom}, {entreprise},
  {nombre_de_sites}
- Format : Markdown structure avec titres H3 pour chaque email
```

### 2.2 Points de vigilance

| Point | Detail |
|---|---|
| RGPD | Tout emailing B2B doit respecter le RGPD et la directive ePrivacy. Verifier que la base de contacts est conforme (opt-in ou interet legitime B2B). |
| Personnalisation | Les emails generiques ont un taux d'ouverture 3x inferieur. Toujours personnaliser au-dela des simples variables {prenom}. |
| Spam | Eviter les mots declencheurs de spam : "gratuit", "urgent", "offre exceptionnelle". L'IA les utilise parfois. |
| Frequence | Respecter un rythme raisonnable (pas plus de 4 emails sur 3 semaines). |
| Ton | Relire chaque email a voix haute. S'il sonne "robot", le retoucher. |
| Legalite | Inclure un lien de desinscription dans chaque email. |

### 2.3 Criteres de validation du livrable

- [ ] L'ICP est detaille et coherent avec le segment restauration collective
- [ ] Les enjeux et douleurs identifies sont realistes
- [ ] Chaque email respecte la limite de mots indiquee
- [ ] Chaque email a 2 variantes d'objet A/B (< 50 caracteres)
- [ ] Le cold email suit la structure AIDA
- [ ] Les relances apportent chacune un angle different
- [ ] Les variables de personnalisation sont presentes
- [ ] Le ton est professionnel mais humain
- [ ] Aucun mot declencheur de spam n'est utilise
- [ ] Le dernier email est un message de cloture bienveillant

---

## 3. Atelier COM-2 : Fiche de preparation de rendez-vous prospect

**Duree** : 25 minutes
**Objectif** : Produire une fiche de preparation de RDV complete pour un prospect identifie, avec recherche, questions, objections et proposition de valeur.
**Prerequis** : FICHE-32 (scenario de campagne)

### 3.1 Prompt CREA complet

```
[CONTEXTE]
Tu prepares un rendez-vous commercial pour AgroTech Solutions (PME
agroalimentaire B2B, 80 salaries, Lyon).

Informations sur le prospect :
- Entreprise : Sodexo Restauration
- Activite : restauration collective (hopitaux, cantines, EHPAD, entreprises)
- Taille : 500 sites en France, CA restauration France ~1,2 Md EUR
- Contact : Marie Dupont, Directrice Achats Alimentaires
- Contexte : elle a ouvert notre Email 2 et clique sur le lien vers
  notre etude de cas. Pas encore repondu.
- Le RDV est un appel de decouverte de 30 minutes en visio.

Informations sur AgroTech Solutions :
- Offre : gamme "Terroir Pro" (sauces bio + tracabilite integree)
- 15 clients existants en restauration collective, NPS 8.2/10
- Reference client comparable : Groupe Restalliance (120 sites livres)
- Prix : 15-20 % plus cher que les sauces industrielles classiques
- Differentiation : bio, origine France, tracabilite, gain de temps cuisine
- Nouvelle reglementation etiquetage = levier commercial

[ROLE]
Tu es un coach commercial senior specialise dans la vente complexe B2B.
Tu prepares les commerciaux avant leurs rendez-vous strategiques.
Tu utilises la methode SPIN Selling (Situation, Probleme, Implication,
Need-payoff).

[EXECUTION]
Produis une fiche de preparation de RDV structuree :

1. **Recherche prospect** :
   - Synthese de l'entreprise (activite, taille, enjeux publics)
   - Profil du contact (role, responsabilites probables, motivations)
   - Actualites recentes pertinentes (tendances restauration collective)
   - Fournisseurs actuels probables et positionnement concurrentiel

2. **5 questions ouvertes SPIN** :
   - 1 question Situation (comprendre l'existant)
   - 2 questions Probleme (identifier les douleurs)
   - 1 question Implication (mesurer l'impact des problemes)
   - 1 question Need-payoff (projeter la solution)

3. **Anticipation d'objections** :
   - 4 objections probables avec reponse argumentee pour chacune
   - Pour chaque objection : formulation probable du prospect, reponse
     structuree (accuser reception, reformuler, repondre, verifier)

4. **Proposition de valeur adaptee** :
   - Pitch de 30 secondes adapte a Sodexo Restauration
   - 3 benefices cles chiffres
   - Preuve sociale pertinente (reference client similaire)

5. **Plan de decouverte structure** :
   - Deroulement minute par minute du RDV de 30 min
   - Objectif de chaque phase
   - Prochaine etape a proposer en fin de RDV

[ATTENDU]
- Document utilisable tel quel par un commercial avant son RDV
- Ton : direct, operationnel, pas de blabla theorique
- Chaque question doit avoir une justification strategique (pourquoi
  on la pose et ce qu'on cherche a decouvrir)
- Les reponses aux objections doivent etre naturelles, pas
  "scriptees" ou agressives
- Format : Markdown structure avec sections clairement separees
```

### 3.2 Points de vigilance

| Point | Detail |
|---|---|
| Informations publiques uniquement | La "recherche prospect" generee par l'IA repose sur des connaissances generales. Toujours croiser avec LinkedIn, le site web du prospect, et les actualites recentes. |
| Personnalisation du pitch | Le pitch genere est un point de depart. L'adapter en fonction des signaux specifiques du prospect (clics, pages visitees, echanges precedents). |
| Questions trop intrusives | Certaines questions generees peuvent etre trop directes pour un premier RDV. Adapter au niveau de relation. |
| Hallucinations | L'IA peut inventer des faits sur le prospect (CA, nombre de sites, fournisseurs). Toujours verifier les chiffres. |
| Mise a jour | Regenerer la fiche si le RDV est reporte : les actualites et le contexte peuvent avoir change. |

### 3.3 Criteres de validation du livrable

- [ ] La recherche prospect est structuree et plausible
- [ ] Les 5 questions suivent la methode SPIN (S-P-P-I-N)
- [ ] Chaque question a une justification strategique
- [ ] Au moins 4 objections sont anticipees avec reponses structurees
- [ ] Le pitch de 30 secondes est concis et adapte au prospect
- [ ] Les benefices sont chiffres (pas de generalites)
- [ ] Le plan de decouverte couvre les 30 minutes du RDV
- [ ] Une prochaine etape concrete est proposee
- [ ] Le document est directement utilisable par un commercial

---

## Ressources complementaires

- FICHE-32 : Scenario de campagne de prospection (contexte pour COM-1 et COM-2)
- Module 1 : Methode CREA pour la construction de prompts

---

*Formation IA pour les Metiers du Tertiaire -- Module 2 : Pratique Metier*
*Fiche d'exercice FICHE-31 -- Session 7*

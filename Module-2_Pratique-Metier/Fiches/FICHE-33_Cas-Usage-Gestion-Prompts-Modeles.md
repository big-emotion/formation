# FICHE-33 : Cas d'Usage Gestion -- Prompts Modeles

**Formation IA pour les Metiers du Tertiaire**
Fiche d'exercice -- Atelier Gestion, Session 7

> Entreprise fil rouge : **AgroTech Solutions**, PME agroalimentaire B2B, 80 salaries, Lyon.
> Specialisee dans les solutions de tracabilite et les produits alimentaires pour professionnels.

---

## 1. Cartographie des cas d'usage Gestion / Administratif avec l'IA

| Tache | Temps sans IA | Temps avec IA | Gain estime |
|---|---|---|---|
| Compte-rendu de reunion structure a partir de notes brutes | 1 h 30 | 20 min | ~80 % |
| Creation de templates de courriers administratifs | 2 h par template | 15 min par template | ~85 % |
| Redaction de procedures internes | 3 h | 45 min | ~75 % |
| Synthese de documents volumineux (rapports, audits) | 2 h | 30 min | ~75 % |
| Planification de projet (WBS, retroplanning) | 4 h | 1 h | ~75 % |
| Redaction de fiches de poste | 1 h 30 | 20 min | ~80 % |
| Traduction et adaptation de documents multilingues | 2 h / document | 30 min / document | ~75 % |
| Preparation d'ordre du jour structure | 30 min | 5 min | ~85 % |

> **Rappel** : L'IA excelle dans la structuration et la mise en forme. Le contenu metier (decisions, engagements, chiffres) doit toujours etre verifie par l'humain.

---

## 2. Atelier GEST-1 : Compte-rendu structure a partir de notes brutes

**Duree** : 25 minutes
**Objectif** : Transformer des notes de reunion desordonnees en compte-rendu professionnel structure.
**Prerequis** : FICHE-34 (notes de reunion brutes)

### 2.1 Prompt CREA complet

```
[CONTEXTE]
Tu travailles pour AgroTech Solutions, PME agroalimentaire B2B de 80 salaries
basee a Lyon. Un comite de direction a eu lieu et tu disposes de notes brutes
prises a la volee par un assistant.

Voici les notes brutes de la reunion :

<<< COLLER ICI LE CONTENU DE LA FICHE-34 >>>

Participants habituels du comite de direction AgroTech Solutions :
- Philippe Moreau -- Directeur General (DG)
- Sophie Laurent -- Directrice Administrative et Financiere (DAF)
- Marc Benoit -- Directeur Commercial (DC)
- Nadia Cherif -- Responsable R&D
- Thomas Girard -- Responsable Production
- Camille Rousseau -- Responsable RH
- Julien Fabre -- Responsable Marketing Digital

[ROLE]
Tu es un assistant de direction experimente avec 10 ans de pratique en PME.
Tu maitrises la redaction de comptes-rendus de comite de direction : tu sais
distinguer les decisions fermes des discussions ouvertes, identifier les
actions a mener, et structurer l'information de maniere claire et actionnable.

[EXECUTION]
1. Analyse les notes brutes en identifiant :
   - Les sujets abordes (meme s'ils sont melanges dans les notes)
   - Les decisions prises (distinguer decision ferme vs discussion ouverte)
   - Les actions a mener (avec responsable et delai si mentionne)
   - Les points en suspens ("a confirmer", "voir avec...")
   - Les informations factuelles (chiffres, dates, noms)

2. Restructure l'ensemble en un compte-rendu professionnel.

3. Signale les informations manquantes ou a verifier.

[ATTENDU]
Produis un compte-rendu de reunion avec la structure suivante :

**En-tete** :
- Titre : "Compte-rendu du Comite de Direction"
- Date, heure, lieu
- Participants presents (avec fonction)
- Excuses le cas echeant
- Redacteur

**Ordre du jour reconstitue** :
- Liste numerotee des sujets abordes

**Pour chaque sujet** :
- Titre du sujet
- Resume des echanges (3 a 5 lignes maximum)
- Decision(s) prise(s) (en gras, formulees clairement)
- Action(s) a mener : format tableau
  | Action | Responsable | Delai | Statut |

**Tableau recapitulatif des actions** :
- Toutes les actions consolidees dans un seul tableau en fin de CR
- Numerotees (A1, A2, A3...)

**Points en suspens** :
- Liste des sujets non tranches ou informations a confirmer

**Prochaine reunion** :
- Date et heure si mentionnee

Ton : factuel, precis, professionnel. Pas de commentaire personnel
ni d'interpretation. Si une information est ambigue dans les notes,
le signaler avec [A CONFIRMER].
```

### 2.2 Points de vigilance

| Point | Detail |
|---|---|
| Confidentialite | Les notes de reunion contiennent souvent des informations sensibles (RH, strategie, finances). Ne jamais les envoyer sur un LLM public en situation reelle. |
| Decisions vs discussions | L'IA peut confondre une piste evoquee avec une decision validee. Toujours faire relire le CR par le president de la reunion. |
| Noms et fonctions | Verifier que l'IA a correctement attribue les interventions aux bonnes personnes. |
| Informations manquantes | Si les notes sont lacunaires, l'IA peut "completer" avec des informations inventees. Verifier chaque fait. |
| Delais | Si un delai n'est pas mentionne dans les notes, l'IA peut en inventer un. Signaler avec [A CONFIRMER]. |

### 2.3 Criteres de validation du livrable

- [ ] L'en-tete est complet (date, participants, lieu)
- [ ] L'ordre du jour est reconstitue de maniere logique
- [ ] Chaque sujet a un resume, des decisions et des actions
- [ ] Les decisions sont clairement distinguees des discussions
- [ ] Le tableau des actions contient : action, responsable, delai, statut
- [ ] Les points en suspens sont identifies
- [ ] Le ton est factuel (pas d'interpretation)
- [ ] Les informations ambigues sont signalees [A CONFIRMER]
- [ ] Le CR est directement diffusable aux participants

---

## 3. Atelier GEST-2 : Templates de courriers administratifs + prompt reutilisable

**Duree** : 25 minutes
**Objectif** : Creer un systeme de templates de courriers professionnels reutilisables, avec un prompt generique adaptable.
**Pas de prerequis externe** : l'exercice est autonome.

### 3.1 Prompt CREA complet

```
[CONTEXTE]
Tu travailles pour AgroTech Solutions, PME agroalimentaire B2B de 80 salaries
basee a Lyon. L'entreprise a besoin de standardiser ses courriers administratifs
pour gagner en coherence et en rapidite. Actuellement, chaque collaborateur
redige ses courriers de zero, ce qui entraine des disparites de ton, des oublis
d'informations obligatoires et une perte de temps estimee a 5 heures par semaine
pour l'ensemble de l'equipe administrative.

Coordonnees de l'entreprise :
- AgroTech Solutions SAS
- 45 rue de la Republique, 69002 Lyon
- SIRET : 823 456 789 00015
- TVA : FR 82 823456789
- Tel : 04 72 XX XX XX
- Email : contact@agrotech-solutions.fr

[ROLE]
Tu es un expert en communication administrative et en gestion documentaire.
Tu concois des templates professionnels qui sont a la fois rigoureux sur
le plan juridique et chaleureux dans le ton (AgroTech cultive une image
de PME accessible et professionnelle).

[EXECUTION]
Cree 4 templates de courriers pour les situations suivantes :

**Template 1 : Reponse a une reclamation client**
- Contexte : un client professionnel se plaint d'un probleme
  (qualite produit, retard livraison, erreur de facturation)
- Le template doit etre adaptable a differents types de reclamations
- Variables : {nom_client}, {entreprise_client}, {ref_commande},
  {date_reclamation}, {nature_probleme}, {solution_proposee},
  {geste_commercial}, {nom_interlocuteur}

**Template 2 : Confirmation de commande**
- Contexte : confirmer la prise en compte d'une commande client
- Inclure : recapitulatif commande, delai de livraison, conditions
  de paiement, contact en cas de question
- Variables : {nom_client}, {entreprise_client}, {ref_commande},
  {date_commande}, {detail_commande}, {montant_HT}, {montant_TTC},
  {delai_livraison}, {conditions_paiement}

**Template 3 : Relance impaye**
- Contexte : facture impayee apres echeance (3 niveaux de relance)
- Niveau 1 (J+7) : rappel courtois
- Niveau 2 (J+21) : relance formelle
- Niveau 3 (J+45) : mise en demeure avant contentieux
- Variables : {nom_client}, {entreprise_client}, {ref_facture},
  {date_facture}, {montant_du}, {date_echeance}, {penalites}

**Template 4 : Demande de devis fournisseur**
- Contexte : solliciter un devis aupres d'un fournisseur potentiel
- Inclure : description du besoin, volumes estimes, delai souhaite,
  criteres de selection, format de reponse attendu
- Variables : {nom_fournisseur}, {entreprise_fournisseur},
  {description_besoin}, {volume_estime}, {delai_souhaite},
  {date_limite_reponse}

[ATTENDU]
Pour chaque template, produis :

1. **Le template complet** en Markdown avec les variables entre accolades
2. **Un exemple rempli** avec des donnees fictives coherentes
   (un vrai cas AgroTech Solutions)
3. **Un prompt reutilisable** : un meta-prompt que le collaborateur
   pourra copier-coller dans l'IA en remplacant les variables, pour
   generer le courrier final adapte a chaque situation

Structure du meta-prompt reutilisable :
"Genere un courrier de [TYPE] pour AgroTech Solutions a partir de
ces informations : [LISTE DES VARIABLES A REMPLIR]. Utilise un ton
[INDICATION DE TON]. Le courrier doit inclure [ELEMENTS OBLIGATOIRES]."

Format : Markdown propre avec separateurs entre chaque template.
Ton des courriers : professionnel, courtois, precis. Pour les relances
impayes, le ton se durcit progressivement du niveau 1 au niveau 3.
```

### 3.2 Points de vigilance

| Point | Detail |
|---|---|
| Mentions legales | Les courriers de relance impayee et de mise en demeure doivent contenir les mentions legales obligatoires (article L.441-10 du Code de commerce pour les penalites de retard). Verifier avec le service juridique. |
| Ton et image | Les templates definissent l'image de l'entreprise. Les faire valider par la direction avant diffusion. |
| RGPD | Les templates de reponse a reclamation ne doivent pas contenir de donnees personnelles inutiles. |
| Personnalisation | Un template trop generique est contre-productif. Prevoir des zones de personnalisation libre en plus des variables. |
| Mise a jour | Planifier une revue des templates tous les 6 mois (evolution legale, changement de coordonnees, evolution du ton de marque). |

### 3.3 Criteres de validation du livrable

- [ ] Les 4 templates sont complets et coherents
- [ ] Chaque template contient toutes les variables necessaires
- [ ] Un exemple rempli est fourni pour chaque template
- [ ] Un meta-prompt reutilisable est fourni pour chaque template
- [ ] Les relances impayes ont bien 3 niveaux progressifs
- [ ] Les mentions legales pertinentes sont presentes (relance impayee)
- [ ] Le ton est adapte a chaque situation (courtois pour la confirmation, ferme pour la mise en demeure)
- [ ] Les templates sont directement utilisables par l'equipe
- [ ] Les coordonnees d'AgroTech Solutions sont correctes

---

## 4. Prompt generique reutilisable -- Aide-memoire

Pour creer n'importe quel courrier administratif a l'avenir, l'apprenant peut utiliser ce meta-prompt :

```
Genere un courrier professionnel pour AgroTech Solutions SAS
(45 rue de la Republique, 69002 Lyon).

Type de courrier : [reponse reclamation / confirmation commande /
relance impaye / demande devis / autre : preciser]

Destinataire : [nom, fonction, entreprise, adresse]

Informations cles : [lister toutes les informations pertinentes]

Ton souhaite : [courtois / ferme / neutre]

Elements obligatoires a inclure : [references, mentions legales,
delais, etc.]

Format : courrier professionnel classique avec en-tete, objet,
corps structure, formule de politesse, signature.
```

> Ce meta-prompt est un outil de productivite quotidien. Le sauvegarder
> dans un document partage de l'equipe.

---

## Ressources complementaires

- FICHE-34 : Notes de reunion brutes (pour GEST-1)
- Module 1 : Methode CREA pour la construction de prompts

---

*Formation IA pour les Metiers du Tertiaire -- Module 2 : Pratique Metier*
*Fiche d'exercice FICHE-33 -- Session 7*

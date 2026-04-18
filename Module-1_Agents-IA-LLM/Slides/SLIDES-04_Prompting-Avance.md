# SLIDES-04 — Prompting Avance : Techniques et Chaines de Prompts

> **Session 4** — Jour 2, apres-midi (14h00-17h30)
> **Duree** : 3h30 | **Niveau** : Intermediaire
> **Prerequis** : Methode CREA maitrisee (Session 3)
> **Objectifs** : Maitriser le few-shot, le chain-of-thought, les chaines de prompts et la structuration des outputs

---

## BLOC 1 — TECHNIQUES AVANCEES DE PROMPTING (1h15)

---

### Slide 1 — Page de titre

# Prompting Avance
## Session 4 — Aller plus loin avec les LLM

Formation IA pour les Metiers du Tertiaire
Jour 2 — Apres-midi

---

### Slide 2 — Objectifs de la session

## Ce que vous saurez faire a la fin de cette session

1. **Utiliser** le few-shot prompting pour guider le LLM par l'exemple
2. **Activer** le raisonnement etape par etape (chain-of-thought)
3. **Structurer** les reponses dans le format exact dont vous avez besoin
4. **Enchainer** plusieurs prompts pour traiter des taches complexes
5. **Construire** une chaine de prompts complete pour votre metier

---

### Slide 3 — Rappel : ou en sommes-nous ?

## La session de ce matin : les bases solides

Vous maitrisez deja la methode **CREA** :

```
C — Contexte    : Poser le decor
R — Role        : Definir l'expertise attendue
E — Explicite   : Detailler les contraintes
A — Action      : Formuler la demande precise
```

**Cet apres-midi** : on ajoute des techniques puissantes PAR-DESSUS cette base.

CREA reste votre fondation. Les techniques avancees sont vos super-pouvoirs.

---

### Slide 4 — La carte des techniques

## Vue d'ensemble : votre boite a outils complete

```
+-------------------------------------------------------+
|               TECHNIQUES DE PROMPTING                  |
+-------------------------------------------------------+
|                                                       |
|  NIVEAU 1 (ce matin)        NIVEAU 2 (cet apres-midi)|
|  ~~~~~~~~~~~~~~~~~~~~        ~~~~~~~~~~~~~~~~~~~~~~~~~|
|  [x] Methode CREA            [ ] Zero-shot vs Few-shot|
|  [x] Prompts structures      [ ] Chain-of-thought     |
|  [x] Iteration               [ ] Prompting negatif    |
|                               [ ] Structuration output |
|                               [ ] Chaines de prompts   |
+-------------------------------------------------------+
```

---

### Slide 5 — Introduction : Zero-shot vs Few-shot

# Zero-shot vs Few-shot Prompting
## Guider le LLM par l'exemple

---

### Slide 6 — Zero-shot : la demande directe

## Zero-shot prompting : demander sans montrer

**Principe** : Vous formulez votre demande sans fournir d'exemple du resultat attendu.

C'est ce que vous faites naturellement depuis ce matin.

**Exemple :**
```
Classe ce commentaire client comme "positif", "negatif" ou "neutre" :

"La livraison a ete rapide mais le produit ne correspondait pas
a la description sur le site."
```

Le LLM doit deviner seul le format et le niveau de detail attendus.

---

### Slide 7 — Few-shot : montrer avant de demander

## Few-shot prompting : apprendre par l'exemple

**Principe** : Vous fournissez 2-3 exemples du resultat attendu AVANT de poser votre question.

**Exemple :**
```
Classe ces commentaires clients. Voici le format attendu :

Commentaire : "Produit excellent, je recommande !"
-> Sentiment : positif | Confiance : haute

Commentaire : "C'est correct, rien d'exceptionnel."
-> Sentiment : neutre | Confiance : moyenne

Commentaire : "Jamais recu ma commande, service client injoignable."
-> Sentiment : negatif | Confiance : haute

Maintenant, classe celui-ci :
Commentaire : "La livraison a ete rapide mais le produit ne
correspondait pas a la description sur le site."
```

---

### Slide 8 — Comparaison visuelle

## Zero-shot vs Few-shot : le meme objectif, deux approches

```
ZERO-SHOT                          FEW-SHOT
==========                         =========

+-------------+                    +-------------+
|  Consigne   |                    |  Exemple 1  |
+------+------+                    +-------------+
       |                           |  Exemple 2  |
       v                           +-------------+
+-------------+                    |  Consigne   |
|  Reponse    |                    +------+------+
|  (variable) |                           |
+-------------+                           v
                                   +-------------+
                                   |  Reponse    |
                                   | (calibree)  |
                                   +-------------+
```

**Zero-shot** : rapide, mais resultat imprevisible
**Few-shot** : plus long a ecrire, mais resultat precis et constant

---

### Slide 9 — Quand utiliser chaque approche ?

## Zero-shot vs Few-shot : guide de choix

| Situation | Zero-shot | Few-shot |
|-----------|-----------|----------|
| Tache simple et standard | Oui | Pas necessaire |
| Format de sortie tres precis | Risque | **Recommande** |
| Tache repetitive (meme format) | Risque | **Recommande** |
| Classification avec categories fixes | Possible | **Recommande** |
| Brainstorming, ideation libre | **Recommande** | Trop contraignant |
| Premiere exploration d'un sujet | **Recommande** | Pas necessaire |

**Regle simple** : si vous devez faire la meme tache plusieurs fois avec un format identique, investissez dans un prompt few-shot.

---

### Slide 10 — Few-shot par metier : exemples concrets

## Few-shot en action pour chaque metier

**RH — Classification de candidatures :**
```
Classe chaque CV selon : "A convoquer" / "A revoir" / "Non retenu"

CV : 5 ans exp. management, master RH, anglais courant
-> A convoquer | Motif : profil senior correspondant au poste

CV : Stage 6 mois, licence eco, pas d'anglais
-> Non retenu | Motif : experience insuffisante pour le niveau demande

CV : 3 ans exp. similaire, licence RH, anglais intermediaire
-> A revoir | Motif : profil interessant, verifier competences techniques

Maintenant, classe : [nouveau CV]
```

---

### Slide 11 — Few-shot par metier (suite)

## Few-shot en action (suite)

**Finance — Categorisation d'ecritures :**
```
Categorise chaque ecriture comptable :

Ecriture : "Facture EDF 1 247,50 EUR"
-> Categorie : Charges externes | Compte : 6061 | TVA : 20%

Ecriture : "Salaire janvier M. Dupont 3 200 EUR"
-> Categorie : Charges de personnel | Compte : 6411 | TVA : N/A

Ecriture : "Achat licence Salesforce 890 EUR/mois"
-> Categorie : Charges externes | Compte : 6156 | TVA : 20%

Maintenant : "Facture cabinet comptable Deloitte 15 000 EUR"
```

**Marketing — Ton de communication :**
```
Reecris chaque message dans un ton professionnel mais chaleureux :

Original : "Promo -30% sur tout !!!"
-> Reecrit : "Profitez de 30% de reduction sur l'ensemble de notre
   collection — une attention speciale pour nos clients fideles."

Original : "DERNIER JOUR pour en profiter !!!"
-> Reecrit : [a faire]
```

---

### Slide 12 — Exercice rapide : transformez en few-shot

## A vous ! (5 minutes)

**Consigne** : Transformez ce prompt zero-shot en prompt few-shot.

**Prompt zero-shot de depart :**
```
Redige un objet d'email professionnel pour relancer un client
qui n'a pas repondu a notre devis.
```

**Votre mission :**
1. Inventez 2-3 exemples d'objets d'email de relance
2. Montrez le format attendu (longueur, ton, structure)
3. Formulez ensuite la vraie demande

Reflechissez : quels exemples montrer pour calibrer le style ?

---

### Slide 13 — Correction de l'exercice

## Un prompt few-shot possible

```
Redige un objet d'email de relance professionnelle.
Voici le style attendu :

Situation : devis envoye il y a 5 jours, pas de reponse
-> Objet : "Suite a notre proposition — Avez-vous des questions ?"

Situation : devis envoye il y a 2 semaines, 2e relance
-> Objet : "Votre projet [X] — Faisons le point ensemble"

Situation : devis envoye il y a 1 mois, derniere relance
-> Objet : "Derniere opportunite : votre devis expire bientot"

Maintenant :
Situation : devis envoye il y a 10 jours, 1ere relance,
client = directeur achats grand compte
-> Objet :
```

Les exemples calibrent le **ton**, la **longueur** et la **structure**.

---

### Slide 14 — Transition vers le chain-of-thought

# Chain-of-Thought
## Faire raisonner le LLM etape par etape

---

### Slide 15 — Le probleme : les reponses hatives

## Pourquoi le LLM se trompe parfois ?

Sans instruction contraire, le LLM repond **immediatement** — comme un eleve qui leve la main sans reflechir.

**Exemple problematique :**
```
Un fournisseur propose 15% de remise sur une commande de
12 400 EUR HT, mais impose un minimum de commande de 15 000 EUR.
Nous avons aussi une offre concurrente a 11 200 EUR HT sans minimum.
Quelle est la meilleure option ?
```

**Reponse hative typique** : "L'offre avec 15% de remise est plus avantageuse."
(Erreur : 12 400 EUR ne depasse pas le minimum de 15 000 EUR !)

---

### Slide 16 — La solution : "Raisonne etape par etape"

## Chain-of-thought : forcer la reflexion

**Principe** : Ajouter une instruction qui force le LLM a montrer son raisonnement AVANT de conclure.

**Formulations efficaces :**
- "Raisonne etape par etape avant de donner ta reponse finale."
- "Detaille ton analyse point par point, puis conclus."
- "Avant de repondre, examine chaque element un par un."

```
Un fournisseur propose 15% de remise sur une commande de
12 400 EUR HT, mais impose un minimum de commande de 15 000 EUR.
Nous avons aussi une offre concurrente a 11 200 EUR HT sans minimum.

Raisonne etape par etape avant de donner ta recommandation finale.
```

---

### Slide 17 — Chain-of-thought : le resultat

## Le LLM raisonne maintenant correctement

**Reponse avec chain-of-thought :**

```
Etape 1 : Analyser l'offre A (fournisseur avec remise)
- Prix brut : 12 400 EUR HT
- Remise proposee : 15%
- MAIS minimum de commande : 15 000 EUR
- 12 400 EUR < 15 000 EUR => la remise ne s'applique PAS
- Prix reel offre A : 12 400 EUR (sans remise)

Etape 2 : Analyser l'offre B (concurrent)
- Prix : 11 200 EUR HT
- Pas de minimum de commande
- Prix reel offre B : 11 200 EUR

Etape 3 : Comparaison
- Offre A : 12 400 EUR | Offre B : 11 200 EUR
- Ecart : 1 200 EUR en faveur de l'offre B

Conclusion : L'offre B est plus avantageuse de 1 200 EUR,
et l'offre A ne permet meme pas d'obtenir la remise annoncee.
```

---

### Slide 18 — Schema du chain-of-thought

## Comment le chain-of-thought change le processus

```
SANS CHAIN-OF-THOUGHT           AVEC CHAIN-OF-THOUGHT
======================          =======================

+----------+                    +----------+
| Question |                    | Question |
+----+-----+                    +----+-----+
     |                               |
     v                               v
+-----------+                   +-----------+
|  Reponse  |  <- directe,     | Etape 1   |
| immediate |     risque        +-----------+
+-----------+     d'erreur           |
                                     v
                                +-----------+
                                | Etape 2   |
                                +-----------+
                                     |
                                     v
                                +-----------+
                                | Etape 3   |
                                +-----------+
                                     |
                                     v
                                +-----------+
                                | Conclusion|  <- verifiee,
                                |  finale   |     fiable
                                +-----------+
```

---

### Slide 19 — Cas d'usage du chain-of-thought par metier

## Quand utiliser le chain-of-thought ?

| Metier | Cas d'usage | Pourquoi c'est utile |
|--------|------------|---------------------|
| **RH** | Comparer des candidatures selon plusieurs criteres | Evite d'oublier un critere |
| **Finance** | Analyser la rentabilite d'un investissement | Chaque etape du calcul est verifiable |
| **Marketing** | Choisir un canal de communication | Force l'analyse de chaque option |
| **Commercial** | Evaluer la faisabilite d'une offre | Detecte les contraintes cachees |
| **Gestion** | Planifier un projet avec dependances | Identifie l'ordre logique des taches |

**Regle** : Des que le sujet implique un **calcul**, une **comparaison** ou une **decision multi-criteres**, utilisez le chain-of-thought.

---

### Slide 20 — Demonstration comparative

## Chain-of-thought en action : RH

**SANS chain-of-thought :**
```
J'ai 3 candidats pour un poste de responsable marketing digital.
Criteres : 5 ans exp. minimum, anglais courant, management.
Candidat A : 7 ans exp., anglais B2, manage 2 personnes
Candidat B : 4 ans exp., anglais C1, manage 5 personnes
Candidat C : 6 ans exp., anglais C2, pas de management
Quel est le meilleur candidat ?
```
-> Reponse typique : "Le candidat A" (sans justification solide)

**AVEC chain-of-thought :**
```
[meme question]
Analyse chaque candidat critere par critere, attribue une note
sur 5 pour chaque critere, puis classe-les avec justification.
```
-> Le LLM produit un **tableau comparatif** et une **recommandation argumentee**

---

### Slide 21 — Transition vers le prompting negatif

# Prompting Negatif
## Dire ce que vous NE voulez PAS

---

### Slide 22 — Le pouvoir du "Ne fais pas"

## Prompting negatif : les contraintes d'exclusion

**Principe** : Parfois, il est plus efficace de dire ce qu'on ne veut PAS que ce qu'on veut.

**Pourquoi ?** Le LLM a des "reflexes" — des patterns frequents dans ses reponses. Le prompting negatif desactive ces reflexes.

**Exemples de formulations :**
- "Ne commence PAS par une formule de politesse generique."
- "N'utilise PAS de jargon technique."
- "Ne fais PAS de liste a puces — redige en paragraphes."
- "Ne depasse PAS 200 mots."
- "Evite les superlatifs et le ton publicitaire."

---

### Slide 23 — Prompting negatif : avant / apres

## L'impact du prompting negatif

**SANS prompting negatif :**
```
Redige un email de bienvenue pour un nouveau collaborateur.
```
-> "Cher(e) [Prenom], C'est avec un immense plaisir que nous vous
   accueillons au sein de notre formidable equipe..."
   (ton generique, formules creuses)

**AVEC prompting negatif :**
```
Redige un email de bienvenue pour un nouveau collaborateur.

Contraintes :
- Ne commence PAS par "C'est avec plaisir" ou toute formule generique
- N'utilise PAS de superlatifs (formidable, exceptionnel, incroyable)
- Ne depasse PAS 150 mots
- Evite le ton corporate impersonnel
```
-> Email court, direct et authentique

---

### Slide 24 — Prompting negatif par metier

## Exemples de contraintes d'exclusion par metier

**RH :**
- "Ne mentionne PAS le salaire dans l'annonce"
- "Evite les formulations discriminantes liees a l'age"

**Finance :**
- "Ne fournis PAS de conseil fiscal — reste sur l'analyse des chiffres"
- "N'arrondis PAS les montants, garde 2 decimales"

**Marketing :**
- "N'utilise PAS de mots anglais quand un equivalent francais existe"
- "Evite le greenwashing et les affirmations non prouvees"

**Commercial :**
- "Ne denigre PAS la concurrence"
- "Ne promets PAS de delais que nous ne pouvons pas tenir"

**Gestion de projet :**
- "N'inclus PAS les weekends dans le planning"
- "Ne sous-estime PAS les temps de validation client"

---

### Slide 25 — Combiner les techniques

## La puissance de la combinaison

Vous pouvez melanger toutes les techniques dans un seul prompt :

```
[CREA + Few-shot + Chain-of-thought + Prompting negatif]

Contexte : Je suis controleur de gestion dans une PME industrielle.
Role : Agis comme un analyste financier senior.

Voici comment j'attends l'analyse :
Produit A : CA 150K, marge 22% -> Verdict : rentable, a developper
Produit B : CA 80K, marge 8% -> Verdict : a surveiller, marge faible

Analyse maintenant le Produit C : CA 200K, marge 12%,
tendance a la baisse depuis 3 trimestres.

Raisonne etape par etape.
Ne donne PAS de recommandation sans avoir chiffre l'impact.
Ne minimise PAS les signaux negatifs.
```

---

### Slide 26 — Transition vers la structuration des outputs

# Structuration des Outputs
## Obtenir exactement le format dont vous avez besoin

---

### Slide 27 — Pourquoi structurer les outputs ?

## Le probleme des reponses en "bloc de texte"

Sans consigne de format, le LLM repond en texte libre — difficile a exploiter.

```
TEXTE LIBRE (difficile a exploiter)    FORMAT STRUCTURE (actionnable)
===================================    =============================

"L'analyse montre que le projet        | Critere    | Note | Statut |
 A presente un ROI de 15% avec         |------------|------|--------|
 un risque modere tandis que le         | ROI        | 15%  | OK     |
 projet B offre un ROI de 22%          | Risque     | Mod. | Alerte |
 mais avec un risque eleve et          | Delai      | 6m   | OK     |
 un delai plus long de 2 mois          | Budget     | 95K  | OK     |
 supplementaires..."
                                        => Decision : Projet A recommande
```

---

### Slide 28 — Les formats disponibles

## Les formats que vous pouvez demander

**Tableau markdown :**
```
Presente les resultats sous forme de tableau avec les colonnes :
Nom | Valeur | Statut | Commentaire
```

**Liste numerotee avec hierarchie :**
```
Structure ta reponse en liste numerotee a 2 niveaux :
1. Point principal
   1.1 Detail
   1.2 Detail
```

**Sections nommees :**
```
Organise ta reponse avec ces sections exactes :
## RESUME EXECUTIF (3 lignes max)
## ANALYSE DETAILLEE
## RECOMMANDATIONS
## PROCHAINES ETAPES
```

**JSON simplifie (pour integration dans des outils) :**
```
Reponds au format JSON avec cette structure :
{ "categorie": "...", "priorite": "haute/moyenne/basse",
  "action": "...", "deadline": "JJ/MM/AAAA" }
```

---

### Slide 29 — Structuration : delimiteurs et sections

## Utiliser des delimiteurs pour organiser l'input ET l'output

**Dans votre prompt (input), delimitez les sections :**
```
Voici les donnees a analyser :

---DONNEES DE VENTE---
Janvier : 45 000 EUR
Fevrier : 52 000 EUR
Mars : 38 000 EUR
---FIN DONNEES---

---FORMAT ATTENDU---
1. Tendance generale (1 phrase)
2. Mois le plus performant et hypothese explicative
3. Mois le moins performant et actions correctives
4. Prevision pour le trimestre suivant
---FIN FORMAT---
```

Les delimiteurs (`---`, `###`, `"""`) aident le LLM a distinguer les donnees des instructions.

---

### Slide 30 — Demonstration : rapport structure

## Exemple complet — Rapport structure pour la direction

```
Contexte : Reunion du CODIR lundi.
Role : Agis comme un directeur financier preparant une synthese.

Genere un rapport avec EXACTEMENT cette structure :

# SYNTHESE MENSUELLE — [Mois]

## INDICATEURS CLES
| KPI | Valeur | Variation M-1 | Cible | Statut |
(utilise des symboles : OK / ALERTE / CRITIQUE)

## FAITS MARQUANTS (3 maximum, 1 ligne chacun)

## RISQUES IDENTIFIES
- Risque | Probabilite | Impact | Action

## DECISIONS A PRENDRE (formule en questions oui/non)

Donnees a integrer : [coller les donnees]
```

---

### Slide 31 — Recapitulatif du Bloc 1

## Bloc 1 — Ce que vous maitrisez maintenant

```
+------------------+----------------------------------------+
| Technique        | Quand l'utiliser                       |
+------------------+----------------------------------------+
| Few-shot         | Format precis, tache repetitive        |
| Chain-of-thought | Calcul, comparaison, decision          |
| Prompting negatif| Eviter les reflexes du LLM             |
| Structuration    | Rapport, tableau, donnees exploitables |
+------------------+----------------------------------------+
```

**Rappel** : ces techniques se **combinent** avec la methode CREA.
Elles ne la remplacent pas, elles la renforcent.

---

## BLOC 2 — CHAINES DE PROMPTS (1h00)

---

### Slide 32 — Introduction aux chaines de prompts

# Chaines de Prompts
## Decomposer le complexe en etapes simples

---

### Slide 33 — Le concept : pourquoi chainer ?

## Un prompt unique ne suffit pas toujours

**Probleme** : Quand la tache est trop complexe, un prompt unique donne un resultat moyen — le LLM essaie de tout faire en meme temps.

**Solution** : Decomposer en etapes, comme une recette de cuisine.

```
PROMPT UNIQUE (fragile)           CHAINE DE PROMPTS (robuste)
========================          ============================

+-----------------------+         +----------+    +----------+
| Fais-moi une etude    |         | Prompt 1 |--->| Prompt 2 |
| de marche complete    |         | Collecte |    | Analyse  |
| avec analyse, chiffres|         +----------+    +----+-----+
| recommandations et    |                              |
| plan d'action         |                              v
+-----------+-----------+         +----------+    +----------+
            |                     | Prompt 4 |<---| Prompt 3 |
            v                     | Plan     |    | Synthese |
   +------------------+           +----------+    +----------+
   | Resultat moyen,  |
   | incomplet, vague  |          => Chaque etape est verifiable
   +------------------+              et ajustable independamment
```

---

### Slide 34 — La methodologie en 4 etapes

## Comment construire une chaine de prompts

```
ETAPE 1                ETAPE 2               ETAPE 3              ETAPE 4
Decomposer             Ecrire                Enchainer            Verifier

+-----------+     +------------+     +---------------+     +-----------+
| Tache     |     | Prompt     |     | Sortie de P1  |     | Relire    |
| complexe  | --> | pour chaque| --> | = Entree de   | --> | chaque    |
| en sous-  |     | sous-tache |     | P2, etc.      |     | sortie    |
| taches    |     |            |     |               |     | et ajuster|
+-----------+     +------------+     +---------------+     +-----------+
```

**Etape 1** : Listez les sous-taches (que feriez-vous manuellement ?)
**Etape 2** : Un prompt par sous-tache (precis, avec CREA + techniques)
**Etape 3** : Copiez-collez la sortie du prompt N comme contexte du prompt N+1
**Etape 4** : Verifiez la sortie de chaque etape avant de continuer

---

### Slide 35 — Exemple complet : preparation d'un appel d'offres

## Chaine de prompts — Appel d'offres (Commercial + Gestion)

**Contexte** : Vous devez preparer une reponse a un appel d'offres pour une prestation de conseil.

```
Chaine de 4 prompts :

PROMPT 1 : ANALYSE DU CAHIER DES CHARGES
"Voici le cahier des charges de l'appel d'offres [coller].
Extrais sous forme de tableau :
- Les exigences obligatoires
- Les criteres de selection et leur ponderation
- Les contraintes de delai et de budget
- Les livrables attendus"

         |
         v  (copier la sortie)

PROMPT 2 : EVALUATION DE NOTRE ADEQUATION
"Voici les exigences de l'appel d'offres : [coller sortie P1]
Voici nos competences et references : [coller fiche entreprise]
Pour chaque exigence, evalue notre adequation (forte/moyenne/faible)
et identifie les ecarts a combler.
Raisonne etape par etape."
```

---

### Slide 36 — Exemple appel d'offres (suite)

## Chaine de prompts — Appel d'offres (suite)

```
         |
         v  (copier la sortie)

PROMPT 3 : REDACTION DE LA PROPOSITION TECHNIQUE
"Voici notre analyse d'adequation : [coller sortie P2]
Redige la proposition technique en suivant ce plan :
1. Comprehension du besoin (montrer qu'on a compris)
2. Methodologie proposee (etapes concretes)
3. Equipe projet (roles et profils)
4. Planning previsionnel (sous forme de tableau)
Ne fais PAS de promesses irrealistes.
Ne depasse PAS 2 pages."

         |
         v  (copier la sortie)

PROMPT 4 : CHIFFRAGE ET SYNTHESE
"Voici la proposition technique : [coller sortie P3]
Voici nos tarifs journaliers : [coller grille tarifaire]
Genere :
1. Le chiffrage detaille (tableau : poste, nb jours, TJ, total)
2. Le resume executif (10 lignes max pour le decideur)
3. Les 3 arguments differenciants a mettre en avant"
```

---

### Slide 37 — Schema de la chaine "appel d'offres"

## Vue d'ensemble de la chaine

```
+-------------------+     +-------------------+
| P1 : Analyse      |     | ENTREE :          |
| cahier des charges|---->| Cahier des charges|
| SORTIE : tableau  |     | + fiche entreprise|
| d'exigences       |     +-------------------+
+--------+----------+
         |
         v
+--------+----------+
| P2 : Evaluation   |
| de l'adequation   |
| SORTIE : matrice  |
| forces/faiblesses |
+--------+----------+
         |
         v
+--------+----------+
| P3 : Proposition  |
| technique         |
| SORTIE : document |
| structure         |
+--------+----------+
         |
         v
+--------+----------+
| P4 : Chiffrage    |
| et synthese       |
| SORTIE : offre    |
| complete          |
+-------------------+
```

---

### Slide 38 — Exemple complet : etude de marche express

## Chaine de prompts — Etude de marche (Marketing)

```
PROMPT 1 : CADRAGE
"Je suis responsable marketing dans une entreprise de [secteur].
Nous envisageons de lancer [produit/service].
Definis les 5 questions cles auxquelles cette etude de marche
doit repondre. Pour chaque question, indique les sources
d'information potentielles."

         |
         v  (copier la sortie)

PROMPT 2 : ANALYSE DE LA DEMANDE
"Voici les questions cles de notre etude : [coller sortie P1]
A partir des informations suivantes sur notre marche cible :
[coller donnees internes / infos sectorielles]
Analyse la demande : taille du marche, tendances, segments cles.
Presente les resultats en tableau.
Raisonne etape par etape."
```

---

### Slide 39 — Etude de marche (suite)

## Chaine de prompts — Etude de marche (suite)

```
         |
         v  (copier la sortie)

PROMPT 3 : ANALYSE CONCURRENTIELLE
"Voici notre analyse de la demande : [coller sortie P2]
Voici la liste de nos concurrents identifies : [coller liste]
Pour chaque concurrent, analyse :
- Positionnement et cible
- Forces et faiblesses
- Fourchette de prix
Presente sous forme de matrice comparative.
N'invente PAS de donnees — signale quand une information manque."

         |
         v  (copier la sortie)

PROMPT 4 : RECOMMANDATIONS STRATEGIQUES
"Voici l'analyse de la demande : [coller sortie P2]
Voici l'analyse concurrentielle : [coller sortie P3]
Genere :
1. SYNTHESE (5 lignes max)
2. OPPORTUNITES identifiees (top 3)
3. MENACES a anticiper (top 3)
4. RECOMMANDATION de positionnement
5. PROCHAINES ETAPES (actions concretes, responsable, delai)
Format : sections avec titres, pas de texte continu."
```

---

### Slide 40 — Chaines de prompts par metier

## Idees de chaines pour chaque metier

| Metier | Chaine de prompts | Nb prompts |
|--------|------------------|------------|
| **RH** | Processus de recrutement complet (fiche de poste -> grille d'entretien -> evaluation -> offre) | 4 |
| **Finance** | Preparation budgetaire (collecte -> analyse N-1 -> previsions -> presentation) | 4 |
| **Marketing** | Lancement campagne (brief -> personas -> messages -> planning editorial) | 4 |
| **Commercial** | Cycle de vente (qualification lead -> proposition -> negociation -> closing) | 4 |
| **Gestion** | Cadrage projet (expression de besoin -> planning -> risques -> comite de lancement) | 4 |

**Conseil** : Commencez avec 3-4 prompts. N'allez pas au-dela de 6 — le gain marginal diminue.

---

### Slide 41 — Les regles d'or des chaines de prompts

## 5 regles pour des chaines efficaces

**1. Une tache par prompt**
Chaque prompt a UN objectif clair. Si vous ecrivez "et aussi", c'est qu'il faut couper.

**2. Sortie = Entree**
La sortie du prompt N doit etre directement utilisable comme entree du prompt N+1.

**3. Verifiez a chaque etape**
Ne lancez pas le prompt suivant si la sortie actuelle est incorrecte. Corrigez d'abord.

**4. Gardez le contexte**
Rappelez le contexte general a chaque nouveau prompt (le LLM n'a pas de memoire entre les echanges dans un nouveau fil).

**5. Documentez votre chaine**
Notez vos prompts dans un document reutilisable — c'est votre "processus automatise".

---

### Slide 42 — Recapitulatif du Bloc 2

## Bloc 2 — Ce que vous maitrisez maintenant

```
AVANT                              APRES
======                             ======

+------------------------+         +------+ +------+ +------+ +------+
| 1 prompt enorme        |         | P1   | | P2   | | P3   | | P4   |
| qui essaie de tout     |  --->   | Cadre| |Analyse| |Redige| |Conclut|
| faire en meme temps    |         +--+---+ +--+---+ +--+---+ +--+---+
+------------------------+            |        |        |        |
                                      +--------+--------+--------+
Resultat : moyen                   Resultat : precis, verifiable
```

Vous savez decomposer une tache complexe en chaine de prompts maitrisee.

---

## BLOC 3 — ATELIER PRATIQUE (1h00)

---

### Slide 43 — Consignes de l'atelier

## Atelier : Construisez votre chaine de prompts metier

**Duree** : 40 minutes en groupe + 20 minutes de restitution

**Groupes** : 2-3 personnes du meme metier (ou de metiers proches)

**Mission** : Construisez une chaine de 3-4 prompts pour un cas reel de votre quotidien.

**Etapes :**
1. **Choisissez un cas concret** (10 min)
   - Une tache complexe que vous faites regulierement
   - Exemples : preparer un reporting, rediger un document, analyser des donnees

2. **Decomposez en sous-taches** (5 min)
   - Listez les etapes que vous feriez manuellement

3. **Redigez les prompts** (20 min)
   - Un prompt par sous-tache
   - Utilisez CREA + les techniques vues aujourd'hui
   - Testez chaque prompt et ajustez

4. **Preparez votre restitution** (5 min)

---

### Slide 44 — Suggestions de cas par metier

## Idees de cas concrets pour l'atelier

**RH :**
- Preparer un entretien annuel (grille -> questions -> synthese -> plan de dev.)
- Construire un plan d'integration pour un nouveau collaborateur

**Finance :**
- Analyser les ecarts budgetaires du trimestre (collecte -> analyse -> alertes -> memo)
- Preparer la cloture mensuelle (checklist -> anomalies -> ecritures -> reporting)

**Marketing :**
- Creer une newsletter mensuelle (veille -> angle -> redaction -> objet email)
- Preparer le bilan d'une campagne (donnees -> analyse -> enseignements -> next steps)

**Commercial :**
- Qualifier un prospect strategique (recherche -> scoring -> plan d'approche -> email)
- Preparer une negociation tarifaire (historique -> arguments -> scenarios -> BATNA)

**Gestion :**
- Rediger un compte-rendu de reunion (notes brutes -> structure -> actions -> diffusion)
- Preparer un comite de pilotage (collecte KPI -> alertes -> decisions -> support)

---

### Slide 45 — Grille de restitution

## Restitution : presentez votre chaine (3 min par groupe)

**Ce que chaque groupe presente :**

1. **Le cas choisi** : quelle tache ? pourquoi celle-la ?
2. **La decomposition** : combien d'etapes ? quelle logique ?
3. **Un prompt cle** : montrez votre meilleur prompt de la chaine
4. **Le resultat** : qu'a produit le LLM ? Etait-ce exploitable ?
5. **Ce que vous avez appris** : quelle technique a fait la difference ?

**Criteres d'evaluation collective :**

| Critere | Question a se poser |
|---------|-------------------|
| Clarte | Chaque prompt a-t-il UN objectif clair ? |
| Techniques | Few-shot, chain-of-thought, negatif utilises ? |
| Enchainement | La sortie de chaque prompt alimente le suivant ? |
| Resultat | Le livrable final est-il utilisable en l'etat ? |

---

### Slide 46 — Synthese de la session

## Session 4 — Ce que vous repartez avec aujourd'hui

```
+-----------------------------------------------------------+
|                    VOTRE BOITE A OUTILS                    |
+-----------------------------------------------------------+
|                                                           |
|  BASE (Session 3)           AVANCE (Session 4)            |
|  ~~~~~~~~~~~~~~~~           ~~~~~~~~~~~~~~~~~~~~~~         |
|  Methode CREA               Few-shot prompting             |
|  Prompts structures         Chain-of-thought               |
|  Iteration                  Prompting negatif              |
|                             Structuration des outputs      |
|                             Chaines de prompts             |
|                                                           |
+-----------------------------------------------------------+
|  PROCHAINE ETAPE : Session 5 — Les outils IA en pratique  |
+-----------------------------------------------------------+
```

---

### Slide 47 — Les reflexes a adopter

## Vos nouveaux reflexes au quotidien

**Avant d'ecrire un prompt, posez-vous ces questions :**

1. Est-ce que je peux **montrer un exemple** du resultat attendu ? -> Few-shot
2. Est-ce que la tache demande de **raisonner ou comparer** ? -> Chain-of-thought
3. Y a-t-il des **reflexes du LLM** que je veux eviter ? -> Prompting negatif
4. Dans quel **format** ai-je besoin du resultat ? -> Structuration
5. La tache est-elle **trop complexe** pour un seul prompt ? -> Chaine de prompts

**Et toujours** : commencez par CREA, puis ajoutez ces techniques par-dessus.

---

### Slide 48 — Fin de session

# Merci !

## Session 4 terminee

**Ce que nous avons couvert :**
- Zero-shot vs Few-shot prompting
- Chain-of-thought (raisonnement etape par etape)
- Prompting negatif (contraintes d'exclusion)
- Structuration des outputs
- Chaines de prompts pour taches complexes

**Prochaine session** : Les outils IA en pratique dans votre environnement de travail

> "Un bon prompt, c'est un bon briefing : plus vous etes precis avec l'IA,
> plus le resultat ressemble a ce que vous aviez en tete."

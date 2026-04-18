# SLIDES-10 — Projet Final, Presentations et Evaluation

> **Session 10** — Jour 5, apres-midi (14h00-17h30)
> **Duree** : 3h30 | **Niveau** : Avance
> **Prerequis** : Sessions 1-9 (integralite de la formation), conception du projet validee (Session 9)
> **Objectifs** : Construire le projet, documenter, presenter, evaluer les acquis, planifier la suite

---

<!-- ============================================================ -->
<!-- BLOC 1 — CONSTRUCTION DU PROJET (1h30)                       -->
<!-- ============================================================ -->

## BLOC 1 — CONSTRUCTION DU PROJET (1h30)

---

### Slide 1 — Page de titre

# Projet Final, Presentations et Evaluation
## Session 10 — Le grand final : montrez ce que vous savez faire

Formation IA pour les Metiers du Tertiaire
Jour 5 — Apres-midi

---

### Slide 2 — Deroulement de l'apres-midi

| Bloc | Contenu | Duree |
|------|---------|-------|
| 1 | Construction du projet dans Make | 1h30 |
| -- | **Pause** | **10 min** |
| 2 | Documentation : fiche projet | 30 min |
| 3 | Presentations orales + feedback | 1h00 |
| -- | **Pause** | **5 min** |
| 4 | Evaluation finale (QCM + auto-evaluation) et cloture | 30 min |

---

### Slide 3 — Consignes du projet

## Rappel : ce que vous devez construire

**Votre scenario d'automatisation IA doit comporter :**

```
+------------------------------------------------------------------+
|                                                                  |
|  EXIGENCES MINIMALES :                                           |
|                                                                  |
|  1. Au moins 3 etapes (modules) dans Make                        |
|  2. Au moins 1 etape utilisant l'IA                              |
|     (module HTTP vers OpenAI ou module IA integre)               |
|  3. Un trigger pertinent pour votre quotidien professionnel      |
|  4. Un resultat concret et utile                                 |
|     (email, document, notification, mise a jour de tableau)      |
|                                                                  |
|  BONUS (non obligatoire) :                                       |
|  - Filtre ou condition dans le scenario                          |
|  - Iteration sur plusieurs elements                              |
|  - Gestion d'erreur (error handler)                              |
|                                                                  |
+------------------------------------------------------------------+
```

---

### Slide 4 — Points d'etape

## Jalons pendant la construction (1h30)

```
14h00  DEBUT
  |    Ouvrez Make et commencez a construire votre scenario
  |    Reprenez votre fiche de conception de ce matin
  |
14h20  POINT D'ETAPE 1 — Le trigger fonctionne
  |    Le formateur passe verifier que chaque trigger est operationnel
  |    Si blocage : aide individuelle
  |
14h45  POINT D'ETAPE 2 — L'appel IA fonctionne
  |    Le module HTTP (OpenAI) renvoie un resultat correct
  |    Testez avec "Run once"
  |
15h10  POINT D'ETAPE 3 — Le scenario complet tourne
  |    Toutes les etapes s'enchainent sans erreur
  |    Un test de bout en bout reussi
  |
15h30  FIN DE CONSTRUCTION
       Scenario fonctionnel + pret a documenter
```

**Conseil** : si vous etes bloque sur une etape, passez a la suivante et revenez apres. Le formateur est la pour debloquer.

---

### Slide 5 — Objectif minimum vs objectif ambitieux

## Deux niveaux d'objectif

```
OBJECTIF MINIMUM (a atteindre absolument) :
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
[Trigger] --> [Etape intermediaire] --> [Etape IA]
   (O)              [ ]                    {~}

Exemple : Google Sheets --> Lire donnees --> API OpenAI genere un texte
--> Le texte s'affiche dans le log de Make (pas besoin d'action finale)

OBJECTIF AMBITIEUX (pour ceux qui avancent bien) :
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
[Trigger] --> [Etape IA] --> [Filtre] --> [Action 1] --> [Action 2]
   (O)           {~}           < >          [ ]            [ ]

Exemple : Sheets --> IA analyse --> Si urgent --> Email alerte --> MAJ Sheets
```

**L'objectif minimum suffit pour valider le projet.** L'essentiel est de montrer que vous savez integrer l'IA dans un workflow automatise.

---

<!-- ============================================================ -->
<!-- BLOC 2 — DOCUMENTATION (30 min)                              -->
<!-- ============================================================ -->

## BLOC 2 — DOCUMENTATION (30 min)

---

### Slide 6 — La fiche projet

## Documentez votre projet (30 min)

**Pourquoi documenter ?**
- Pour presenter clairement votre projet aux collegues
- Pour pouvoir le reproduire ou l'ameliorer plus tard
- Pour evaluer votre comprehension des concepts

---

### Slide 7 — Modele de fiche projet

## Fiche projet a remplir

```
+==================================================================+
|                    FICHE PROJET — MINI-PROJET IA                 |
+==================================================================+
|                                                                  |
|  NOM DU PROJET : _______________________________________________  |
|  AUTEUR : ___________________________  DATE : ________________   |
|  METIER / SERVICE : ____________________________________________  |
|                                                                  |
|------------------------------------------------------------------+
|  1. PROBLEME RESOLU                                              |
|     Quelle tache repetitive ce scenario automatise-t-il ?        |
|     ____________________________________________________________  |
|     ____________________________________________________________  |
|                                                                  |
|------------------------------------------------------------------+
|  2. ARCHITECTURE DU SCENARIO                                     |
|     Dessinez ou decrivez les etapes :                            |
|                                                                  |
|     [__________] --> [__________] --> [__________] --> [________] |
|                                                                  |
|     Nombre total d'etapes : ____                                 |
|     Etape(s) utilisant l'IA : ____                               |
|                                                                  |
|------------------------------------------------------------------+
|  3. PROMPTS UTILISES                                             |
|     Prompt systeme (role de l'IA) :                              |
|     ____________________________________________________________  |
|     Prompt utilisateur (instruction) :                           |
|     ____________________________________________________________  |
|     ____________________________________________________________  |
|                                                                  |
|------------------------------------------------------------------+
|  4. RESULTATS OBTENUS                                            |
|     Le scenario fonctionne-t-il ? [ ] Oui  [ ] Partiellement    |
|     Exemple de resultat produit :                                |
|     ____________________________________________________________  |
|     ____________________________________________________________  |
|                                                                  |
|------------------------------------------------------------------+
|  5. TEMPS GAGNE ESTIME                                           |
|     Temps pour faire cette tache manuellement : ____ min         |
|     Temps avec le scenario automatise : ____ min                 |
|     Gain estime par semaine : ____ min                           |
|                                                                  |
|------------------------------------------------------------------+
|  6. AMELIORATIONS POSSIBLES                                      |
|     Si j'avais plus de temps, j'ajouterais :                     |
|     ____________________________________________________________  |
|     ____________________________________________________________  |
|                                                                  |
+==================================================================+
```

---

<!-- ============================================================ -->
<!-- BLOC 3 — PRESENTATIONS ORALES (1h00)                         -->
<!-- ============================================================ -->

## BLOC 3 — PRESENTATIONS ORALES (1h00)

---

### Slide 8 — Format des presentations

## Presentations : le format

**Pour chaque participant :**

```
+------------------------------------------------------------------+
|                                                                  |
|  PRESENTATION : 3 minutes                                        |
|  ~~~~~~~~~~~~~~~~~~~~~~~~~~                                      |
|  - Quel probleme vous avez resolu                                |
|  - Demonstration du scenario (Run once dans Make)                |
|  - Montrer le resultat produit                                   |
|  - Temps gagne estime                                            |
|                                                                  |
|  FEEDBACK : 2 minutes                                            |
|  ~~~~~~~~~~~~~~~~~~~~~~~~~~                                      |
|  - Questions du groupe                                           |
|  - Feedback du formateur                                         |
|  - 1 point fort + 1 suggestion d'amelioration                    |
|                                                                  |
|  TOTAL : 5 minutes par personne                                  |
|                                                                  |
+------------------------------------------------------------------+
```

**Conseil** : pas besoin de slides. Montrez directement Make et le resultat.

---

### Slide 9 — Grille d'evaluation des presentations

## Grille d'evaluation par les pairs

| Critere | 1 | 2 | 3 | 4 |
|---------|---|---|---|---|
| **Pertinence metier** : le projet resout un vrai probleme | Pas pertinent | Peu pertinent | Pertinent | Tres pertinent |
| **Integration IA** : l'IA apporte une vraie valeur ajoutee | IA absente | IA superficielle | IA utile | IA indispensable |
| **Fonctionnement** : le scenario tourne sans erreur | Ne fonctionne pas | Fonctionne partiellement | Fonctionne | Fonctionne parfaitement |
| **Clarte** : la presentation est claire et comprensible | Confuse | Acceptable | Claire | Tres claire |
| **Creativite** : originalite de l'approche | Basique | Correct | Original | Tres creatif |

**Chaque participant evalue les autres.** Le formateur synthetise.

---

### Slide 10 — Vote du meilleur projet

## Vote du groupe

**A la fin de toutes les presentations :**

Chaque participant vote pour **le projet le plus impressionnant** (autre que le sien).

Criteres libres : utilite, creativite, qualite technique, clarte de la presentation.

Le gagnant recoit les felicitations du groupe (et la satisfaction du travail bien fait).

---

<!-- ============================================================ -->
<!-- BLOC 4 — EVALUATION ET CLOTURE (30 min)                      -->
<!-- ============================================================ -->

## BLOC 4 — EVALUATION ET CLOTURE (30 min)

---

### Slide 11 — QCM final

## Evaluation finale : QCM de 30 questions

**Format :**
- 30 questions a choix multiples
- Couvre l'ensemble de la formation (Sessions 1 a 10)
- Duree : 15 minutes
- Seuil de reussite : 20/30 (67%)

**Repartition des questions :**

| Thematique | Nombre de questions |
|-----------|-------------------|
| Fondamentaux IA et LLM (Sessions 1-2) | 6 |
| Prompting et chaines de prompts (Sessions 3-4) | 6 |
| RAG, assistants, workflows (Session 5) | 4 |
| Cas d'usage metier (Sessions 6-7) | 4 |
| Integration Workspace/M365 (Session 8) | 4 |
| Automatisation, APIs, Make (Sessions 9-10) | 6 |

Le QCM est distribue maintenant. Vous avez 15 minutes.

---

### Slide 12 — Auto-evaluation des competences C1-C6

## Auto-evaluation finale : ou en etes-vous ?

**Evaluez votre niveau sur chaque competence cle :**

| Code | Competence | Avant la formation | Apres la formation |
|------|-----------|-------------------|-------------------|
| **C1** | Comprendre le fonctionnement des LLM et de l'IA generative | /4 | /4 |
| **C2** | Rediger des prompts efficaces et structures | /4 | /4 |
| **C3** | Utiliser l'IA pour des taches metier concretes | /4 | /4 |
| **C4** | Integrer l'IA dans les outils bureautiques (Workspace, M365) | /4 | /4 |
| **C5** | Creer des automatisations no-code integrant l'IA | /4 | /4 |
| **C6** | Evaluer les limites, risques et enjeux ethiques de l'IA | /4 | /4 |

Echelle : 1 = Pas du tout / 2 = Un peu / 3 = Bien / 4 = Tres bien

---

### Slide 13 — Plan d'action post-formation

## Votre plan d'action pour les 30 prochains jours

**Remplissez individuellement :**

```
+==================================================================+
|              MON PLAN D'ACTION POST-FORMATION                    |
+==================================================================+
|                                                                  |
|  SEMAINE 1 : Je mets en pratique immediatement                   |
|  _____________________________________________________________   |
|  (ex: utiliser Gemini dans Docs pour mes comptes rendus)         |
|                                                                  |
|  SEMAINE 2 : J'approfondis un outil                              |
|  _____________________________________________________________   |
|  (ex: creer 3 prompts CREA pour mes taches recurrentes)          |
|                                                                  |
|  SEMAINE 3 : Je partage avec mon equipe                          |
|  _____________________________________________________________   |
|  (ex: presenter 3 usages IA utiles en reunion d'equipe)          |
|                                                                  |
|  SEMAINE 4 : J'automatise une tache                              |
|  _____________________________________________________________   |
|  (ex: activer mon scenario Make pour la veille concurrentielle)  |
|                                                                  |
|  MON OBJECTIF A 3 MOIS :                                         |
|  _____________________________________________________________   |
|                                                                  |
+==================================================================+
```

---

### Slide 14 — Cloture de la formation

## Tour de table et cloture

**Tour de table (1 mot ou 1 phrase chacun) :**
- Qu'est-ce qui vous a le plus marque dans cette formation ?
- Quel est le premier usage IA que vous allez mettre en place ?

**Ressources pour continuer :**
- Documentation des outils : ChatGPT, Claude, Gemini, Make
- Communautes en ligne : r/ChatGPT, forums Make, groupes LinkedIn IA
- Veille : suivre les actualites IA (newsletters, podcasts)
- Le support du formateur reste disponible par email pendant 1 mois

**Enquete de satisfaction :**
- Un formulaire vous sera envoye par email
- Vos retours sont precieux pour ameliorer la formation
- Merci de le remplir dans les 48h

---

### Slide 15 — Attestation et remerciements

## Felicitations !

```
+==================================================================+
|                                                                  |
|              ATTESTATION DE FIN DE FORMATION                     |
|                                                                  |
|     Formation : IA pour les Metiers du Tertiaire                 |
|     Duree : 35 heures (5 jours)                                  |
|     Niveau : Fondamentaux --> Intermediaire --> Avance            |
|                                                                  |
|     Competences validees :                                       |
|     [x] C1 — Comprendre l'IA et les LLM                         |
|     [x] C2 — Prompting efficace                                  |
|     [x] C3 — Usages metier de l'IA                               |
|     [x] C4 — Integration bureautique                             |
|     [x] C5 — Automatisation no-code + IA                         |
|     [x] C6 — Ethique et limites de l'IA                          |
|                                                                  |
+==================================================================+

          Merci pour votre participation et votre engagement.
                L'IA est un outil. Vous etes le talent.
                        Bonne continuation !
```

---

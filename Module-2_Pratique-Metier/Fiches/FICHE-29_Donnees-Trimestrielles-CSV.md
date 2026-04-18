# FICHE-29 : Jeu de Donnees Trimestrielles CSV

**Formation IA pour les Metiers du Tertiaire**
Fiche d'exercice -- Atelier Finance, Session 7

> Entreprise fil rouge : **AgroTech Solutions**, PME agroalimentaire B2B, 80 salaries, Lyon.
> Ces donnees alimentent l'exercice FIN-1 (FICHE-28).

---

## 1. Compte de resultat simplifie -- T1 a T4 2024

Copiez le bloc CSV ci-dessous et collez-le dans votre prompt.

```csv
COMPTE_DE_RESULTAT;T1_2024;T2_2024;T3_2024;T4_2024;UNITE
;;;;;;
CHIFFRE_AFFAIRES_TOTAL;2 340 000;2 580 000;2 050 000;2 890 000;EUR
;;;;;;
CA_Sauces_Pro;980 000;1 050 000;820 000;1 120 000;EUR
CA_Condiments_Bio;420 000;480 000;390 000;680 000;EUR
CA_Solutions_Tracabilite;640 000;720 000;580 000;750 000;EUR
CA_Services;300 000;330 000;260 000;340 000;EUR
;;;;;;
COUTS_DIRECTS_TOTAL;1 380 000;1 500 000;1 270 000;1 640 000;EUR
;;;;;;
Matieres_premieres;820 000;890 000;760 000;980 000;EUR
Main_oeuvre_production;380 000;400 000;350 000;430 000;EUR
Transport_logistique;180 000;210 000;160 000;230 000;EUR
;;;;;;
MARGE_BRUTE;960 000;1 080 000;780 000;1 250 000;EUR
Taux_marge_brute;41,0%;41,9%;38,0%;43,3%;POURCENTAGE
;;;;;;
CHARGES_EXPLOITATION_TOTAL;780 000;800 000;790 000;850 000;EUR
;;;;;;
Salaires_charges_hors_prod;420 000;430 000;425 000;445 000;EUR
Loyers_charges_locatives;85 000;85 000;85 000;85 000;EUR
Marketing_communication;95 000;110 000;75 000;130 000;EUR
Recherche_developpement;60 000;55 000;65 000;70 000;EUR
Frais_generaux;120 000;120 000;140 000;120 000;EUR
;;;;;;
EBITDA;180 000;280 000;-10 000;400 000;EUR
Taux_EBITDA;7,7%;10,9%;-0,5%;13,8%;POURCENTAGE
;;;;;;
Dotations_amortissements;65 000;65 000;65 000;65 000;EUR
Charges_financieres;18 000;17 500;18 200;16 800;EUR
;;;;;;
RESULTAT_AVANT_IMPOT;97 000;197 500;-93 200;318 200;EUR
Impot_societes;24 250;49 375;0;79 550;EUR
;;;;;;
RESULTAT_NET;72 750;148 125;-93 200;238 650;EUR
Taux_resultat_net;3,1%;5,7%;-4,5%;8,3%;POURCENTAGE
```

---

## 2. KPIs commerciaux -- T1 a T4 2024

```csv
KPI_COMMERCIAL;T1_2024;T2_2024;T3_2024;T4_2024;UNITE
;;;;;;
Clients_actifs;185;198;172;215;NOMBRE
Nouveaux_clients;12;18;5;28;NOMBRE
Clients_perdus;4;5;16;3;NOMBRE
Taux_retention;97,8%;97,5%;90,7%;98,6%;POURCENTAGE
;;;;;;
Panier_moyen_commande;4 200;4 350;3 800;4 680;EUR
Frequence_commande_mensuelle;2,1;2,2;1,9;2,4;NOMBRE
CA_moyen_par_client;12 649;13 030;11 919;13 442;EUR
;;;;;;
Nombre_commerciaux;6;6;6;7;NOMBRE
CA_par_commercial;390 000;430 000;341 667;412 857;EUR
RDV_prospect_realises;45;52;28;68;NOMBRE
Taux_conversion_RDV;26,7%;34,6%;17,9%;41,2%;NOMBRE
;;;;;;
Top_client_CA;Groupe_Restalliance;Groupe_Restalliance;Groupe_Restalliance;Sodexo_Restauration;NOM
Top_client_montant;185 000;192 000;95 000;210 000;EUR
Concentration_top5;38,2%;36,5%;42,1%;33,8%;POURCENTAGE
;;;;;;
NPS_clients;7,8;8,1;7,2;8,5;SCORE_10
Reclamations;8;6;14;5;NOMBRE
Delai_paiement_moyen;42;39;51;36;JOURS
```

---

## 3. Cle de lecture -- L'histoire racontee par les donnees

Les donnees ci-dessus sont construites pour raconter l'evolution suivante :

| Trimestre | Dynamique | Elements cles |
|---|---|---|
| **T1 2024** | Croissance moderee | Demarrage d'annee solide, base de clients stable, marge brute a 41 %. Activite dans la norme saisonniere. |
| **T2 2024** | Acceleration | Meilleur trimestre de l'annee en tendance : CA +10 % vs T1, marge brute en legere hausse (41,9 %), 18 nouveaux clients. Le marketing est renforce (+16 % vs T1). |
| **T3 2024** | Baisse marquee | Effet combine : saisonnalite estivale (baisse habituelle de 10-15 %) + perte du client Groupe Restalliance qui reduit ses commandes de 50 % (litige qualite). EBITDA negatif (-10 K EUR), 16 clients perdus, NPS en baisse (7,2), reclamations doublees (14), delais de paiement allonges (51 jours). Frais generaux en hausse (+17 % vs T2) lies a des couts exceptionnels (audit qualite, penalites). |
| **T4 2024** | Reprise forte | Signature de Sodexo Restauration comme nouveau top client. Lancement de la gamme Condiments Bio elargie (+74 % vs T3). Recrutement d'un 7e commercial. Meilleur taux de conversion (41,2 %). Marge brute record (43,3 %). EBITDA a 400 K EUR (13,8 %). NPS au plus haut (8,5). Concentration top 5 en baisse (33,8 %) = diversification du portefeuille. |

---

## 4. Donnees complementaires de contexte

Pour enrichir le prompt, l'apprenant peut ajouter ces elements de contexte :

- **Secteur** : Agroalimentaire B2B, marche francais
- **Effectif** : 80 salaries (dont 6-7 commerciaux, 25 en production, 10 en R&D)
- **Concurrents principaux** : Transgourmet (grand groupe), Pomona (distribution), startups FoodTech
- **Evenements marquants 2024** :
  - Janvier : Salon SIRHA Lyon (investissement marketing)
  - Mars : Obtention certification Bio sur 3 nouvelles references
  - Juillet : Litige qualite avec Groupe Restalliance (lot non conforme)
  - Septembre : Resolution du litige, plan qualite renforce
  - Octobre : Signature contrat-cadre Sodexo Restauration (3 ans)
  - Novembre : Lancement gamme "Condiments Bio Terroir" (6 references)
  - Decembre : Embauche d'un commercial specialise restauration collective

---

> **ATTENTION : Donnees fictives -- Exercice pedagogique uniquement.**
> Ces donnees ont ete construites pour les besoins de la formation.
> Elles ne correspondent a aucune entreprise reelle.
> Ne jamais envoyer de vraies donnees financieres a un LLM public.

---

*Formation IA pour les Metiers du Tertiaire -- Module 2 : Pratique Metier*
*Fiche d'exercice FICHE-29 -- Session 7*

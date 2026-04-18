# Formation IA pour les Métiers du Tertiaire — Fiche de référence — Session 9

# FICHE 43 — Comparatif Make vs Zapier vs n8n vs Power Automate

---

## Tableau comparatif détaillé

| Critère | Make | Zapier | n8n | Power Automate |
|---------|------|--------|-----|----------------|
| **Prix (plan gratuit)** | Gratuit (1 000 ops/mois) | Gratuit (100 tâches/mois) | Gratuit (self-hosted illimité) | Gratuit (limité, inclus dans Microsoft 365) |
| **Plans payants (entrée)** | Core : ~9 $/mois (10 000 ops) | Starter : ~19.99 $/mois (750 tâches) | Starter Cloud : ~20 $/mois | Per user : ~15 $/mois/utilisateur |
| **Opérations/tâches gratuites** | 1 000 opérations/mois | 100 tâches/mois | Illimité (self-hosted) | Limité (flux standard inclus M365) |
| **Interface** | Visuelle, drag-and-drop, canvas 2D (organigramme) | Linéaire, étape par étape (liste verticale) | Visuelle, canvas (similaire à Make) | Linéaire avec quelques vues avancées |
| **Nombre d'intégrations** | ~1 800+ applications | ~7 000+ applications | ~400+ nœuds natifs + HTTP | ~1 000+ connecteurs (focus Microsoft) |
| **Facilité d'apprentissage** | 4/5 — Intuitif grâce au visuel | 5/5 — Le plus simple | 3/5 — Courbe d'apprentissage plus technique | 3/5 — Simple si déjà dans l'écosystème Microsoft |
| **Puissance / flexibilité** | 4.5/5 — Très flexible, logique avancée | 3/5 — Limité sur la logique complexe | 5/5 — Contrôle total, code possible | 3.5/5 — Bon dans l'écosystème Microsoft |
| **Module HTTP/API personnalisé** | Oui (HTTP module complet) | Oui (Webhooks, mais moins flexible) | Oui (HTTP Request, excellent) | Oui (HTTP connector) |
| **Gestion des erreurs** | Excellente (routes d'erreur, retry, break) | Basique (retry automatique) | Très bonne (try/catch, custom) | Correcte (gestion de conditions) |
| **Hébergement** | Cloud uniquement | Cloud uniquement | Cloud OU Self-hosted (Docker) | Cloud (Azure) |
| **Support IA natif** | Module OpenAI intégré, HTTP pour les autres | Module ChatGPT et IA intégrés | Modules IA via communauté + HTTP | Intégration Azure OpenAI, Copilot |
| **Communauté et ressources** | Communauté active, Make Academy, forum | Très large communauté, blog abondant | Communauté open-source, forum, GitHub | Documentation Microsoft étendue |
| **Idéal pour...** | PME, freelances, workflows complexes visuels | Débutants, automatisations simples et rapides | Développeurs, entreprises voulant le self-hosted | Entreprises utilisant Microsoft 365 |

---

## Détail des forces et faiblesses

### Make (ex-Integromat)

**Forces**
- Interface visuelle en organigramme : on voit le flux de données
- Plan gratuit généreux (1 000 opérations)
- Gestion avancée des erreurs (routes d'erreur, rollback)
- Excellent module HTTP pour les appels API personnalisés
- Routes et filtres pour la logique conditionnelle complexe
- Bon rapport qualité/prix sur les plans payants

**Faiblesses**
- Moins d'intégrations natives que Zapier
- Peut être déroutant au début pour les non-visuels
- Documentation parfois en anglais uniquement
- Pas de self-hosting

---

### Zapier

**Forces**
- Le plus simple à prendre en main
- Le plus grand catalogue d'intégrations (~7 000+)
- Interface pas-à-pas très guidée
- Énormément de tutoriels et ressources en ligne
- "Zaps" pré-faits pour des cas d'usage courants

**Faiblesses**
- Plan gratuit très limité (100 tâches seulement)
- Plans payants plus chers que la concurrence
- Logique conditionnelle limitée (pas de vraies branches visuelles)
- Moins flexible pour les workflows complexes
- Module HTTP moins puissant que Make

---

### n8n

**Forces**
- Open source et self-hosted possible (contrôle total des données)
- Gratuit sans limite en self-hosted
- Très flexible : possibilité d'ajouter du code JavaScript
- Interface visuelle similaire à Make
- Idéal pour les préoccupations de confidentialité (données restent chez vous)

**Faiblesses**
- Nécessite des compétences techniques pour l'installation self-hosted
- Moins d'intégrations natives
- Communauté plus petite (mais active)
- Courbe d'apprentissage plus raide
- Support officiel limité sur le plan gratuit

---

### Power Automate (Microsoft)

**Forces**
- Intégration native parfaite avec Microsoft 365 (Outlook, Teams, SharePoint, Excel)
- Inclus dans de nombreux abonnements Microsoft 365
- Accès à Azure OpenAI pour l'IA d'entreprise
- RPA (Robotic Process Automation) inclus pour automatiser des applications desktop
- Conformité et sécurité de niveau entreprise

**Faiblesses**
- Principalement pertinent dans l'écosystème Microsoft
- Interface moins intuitive que Make ou Zapier
- Moins flexible pour les intégrations hors-Microsoft
- Courbe d'apprentissage si pas familier avec Microsoft
- Plans de tarification complexes

---

## Notre recommandation pour la formation

> **Nous utilisons Make dans cette formation pour les raisons suivantes :**
>
> 1. **Interface visuelle intuitive** : l'approche organigramme permet de comprendre visuellement le flux de données, ce qui est essentiel pour des apprenants débutants en automatisation
> 2. **Plan gratuit généreux** : 1 000 opérations/mois permettent de faire tous les exercices de la formation sans frais
> 3. **Excellent support API** : le module HTTP de Make est l'un des plus complets, crucial pour nos scénarios avec les APIs d'IA
> 4. **Bon équilibre simplicité/puissance** : assez simple pour débuter, assez puissant pour des cas réels en entreprise
> 5. **Communauté active et francophone** : ressources d'aide disponibles en français
> 6. **Transférable** : les concepts appris sur Make (triggers, modules, mapping, routes) se retrouvent sur toutes les autres plateformes

---

## Guide de choix : quelle plateforme pour vous ?

Utilisez cet arbre de décision pour choisir la plateforme adaptée à votre contexte professionnel :

### Vous êtes débutant total en automatisation

**Recommandation : Make**

- L'interface visuelle vous aide à comprendre ce qui se passe
- Le plan gratuit est suffisant pour démarrer
- Vous pourrez évoluer vers des scénarios complexes sans changer de plateforme

### Vous voulez le plus simple possible, pour des automatisations basiques

**Recommandation : Zapier**

- Si vos besoins sont "Quand X se passe, faire Y" sans logique complexe
- Si vous avez besoin d'une intégration très spécifique (Zapier a le plus grand catalogue)
- Si vous êtes prêt à payer un plan pour dépasser les 100 tâches mensuelles

### Vous êtes technique et voulez le contrôle total

**Recommandation : n8n**

- Si vous savez installer un conteneur Docker ou un serveur
- Si la confidentialité des données est critique (hébergement chez vous)
- Si vous voulez ajouter du code personnalisé dans vos workflows
- Si vous ne voulez pas de limites d'opérations

### Vous êtes dans l'écosystème Microsoft 365

**Recommandation : Power Automate**

- Si votre entreprise utilise Outlook, Teams, SharePoint, Excel Online
- Si vous avez déjà un abonnement Microsoft 365 Business
- Si la conformité et la sécurité d'entreprise sont prioritaires
- Si vous voulez automatiser des applications desktop (RPA)

### Tableau de décision rapide

| Votre situation | Plateforme recommandée |
|----------------|----------------------|
| Formation et apprentissage | Make |
| Freelance / TPE, automatisations variées | Make |
| PME, automatisations simples et rapides | Zapier |
| Startup tech, données sensibles | n8n (self-hosted) |
| Grande entreprise Microsoft | Power Automate |
| Besoin du plus grand choix d'apps | Zapier |
| Workflows complexes avec logique avancée | Make ou n8n |
| Budget zéro, usage intensif | n8n (self-hosted) |

---

> **A retenir** : il n'y a pas de "meilleure" plateforme universelle. Le choix dépend de votre contexte, de vos compétences techniques et de votre écosystème d'outils. Les concepts fondamentaux (triggers, actions, conditions, APIs) sont les mêmes partout : ce que vous apprenez sur Make est transférable aux autres plateformes.

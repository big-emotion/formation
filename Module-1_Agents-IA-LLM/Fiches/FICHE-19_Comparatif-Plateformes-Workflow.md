# FICHE-19 — Tableau Comparatif des Plateformes de Workflow

> **Formation IA pour les Métiers du Tertiaire**
> Fiche de référence — Session 5 (1 page)

---

## Les 4 plateformes principales

| Critère | **Make** (ex-Integromat) | **Zapier** | **n8n** | **Power Automate** |
|---------|------------------------|-----------|---------|-------------------|
| **Pays** | 🇨🇿 Tchéquie | 🇺🇸 États-Unis | 🇩🇪 Allemagne | 🇺🇸 États-Unis (Microsoft) |
| **Interface** | Visuelle (glisser-déposer) | Linéaire (étape par étape) | Visuelle (glisser-déposer) | Linéaire + visuelle |
| **Facilité** | ⭐⭐⭐⭐ Intermédiaire | ⭐⭐⭐⭐⭐ Très facile | ⭐⭐⭐ Technique | ⭐⭐⭐⭐ Facile |
| **Plan gratuit** | ✅ 1 000 opérations/mois | ✅ 100 tâches/mois | ✅ Illimité (auto-hébergé) | ✅ Limité (avec licence M365) |
| **Prix (entrée)** | 9€/mois | 19,99$/mois | Gratuit (community) | Inclus dans M365 ou 15$/mois |
| **Intégrations** | ~1 500 apps | ~7 000 apps | ~400+ apps | ~1 000+ apps (surtout Microsoft) |
| **IA intégrée** | ✅ Modules OpenAI, Claude | ✅ Modules IA natifs | ✅ Modules IA | ✅ Copilot + Azure AI |
| **Module HTTP** | ✅ Puissant | ✅ Basique | ✅ Très puissant | ✅ Oui |
| **Open source** | ❌ | ❌ | ✅ | ❌ |

---

## Quand choisir quoi ?

| Votre situation | Plateforme recommandée | Pourquoi |
|----------------|----------------------|----------|
| Je débute, je veux un outil simple | **Zapier** | Le plus intuitif, énorme catalogue |
| Je veux un bon rapport puissance/prix | **Make** | Visuel, puissant, plan gratuit généreux |
| Mon entreprise est sur Microsoft 365 | **Power Automate** | Intégration native Teams, Outlook, SharePoint |
| Je veux du contrôle total et c'est gratuit | **n8n** | Open-source, auto-hébergeable, pas de limite |
| Je veux intégrer des appels API IA | **Make** ou **n8n** | Modules HTTP puissants et flexibles |
| J'ai besoin de +5 000 intégrations | **Zapier** | Le plus grand catalogue d'apps |

---

## Vocabulaire commun

| Terme | Make | Zapier | n8n | Power Automate |
|-------|------|--------|-----|----------------|
| Un workflow | **Scénario** | **Zap** | **Workflow** | **Flow** |
| L'événement déclencheur | **Trigger** | **Trigger** | **Trigger** | **Trigger** |
| Une étape d'action | **Module** | **Action** | **Node** | **Action** |
| Exécuter le workflow | **Run** | **Run** | **Execute** | **Run** |
| Un branchement conditionnel | **Router** | **Path** | **If** | **Condition** |

---

## Notre choix pour la formation : Make

**Pourquoi Make ?**
- Interface visuelle claire (on "voit" le workflow)
- Plan gratuit suffisant pour apprendre (1 000 opérations/mois)
- Module HTTP puissant pour appeler les APIs des LLM
- Bon équilibre simplicité / puissance
- Grande communauté et tutoriels en français

> Les compétences acquises sur Make sont facilement transférables vers Zapier, n8n ou Power Automate. Le principe est le même partout : **Déclencheur → Actions → Résultat**.

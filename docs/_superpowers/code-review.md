---
layout: page
title: "Code Review automatisé"
subTitle: "Super-pouvoir ans-review"
description: "Revue automatique des pull requests avec des agents spécialisés et un score de confiance pour filtrer les faux positifs."
icon: "🔍"
category: "qualité"
version: "0.1.0"
author: "DevTools Team — ANS"
install_name: "ans-review"
---

<div class="superpower-meta mb-4">
  <span class="badge rounded-pill bg-primary">qualité</span>
  <span class="badge rounded-pill bg-light text-dark">v0.1.0</span>
  <span class="badge rounded-pill bg-light text-dark">ans-review</span>
</div>

## Vue d'ensemble

Le plugin **Code Review automatisé** analyse vos pull requests en parallèle via plusieurs agents spécialisés indépendants. Un score de confiance (0–100) filtre les faux positifs — seuls les problèmes à 80+ sont remontés.

## Installation

```bash
/plugin install ans-review@claude-plugins-ans-official
```

## Commande

### `/code-review`

Lance la revue automatique d'une pull request ouverte.

**Ce que ça fait :**

1. Vérifie si la revue est nécessaire (ignore les PR fermées, en brouillon, triviales ou déjà revues)
2. Collecte les fichiers `CLAUDE.md` du dépôt pour les règles projet
3. Résume les changements de la PR
4. Lance **4 agents en parallèle** :
   - Agents 1 & 2 — Conformité aux règles `CLAUDE.md`
   - Agent 3 — Détection de bugs dans les changements
   - Agent 4 — Analyse du contexte via `git blame`
5. Attribue un score de confiance 0–100 à chaque problème trouvé
6. Filtre les problèmes en dessous du seuil de 80
7. Poste un commentaire de revue sur GitHub avec uniquement les problèmes à haute confiance

**Exemple :**

```bash
# Sur une branche de PR
/code-review

# Claude va :
# — Lancer 4 agents en parallèle
# — Scorer chaque problème
# — Poster un commentaire avec les problèmes ≥ 80
# — Ne rien poster s'il n'y a aucun problème à haute confiance
```

## Format du commentaire de revue

```markdown
## Code review

Found 3 issues:

1. Missing error handling for OAuth callback
   (CLAUDE.md says "Always handle OAuth errors")

   https://github.com/owner/repo/blob/abc123.../src/auth.ts#L67-L72

2. Memory leak: OAuth state not cleaned up
   (bug due to missing cleanup in finally block)

   https://github.com/owner/repo/blob/abc123.../src/auth.ts#L88-L95
```

## Scores de confiance

| Score | Signification |
|-------|---------------|
| 0 | Faux positif probable |
| 25 | Incertain |
| 50 | Modérément probable |
| 75 | Très probable |
| **80+** | **Seuil de publication** |
| 100 | Certitude absolue |

## Bonnes pratiques

- Maintenez des fichiers `CLAUDE.md` précis pour de meilleures revues de conformité
- Faites confiance au seuil 80+ — les faux positifs sont filtrés
- Lancez sur toutes les PR non triviales
- Mettez à jour `CLAUDE.md` en fonction des patterns récurrents détectés

## Prérequis

- Dépôt Git avec intégration GitHub
- GitHub CLI (`gh`) installé et authentifié
- Fichiers `CLAUDE.md` (optionnel mais recommandé)

## Architecture technique

```
4 agents parallèles
├── Agent 1 — Conformité CLAUDE.md (redondance)
├── Agent 2 — Conformité CLAUDE.md (redondance)
├── Agent 3 — Détection de bugs dans les changements
└── Agent 4 — Analyse git blame / historique
         ↓
Score de confiance 0–100 par problème
         ↓
Filtre seuil ≥ 80
         ↓
Commentaire GitHub
```

<style>
.superpower-meta { display: flex; gap: 0.5rem; flex-wrap: wrap; }
table { width: 100%; border-collapse: collapse; margin: 1rem 0; }
th, td { padding: 0.5rem 0.75rem; border: 1px solid #dee2e6; text-align: left; }
th { background: #f8f9fa; font-weight: 600; }
</style>

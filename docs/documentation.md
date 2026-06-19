---
layout: page
title: "Documentation"
subTitle: "ANS Claude Marketplace"
permalink: /docs/
---

## Qu'est-ce qu'un super-pouvoir ?

Un **super-pouvoir** est un plugin Claude Code publié par l'ANS. Il ajoute des commandes (`/ma-commande`), des agents ou des compétences directement dans votre session Claude Code.

## Structure d'un plugin

```
mon-plugin/
├── .claude-plugin/
│   └── plugin.json      # Métadonnées (obligatoire)
├── .mcp.json            # Serveur MCP (optionnel)
├── commands/            # Commandes slash (optionnel)
├── agents/              # Définitions d'agents (optionnel)
├── skills/              # Compétences (optionnel)
└── README.md
```

## Installer un plugin

```bash
# Via le nom du plugin
/plugin install <nom>@claude-plugins-ans-official

# Via la découverte interactive
/plugin > Discover
```

## Contribuer

Les contributions sont les bienvenues. Consultez le [dépôt GitHub](https://github.com/ansforge/ia-claude-marketplace) pour les standards de qualité et la procédure de soumission.

## Ressources

- [Documentation Claude Code](https://code.claude.com/docs/en/plugins)
- [Dépôt GitHub ANS Marketplace](https://github.com/ansforge/ia-claude-marketplace)
- [DSFR — Design System de l'État](https://www.systeme-de-design.gouv.fr/)

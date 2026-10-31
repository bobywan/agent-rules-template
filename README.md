# agent-rules-template

Règles partagées pour les projets front-end React, Next.js, Tailwind CSS et TypeScript. Ce dépôt est un sous-module Git : une mise à jour ici se propage aux projets qui le référencent.

Cursor, Claude Code (v2.1.277 et après) et Codex lisent `AGENTS.md` à la racine du projet. Le fichier toujours chargé reste court. Le détail est dans `agents/` et n'est lu qu'au moment de créer un composant, un store ou un schéma.

## Rôles

| Fichier | Rôle |
| --- | --- |
| `AGENTS.md` | Invariants et choix du playbook |
| `agents/01-architect.md` | Découpage, sans code |
| `agents/02-frontend-expert.md` | Interface, accessibilité |
| `agents/03-state-and-logic.md` | Types, état, Zod |
| `agents/04-code-reviewer.md` | Bloquants à corriger sur place |

## Intégrer

Le sous-module n'est pas lu tant qu'un lien à la racine du projet consommateur ne l'expose pas. Depuis cette racine :

```bash
git submodule add git@github.com:bobywan/agent-rules-template.git agent-rules
ln -s agent-rules/AGENTS.md AGENTS.md
```

Le premier commit du projet consommateur inclut `.gitmodules`, `agent-rules` et `AGENTS.md`.

N'ajoute pas de `.cursorrules`, de `CLAUDE.md` ni de règle toujours active qui recopient `AGENTS.md`. L'outil chargerait le même texte deux fois.

## Mettre à jour

```bash
git submodule update --remote agent-rules
```

Le lien `AGENTS.md` reste valable. Committe ensuite le nouveau SHA du sous-module dans le projet consommateur.

## Repli Claude

Claude Code lit `AGENTS.md` tant qu'aucun `CLAUDE.md` n'existe dans le projet ni dans un dossier parent. Ajoute un `CLAUDE.md` d'une ligne seulement dans deux cas : un `CLAUDE.md` existe déjà plus haut dans l'arborescence, ou Claude Code est antérieur à la v2.1.277.

```markdown
@AGENTS.md
```

Sans ces cas, ce fichier ferait ignorer `AGENTS.md`, ou charger les deux.

## Structure

```text
agent-rules-template/
├── AGENTS.md
├── agents/
│   ├── 01-architect.md
│   ├── 02-frontend-expert.md
│   ├── 03-state-and-logic.md
│   └── 04-code-reviewer.md
├── LICENSE
└── README.md
```

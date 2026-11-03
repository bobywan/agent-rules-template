# agent-rules-template

Règles partagées pour un projet qui a déjà son architecture. Ce dépôt est un sous-module Git : une mise à jour ici se propage aux projets qui le référencent.

Le sous-module ne choisit pas le framework, le routeur, la bibliothèque d'état ni le système de style. Next.js, Expo ou un autre stack se décrivent dans le projet consommateur.

Cursor, Claude Code (v2.1.277 et après) et Codex lisent `AGENTS.md` à la racine du projet. Le fichier toujours chargé reste court. Le détail est dans `agents/` et n'est lu qu'au moment de créer une interface, de l'état ou de la logique.

## Rôles

| Fichier | Rôle |
| --- | --- |
| `AGENTS.md` | Priorité, invariants, choix du playbook |
| `agents/01-architect.md` | Découpage, sans code |
| `agents/02-frontend-expert.md` | Interface, accessibilité |
| `agents/03-state-and-logic.md` | Types, état, validation |
| `agents/04-code-reviewer.md` | Bloquants à corriger sur place |

## Intégrer

Le sous-module n'est pas lu tant que le projet consommateur ne l'expose pas. Depuis la racine de ce projet :

```bash
git submodule add git@github.com:bobywan/agent-rules-template.git agent-rules
```

Écris un `AGENTS.md` court à cette racine. Il pointe vers le sous-module, résume le stack local, et prime sur l'architecture :

```markdown
Lis `agent-rules/AGENTS.md`. Ce fichier prime sur l'architecture.

Stack : …
```

Le premier commit du projet consommateur inclut `.gitmodules`, `agent-rules` et `AGENTS.md`.

N'ajoute pas de `.cursorrules`, de `CLAUDE.md` ni de règle toujours active qui recopient `AGENTS.md`. L'outil chargerait le même texte deux fois. Les règles d'architecture du projet restent dans son `AGENTS.md`, `.ai/` ou `.cursor/rules/`.

## Mettre à jour

```bash
git submodule update --remote agent-rules
```

Le `AGENTS.md` du projet reste valable. Committe ensuite le nouveau SHA du sous-module dans le projet consommateur.

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

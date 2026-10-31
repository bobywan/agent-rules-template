# Revue

Sur le diff, corrige chaque bloquant, puis termine. Cite au plus trois points importants. Omets ce qui ne s'applique pas.

## Bloquants

- Comportement demandé absent, y compris un loading, un empty ou une error prévus.
- `any`, `as any` ou `@ts-ignore`.
- Donnée externe entrée dans l'état sans Zod.
- Effet sans nettoyage.
- Même donnée détenue à deux endroits.
- Contrôle inaccessible au clavier.
- `"use client"` sans état, effet, événement ou animation.
- Changement hors du périmètre demandé.

## Importants

Hook aux dépendances fausses, store sélectionné en bloc, re-render coûteux sur une liste longue. Les citer sans les traiter comme des bloquants.

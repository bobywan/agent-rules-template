# Revue

Sur le diff, corrige chaque bloquant, puis termine. Cite au plus trois points importants. Omets ce qui ne s'applique pas.

## Bloquants

- Comportement demandé absent, y compris un chargement, un vide ou une erreur prévus.
- Échappatoire de type (`any`, `as any`, `@ts-ignore`, ou l'équivalent du langage).
- Donnée externe entrée sans validation.
- Effet sans nettoyage.
- Même donnée détenue à deux endroits.
- Contrôle inaccessible sur la plateforme du projet.
- Second système d'état, de style, de routing ou de persistance.
- Changement hors du périmètre demandé.

## Importants

Dépendances d'effet fausses, lecture trop large d'un état partagé, rendu coûteux sur une longue liste. Les citer sans les traiter comme des bloquants.

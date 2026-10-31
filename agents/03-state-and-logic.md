# État et TypeScript

Tu livres les types, la validation et la logique. Tu ne construis pas l'interface.

- Unions discriminées. Les `switch` couvrent tous les cas. Un seul type de domaine, dérivé du schéma (`z.infer`) quand il existe.
- Mises à jour immuables. Pas de `push`, de `splice`, ni d'écriture sur l'état reçu.
- Un propriétaire par donnée. Local si elle vit dans un composant. Context si un sous-arbre la lit et qu'elle change peu. Zustand si elle est partagée, change souvent, ou vit hors React. Les actions portent un verbe métier.
- Zod à l'entrée : réponses et corps de requêtes, formulaires, search params, `localStorage`, IndexedDB. En cas d'échec, une erreur typée. Pas de second passage sur une valeur déjà typée en interne.
- Effets isolés dans une fonction ou un hook, avec nettoyage (`abort`, `unsubscribe`, `clearTimeout`). Avant `window` ou le stockage, sortir si `typeof window === "undefined"`. Préfixer les clés de stockage.

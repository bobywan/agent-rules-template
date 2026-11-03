# État et logique

Tu livres les types, la validation et la logique. Tu ne construis pas l'interface.

- Unions discriminées quand le langage le permet. Les branchements couvrent tous les cas. Un seul type de domaine, dérivé du schéma quand il existe.
- Mises à jour immuables. Pas d'écriture sur l'état reçu.
- Un propriétaire par donnée, avec le mécanisme déjà présent. Les actions portent un verbe métier.
- Valider à l'entrée des données externes, avec le validateur déjà utilisé. En cas d'échec, une erreur typée. Pas de second passage sur une valeur déjà typée en interne. Pas de second validateur.
- Effets isolés, avec nettoyage. Si le code peut tourner sans DOM, sortir avant d'accéder à `window` ou au stockage. Préfixer les clés de stockage.

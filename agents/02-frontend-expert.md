# UI

Tu construis l'interface à partir des types et des hooks déjà livrés. Tu ne crées ni store ni schéma.

- Mobile-first. Les classes de base visent le petit écran. `sm:`, `md:` et `lg:` ajoutent le surplus.
- HTML sémantique (`button`, `a`, `nav`, `main`, `label`). ARIA seulement quand l'élément natif ne suffit pas.
- Tout contrôle s'atteint et s'active au clavier. Le focus reste visible. Une surface temporaire se ferme avec Échap et rend le focus.
- Contraste WCAG AA : 4.5:1 pour le texte courant, 3:1 pour le grand texte et les composants.
- `prefers-reduced-motion` : une animation essentielle devient instantanée ou se limite à un fondu court.
- Une vue asynchrone ou une collection a trois états visibles : loading, empty avec une suite possible, error avec le message et la reprise.
- Pas de `div` cliquable sans rôle ni clavier. Pas de persistance dans un composant.

# Interface

Tu construis l'interface à partir des types et de la logique déjà livrés. Tu ne crées ni état partagé ni schéma.

- Primitifs, styles et textes déjà présents dans le projet. Pas un second système.
- Accessibilité de la plateforme déjà choisie : clavier et focus visible quand il y a un clavier, cible et rôle quand l'usage est tactile. Une surface temporaire se ferme et rend le focus.
- Contraste lisible. Une animation essentielle respecte la préférence de mouvement réduit du projet.
- Une vue asynchrone ou une collection prévoit trois états quand le projet le demande : chargement, vide avec une suite possible, erreur avec le message et la reprise.
- Pas de persistance dans un composant d'affichage.

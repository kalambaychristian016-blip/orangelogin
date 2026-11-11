# Orange Login — export source

Cette archive contient le code source de l’application Orange Login : frontend React, serveur tRPC/Express, schéma Drizzle, migrations, tests et configuration du projet.

## Installation

```bash
pnpm install
pnpm run check
pnpm test
pnpm run build
pnpm start
```

## Variables d’environnement à configurer sur l’hébergeur

Ne mettez jamais ces valeurs dans le dépôt ou dans l’archive. Configurez-les dans le gestionnaire de secrets de l’hébergeur :

- `DATABASE_URL`
- `JWT_SECRET`
- `VITE_APP_ID`
- `OAUTH_SERVER_URL`
- `OWNER_OPEN_ID`
- `BUILT_IN_FORGE_API_URL`
- `BUILT_IN_FORGE_API_KEY`
- `ADMIN_SECOND_PIN_HASH`

Définir également `NODE_ENV=production` en production.

## Base de données

Le projet utilise MySQL/TiDB et Drizzle ORM. Vérifiez la chaîne `DATABASE_URL`, puis utilisez les migrations présentes dans `drizzle/migrations/` selon la procédure de l’hébergeur. Faites une sauvegarde de la base avant toute migration.

## Stockage des pièces jointes

Les pièces d’identité et autres fichiers doivent rester dans un stockage objet sécurisé. Configurez les identifiants de stockage via les variables secrètes propres à l’hébergeur et ne stockez pas de fichiers sensibles dans le dépôt Git.

## Important avant publication

Effectuez un audit de conformité et de confidentialité avant de rendre l’application publique : données personnelles, pièces d’identité, paiements, contrôle d’accès administrateur, durée de conservation et suppression des données. Cette archive ne contient pas les dépendances `node_modules`, les artefacts `dist`, les logs, le dépôt `.git` ni les fichiers d’environnement.

# Sika Skills — Coach Objectif 1 Million

Application web progressive (PWA) conçue pour être publiée avec **GitHub Pages**.

## Mise en ligne avec GitHub

1. Sur GitHub, crée un nouveau dépôt public nommé `sika-skills-coach` (ou le nom de ton choix).
2. Dans le dépôt, choisis **Add file → Upload files**.
3. Envoie tous les éléments de ce dossier : `index.html`, `manifest.webmanifest`, `sw.js`, `icons/` et `README.md`. Il faut garder exactement cette organisation.
4. Ouvre **Settings → Pages**.
5. Dans **Build and deployment**, choisis **Deploy from a branch**, branche `main`, dossier `/ (root)`, puis **Save**.
6. Attends la publication et ouvre l’adresse GitHub Pages indiquée dans cette page.
7. Sur Android avec Chrome : ouvre l’adresse HTTPS, menu ⋮, puis **Installer l’application** ou **Ajouter à l’écran d’accueil**.

## Base de données en ligne (préparation Supabase)

La connexion Supabase, l’inscription/connexion par e-mail et la synchronisation des données sont intégrées. Le schéma SQL et les étapes de configuration Auth figurent dans `supabase/schema.sql` et `DATABASE_SUPABASE.md`. La synchronisation réelle doit être validée après publication sur GitHub Pages. Ne publie jamais une clé `secret` ou `service_role`.

## Sauvegarde des progrès

Les données sont conservées dans le navigateur de l’appareil (localStorage) et copiées dans une seconde sauvegarde locale IndexedDB. Le bouton **Sauvegarder mes progrès** télécharge aussi un fichier JSON ; garde ce fichier dans un endroit sûr (Drive ou ordinateur). Le bouton **Restaurer** permet de le réimporter.

**Important :** GitHub Pages héberge les fichiers de l’application, mais ne synchronise pas les données personnelles entre plusieurs téléphones. Pour une synchronisation cloud avec compte utilisateur, il faudra ajouter un service de base de données (par exemple Supabase) et configurer ses clés publiques dans le projet. Ne publie jamais de clé secrète dans GitHub.

## Dates tarifaires intégrées

- Pourquoi Mes Clients Ne Commandent Pas ? : 2 900 FCFA jusqu’au 5 novembre 2026 inclus, puis 3 900 FCFA à partir du 6 novembre.
- Calculer le Vrai Bénéfice : 1 900 FCFA jusqu’au 15 novembre 2026 inclus, puis 2 900 FCFA à partir du 16 novembre.

Vérifie toujours que les prix sur Chariow correspondent à ces dates avant de publier.

## Limites actuelles

L’application aide à préparer, copier et partager les contenus ; elle ne publie pas automatiquement sur WhatsApp, Facebook, TikTok ou Instagram. Les objectifs hebdomadaires sont des cibles de travail, pas des revenus garantis.

# Sika Coach — synchronisation Supabase

Cette version de Sika Coach est configurée avec le Project URL et la clé publishable du projet Supabase de Sika Skills. Le client Supabase est chargé depuis jsDelivr.

## Avant le premier compte

1. Dans Supabase, vérifie que `supabase/schema.sql` a été exécuté avec succès dans SQL Editor.
2. Dans **Authentication → URL Configuration**, configure le **Site URL** sur `https://sikaskills.github.io/sika-skills-coach/` et ajoute cette même adresse dans les Redirect URLs autorisées.
3. Dans **Authentication → Providers → Email**, conserve le fournisseur Email activé. Si la confirmation d'e-mail est activée, l'utilisateur doit cliquer sur le lien reçu avant de se connecter.
4. Publie le contenu du dossier `sika-skills-pwa` dans le dépôt GitHub Pages qui sert l'application.

## Utilisation

- Dans l'application, saisis ton adresse e-mail et un mot de passe d'au moins 6 caractères, puis choisis **Créer un compte**.
- Confirme l'adresse e-mail si Supabase le demande, puis connecte-toi.
- Les modifications de l'état (cases cochées, notes, ventes et objectif) sont conservées localement et envoyées à `public.coach_backups` après connexion.
- Sur un autre téléphone, ouvre la même adresse de l'application et connecte-toi avec le même compte. Si une sauvegarde existe, l'application propose de récupérer la version en ligne ou de remplacer la sauvegarde en ligne par les données locales.

## Sécurité et limites

La clé `sb_publishable_...` est une clé publique prévue pour le navigateur. La table utilise RLS et les politiques du schéma limitent chaque utilisateur à sa propre ligne via `auth.uid() = user_id`. Ne publie jamais une clé `secret` ou `service_role`.

La synchronisation doit encore être testée dans le navigateur après déploiement : création de compte, connexion, sauvegarde d'une modification, puis récupération sur un second appareil. En cas d'échec, vérifie l'URL du site, le SQL, l'accès réseau et le message affiché sous le formulaire de connexion.

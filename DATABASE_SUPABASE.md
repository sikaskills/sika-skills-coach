# Ajouter une base de données en ligne sécurisée à Sika Skills

## Ce qui est inclus dans ce ZIP
- `supabase/schema.sql` : table de sauvegarde et règles de sécurité Row Level Security (RLS).
- `supabase/config.example.js` : exemple des deux paramètres publics nécessaires au client Supabase.
- Ce guide : création du projet et étapes de raccordement.

**Important : la base en ligne n'est pas encore créée ni reliée à l'application.** Ce dossier prépare le travail, mais ne crée pas de compte Supabase et ne déclenche aucune synchronisation. La PWA actuelle continue à enregistrer les données sur l'appareil (localStorage + IndexedDB) et à proposer l'export/import JSON.

## 1. Créer le projet Supabase
1. Va sur https://supabase.com/ et crée ton compte.
2. Crée un nouveau projet, choisis un mot de passe fort pour la base et conserve-le en lieu sûr.
3. Dans **SQL Editor**, ouvre une nouvelle requête, copie le contenu de `supabase/schema.sql`, puis exécute-le.
4. Dans **Authentication**, active la méthode de connexion souhaitée (par exemple e-mail avec confirmation).
5. Dans **Project Settings > API**, relève le Project URL et la clé publishable (ou l'ancienne clé `anon`).

## 2. Règles de sécurité essentielles
- N'insère jamais la clé `service_role` dans `index.html`, JavaScript, GitHub ou un dépôt public.
- Seule la clé publishable/anon peut être utilisée côté navigateur, avec les politiques RLS activées.
- Le SQL fourni lie chaque sauvegarde à `auth.uid()` : un compte ne peut consulter/modifier que sa propre ligne.
- Ne désactive pas RLS pour « faire fonctionner » l'application.
- Protège ton mot de passe et active la confirmation d'e-mail.

## 3. Raccordement à la PWA
Le raccordement fonctionnel nécessite encore une modification de `index.html` : ajouter le client Supabase, un écran d'inscription/connexion, puis les opérations de lecture/écriture dans `coach_backups` après authentification. Le fichier `supabase/config.example.js` est un modèle à compléter, pas une configuration active. Il ne faut pas coller de mot de passe de base ni de clé `service_role` dans ce fichier.

Pour terminer le raccordement, il faudra disposer du Project URL et de la clé publishable/anon de ton propre projet. Ces deux valeurs ne suffisent pas à elles seules à ouvrir l'accès aux données : l'utilisateur doit aussi être authentifié et les règles RLS doivent rester actives.

## 4. En attendant
Utilise régulièrement le bouton de sauvegarde de la PWA et conserve le fichier JSON exporté dans un endroit sûr. GitHub Pages héberge l'application, mais n'est pas la base de données et ne synchronise pas les progrès entre appareils.

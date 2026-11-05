# Correctif Sika Coach — 4 novembre 2026

Ce paquet est une version corrigée du projet fourni. Il conserve l'identité visuelle, les onglets, les contenus, les ventes, les notes et les fichiers d'installation.

## Corrections apportées
- Correction de la structure des tâches des 14 premiers jours : chaque journée recevait auparavant un tableau de champs comme s'il s'agissait d'une liste de tâches. Cela provoquait des titres réduits à une lettre, des valeurs `undefined` et des durées invalides (`NaN h`).
- Normalisation défensive des tâches, sous-tâches et durées avant affichage.
- Calcul du temps prévu avec une valeur de secours si une durée est absente.
- Affichage du texte en thème clair à contraste stable, y compris lorsque le téléphone est réglé en mode sombre.
- Chronomètre recalculé à partir de l'heure réelle, avec démarrage, pause et remise à zéro.
- Mise à jour du cache du service worker pour forcer le chargement de cette version corrigée.
- Progression des semaines rafraîchie après modification d'une case.

## Mise en ligne sur GitHub Pages
1. Télécharge et décompresse ce ZIP.
2. Ouvre le dépôt GitHub qui héberge Sika Coach.
3. Ouvre le dossier `sika-skills-pwa` du dépôt (ou le dossier publié par GitHub Pages si son nom diffère).
4. Remplace les fichiers existants par le contenu du dossier `sika-coach-correctif` décompressé : `index.html`, `sw.js`, `manifest.webmanifest`, `README.md`, `DATABASE_SUPABASE.md`, le dossier `supabase` et le dossier `icons`.
5. Valide les changements (Commit changes).
6. Attends la publication GitHub Pages, puis recharge le site.

Important : ne supprime pas le dossier `icons` ni le dossier `supabase`. Ne téléverse pas le ZIP lui-même à la place des fichiers décompressés.

## Après publication
Sur le téléphone Android :
1. Ferme complètement l'application ou l'onglet Sika Coach.
2. Ouvre le site dans Chrome et actualise la page.
3. Si l'ancienne version reste affichée, ouvre les paramètres du site dans Chrome et efface les données/cache du site, puis recharge.
4. Vérifie Ma journée, Programme, les cases à cocher et le chronomètre.

## Sauvegarde des données
Les progrès, ventes et notes sont conservés dans le stockage local du navigateur. Avant de remplacer les fichiers, utilise « Sauvegarder mes progrès » dans l'application pour télécharger une sauvegarde JSON. Ne supprime pas les données du site sans avoir conservé ce fichier.

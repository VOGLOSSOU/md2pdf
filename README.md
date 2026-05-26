# md2pdf

Convertisseur Markdown vers PDF, entièrement côté client. Aucun serveur, aucune installation, aucune donnée transmise.

## Utilisation

Ouvre `index.html` dans un navigateur, c'est tout.

1. Glisse un fichier `.md` dans la zone de dépôt, ou clique pour le sélectionner.
2. Clique sur **Enregistrer en PDF**.
3. Une nouvelle fenêtre s'ouvre avec le document rendu.
4. La boîte d'impression s'ouvre automatiquement — sélectionne **"Enregistrer en PDF"** comme destination et choisis où sauvegarder.

## Fonctionnement

Le fichier Markdown est lu localement par le navigateur, converti en HTML via [marked.js](https://marked.js.org/), puis rendu dans une nouvelle fenêtre. La conversion en PDF est assurée par le moteur d'impression natif du navigateur. Rien ne quitte ta machine.

Cette approche produit un meilleur rendu que les solutions basées sur canvas (html2pdf, html2canvas) qui peinent avec les fichiers locaux.

## Rendu PDF

Le document est formaté pour être lisible sur mobile et desktop :

- Hiérarchie typographique claire (h1 à h6)
- Blocs de code avec fond gris et police monospace
- Tableaux avec bordures
- Blockquotes avec barre latérale
- Liens, images, listes, séparateurs

## Dépendances

Bundlées localement dans `vendor/`, aucune connexion internet requise :

- `marked` — parsing Markdown vers HTML

## Limitations

- La conversion passe par la boîte d'impression du navigateur — il faut sélectionner "Enregistrer en PDF" manuellement.
- Si le navigateur bloque la popup, autoriser les popups pour les fichiers locaux dans les paramètres.
- Les images externes peuvent ne pas s'afficher si elles ne sont pas accessibles localement.

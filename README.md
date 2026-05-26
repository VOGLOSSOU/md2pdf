# md2pdf

Convertisseur Markdown vers PDF, entièrement côté client. Aucun serveur, aucune installation, aucune donnée transmise.

## Utilisation

Ouvre `index.html` dans un navigateur, c'est tout.

1. Glisse un fichier `.md` dans la zone de dépôt, ou clique pour le sélectionner.
2. Clique sur **Télécharger le PDF**.
3. Le PDF se télécharge avec le même nom que le fichier source.

## Fonctionnement

Le fichier Markdown est lu localement par le navigateur, converti en HTML via [marked.js](https://marked.js.org/), puis rendu en PDF via [html2pdf.js](https://github.com/eKoopmans/html2pdf.js). Rien ne quitte ta machine.

## Rendu PDF

Le PDF est formaté pour être lisible sur mobile et desktop :

- Hiérarchie typographique claire (h1 à h6)
- Blocs de code avec fond gris et police monospace
- Tableaux avec bordures
- Blockquotes avec barre latérale
- Liens, images, listes, séparateurs

## Dépendances

Chargées depuis CDN, aucune installation requise :

- `marked` — parsing Markdown vers HTML
- `html2pdf.js` — rendu HTML vers PDF via html2canvas + jsPDF

## Limitations

- Les liens internes (ancres) ne sont pas cliquables dans le PDF.
- Les images externes peuvent ne pas s'afficher si le serveur bloque les requêtes cross-origin (CORS).
- Le rendu dépend du moteur de rendu du navigateur ; Chrome et Edge donnent les meilleurs résultats.

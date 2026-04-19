# CLAUD-DESIGN

Pour importer du design existant dans un projet, voici les formats pris en charge :

## Fichiers de design

- **Figma** — collez un lien Figma dans l'import ; les frames sont récupérées comme images de référence (pas comme code CSS, malheureusement Figma n'exporte pas un CSS utilisable)
Screenshots / images (PNG, JPG, SVG, WebP) — excellente référence visuelle
PDF — lus page par page
Napkin — croquis à main levée
Code

- **Codebase local** — via « Import codebase » (HTML, CSS, JSX/TSX, Vue, composants React, tokens, tailwind config, etc.). C'est la voie royale : j'accède aux composants réels, aux variables CSS, au thème, et je peux réutiliser exactement vos classes et tokens.
GitHub — collez une URL de repo/dossier/fichier ; je peux explorer l'arbre et importer les fichiers pertinents (tokens de thème, composants, feuilles de style globales).
Autre projet Claude Design — lien direct à un autre projet, je peux lire tous ses fichiers.
Documents

- **DOCX, Markdown, texte brut** — pour les PRD, briefs, specs.
PPTX — je peux lire les slides et les assets embarqués.
Le CSS importé reste totalement fonctionnel : variables CSS, grid/flex, @media, animations, custom properties, Tailwind — tout est préservé. Quand vous importez un codebase, je travaille dessus comme un dev : je lis le theme, je réutilise les composants existants, je respecte les tokens. La fidélité est pixel-parfaite si les sources sont là.

Le meilleur combo pour un résultat premium : codebase + screenshots de l'état actuel + brief. Si vous voulez passer l'un des 4 wireframes en hi-fi, dites-moi juste lequel et attachez ce que vous avez (ou je peux partir sans — ce sera simplement moins ancré dans votre identité existante).

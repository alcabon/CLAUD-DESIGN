# CLAUD-DESIGN

Pour importer du design existant dans un projet, voici les formats pris en charge :

## Fichiers de design

- **Figma** — collez un lien Figma dans l'import ; les frames sont récupérées comme images de référence (pas comme code CSS, malheureusement Figma n'exporte pas un CSS utilisable)

- **Screenshots / images (PNG, JPG, SVG, WebP)**— excellente référence visuelle

- **PDF** — lus page par page

- **Napkin** — croquis à main levée

## Code ##

- **Codebase local** — via « Import codebase » (HTML, CSS, JSX/TSX, Vue, composants React, tokens, tailwind config, etc.). C'est la voie royale : j'accède aux composants réels, aux variables CSS, au thème, et je peux réutiliser exactement vos classes et tokens.

- **GitHub** — collez une URL de repo/dossier/fichier ; je peux explorer l'arbre et importer les fichiers pertinents (tokens de thème, composants, feuilles de style globales).
Autre projet Claude Design — lien direct à un autre projet, je peux lire tous ses fichiers.
Documents

- **DOCX, Markdown, texte brut** — pour les PRD, briefs, specs.

- **PPTX** — je peux lire les slides et les assets embarqués.

Le CSS importé reste totalement fonctionnel : variables CSS, grid/flex, @media, animations, custom properties, Tailwind — tout est préservé. Quand vous importez un codebase, je travaille dessus comme un dev : je lis le theme, je réutilise les composants existants, je respecte les tokens. La fidélité est pixel-parfaite si les sources sont là.

Le meilleur combo pour un résultat premium : codebase + screenshots de l'état actuel + brief. Si vous voulez passer l'un des 4 wireframes en hi-fi, dites-moi juste lequel et attachez ce que vous avez (ou je peux partir sans — ce sera simplement moins ancré dans votre identité existante).

---

## Compatibilité Figma

Je lis Figma en passant par les liens publics que vous collez (frame, page, ou fichier). Ce que j'en tire :

- Les **images** rendues des frames — référence visuelle fidèle
- La **structure visible** (layout, hiérarchie, espacement approximatif)
- Les **couleurs, typographies, tailles** par inspection des exports
  
Ce qui ne passe pas automatiquement : les *variables Figma, les auto-layout précis, les variants/props de composants, les prototypes interactifs*. Pour ces éléments, le plus sûr reste d'exporter le fichier en codebase (via un plugin type Locofy/Anima/Figma-to-code) puis de l'importer, ou de me fournir en parallèle les tokens (JSON de design tokens si vous en avez).

## L'avantage incomparable sur Figma

Figma produit des maquettes ; moi je produis du code réel, fonctionnel, exécutable.

- **HTML/CSS/JS totalement fonctionnel** — pas d'export approximatif, c'est du code que vous pouvez coller dans votre projet. Les animations tournent, les formulaires fonctionnent, les états (hover, focus, disabled, loading) sont vrais.
Interactions réelles — un bouton clique, un menu s'ouvre, un carousel défile, une API peut être appelée. Les prototypes Figma miment ; les miens font.

- **Responsive déduit automatiquement** — si vous fournissez une maquette desktop + une maquette mobile (ou juste une des deux + la consigne), je génère les @media breakpoints, les grilles fluides, les comportements clamp(), le stacking mobile, les hit-targets 44px, etc. Un seul fichier HTML qui fonctionne sur toutes les tailles.
Logique conditionnelle et data — là où Figma s'arrête à la représentation, je peux brancher de la vraie logique : localStorage, appels LLM via window.claude.complete(), manipulation DOM, validation de formulaires.

- **Accessibilité réelle** — aria-, focus states, navigation clavier, contrastes calculés.
Tweaks live en production — le panneau Tweaks que vous avez utilisé sur les wireframes ? Impossible nativement dans Figma. Ici c'est du vrai JS qui modifie du vrai CSS en direct.
Sortie multi-format — du même HTML je sors un PDF, un PPTX éditable, une version standalone offline, un handoff dev, un export Canva.

Concrètement pour votre cas : si vous me donnez une maquette Figma desktop + la mention « responsive mobile aussi », je livre un fichier HTML unique qui s'adapte de 320px à 2560px, avec vraies interactions, prêt à être déployé. Figma vous aurait donné une deuxième frame à dessiner à la main.

La limite honnête : pour un design system de 200 composants avec variants/tokens complexes déjà en place dans Figma, l'import reste partiel — dans ce cas, importer le codebase de votre bibliothèque de composants donne un meilleur résultat que le Figma lui-même.

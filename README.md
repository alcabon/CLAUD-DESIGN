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

---

Ce que je peux vous dire de manière honnête :

## Ce qui marche très bien

- **Mockups** de sites/landing pages, dashboards, apps SaaS classiques
- **Wireframes** et exploration rapide de directions (comme vos 4 options)
- **Prototypes interactifs hi-fi** (onboarding, flows, composants)
- **Slides** / decks, documents imprimables
- **Animations** et micro-interactions
- **Reprise d'un design system existant** si le codebase est importé
- **Responsive desktop ↔ mobile** avec déduction automatique

## Ce qui demande plus d'itération

- **Designs très typés** « 3D / WebGL / shader »
- **Reproductions pixel-perfect** sans source (juste un screenshot flou)
- **Interactions temps réel complexes** (collaboration multi-user, streams vidéo)
- **Systèmes avec des centaines de composants** où la cohérence totale est critique — il faut alors importer le codebase, pas repartir de zéro

## Mes limites honnêtes

Je ne dessine pas d'illustrations SVG complexes à la main — j'utilise des placeholders et je demande les vrais assets
Pour une vraie mise en prod, mon output est un excellent point de départ mais doit passer par une revue dev/design

Je peux halluciner sur des détails de marques que je connais mal — fournir les sources évite ça

Le plus fiable pour juger : testez sur un cas concret à vous. 

Donnez-moi un brief avec vos contraintes, je livre, vous jugez la fidélité et la fonctionnalité réelle. C'est plus parlant que des chiffres.

---

c'est un des exercices où je suis le plus utile. 

## Voici comment je procède, comparé à un UX designer humain :

## Ce que je fais aussi bien qu'un UX designer senior

- **Critique structurée point par point** — hiérarchie visuelle, parcours utilisateur, charge cognitive, friction, accessibilité, responsive. Je justifie chaque remarque avec un principe (loi de Fitts, loi de Hick, Nielsen heuristics, WCAG, Gestalt…) plutôt qu'avec « je le sens comme ça ».

- **Respect strict des contraintes de marque** — si vous me donnez la charte (couleurs, polices, logos, tone of voice), je ne la touche pas. Ma critique porte alors sur ce qui n'est pas contraint : layout, hiérarchie, copy, interaction, parcours, densité, ordre d'information.

- **Itération rapide** — je produis 3-5 variations fonctionnelles côte-à-côte en une passe, ce qu'un humain fait en plusieurs jours.

- **Critique et implémentation** — je ne dis pas seulement « ceci est faible » ; je livre la version améliorée dans le même mouvement, pour comparaison directe A/B.

## Cadre de critique que j'applique typiquement

- **Clarté** : le message principal est-il lisible en < 3 secondes ?
- **Hiérarchie** : l'œil suit-il l'ordre d'importance métier ?
- **CTA** : un seul CTA primaire visible par écran ? Son libellé est-il actionnable ?
- **Friction** : combien de clics/champs avant la valeur ? Peut-on en retirer ?
- **Scan vs lecture** : densité adaptée au contexte (dashboard = scan, article = lecture) ?
- **États** : vide, chargement, erreur, succès, hover, focus, disabled — tous couverts ?
- **Mobile-first** : la version mobile dégrade-t-elle gracieusement ou est-ce du desktop rétréci ?
- **Accessibilité** : contrastes AA/AAA, targets 44px, ordre DOM logique, aria
- **Cohérence** : mêmes patterns pour mêmes actions à travers le produit
- **Tone & copy** : ton aligné avec la marque, pas de jargon inutile, verbe d'action

## Où un humain reste meilleur

- Recherche utilisateur réelle (entretiens, tests, observation terrain) — je ne peux qu'analyser ce que vous me rapportez
- Intuition culturelle fine sur un marché/métier spécifique
- Négociation politique avec les parties prenantes
- Jugement sur la stratégie produit au-delà de l'écran

Suggestion concrète : envoyez-moi une maquette ou un screenshot d'une de vos interfaces actuelles, avec la charte + le contexte (qui l'utilise, pour quoi faire, quel problème). Je vous rends :

- Une critique écrite numérotée avec justifications
- Une version améliorée fonctionnelle (HTML/CSS) respectant votre charte
- Les points restés subjectifs, clairement signalés comme tels

---

Je lis ce fichier, je l'importe dans tous les prototypes suivants, et la charte est respectée automatiquement sans que le métier ait à y penser.

## La limite honnête de Napkin dans ce workflow

Napkin excelle pour les idées rapides à la main. Le passage à Claude Design reste le plus fluide quand le croquis est accompagné d'un brief contextuel (qui l'utilise, quel parcours, quel CTA principal) — sinon je fais des hypothèses, et c'est vous qui les validez à l'itération suivante.

Mais franchement : **croquis Napkin + tokens CSS + 2 phrases de brief**, c'est suffisant pour que je sorte un prototype présentable en 10 minutes. Le rapport valeur/coût par rapport à une agence ou un dev junior est difficile à battre pour la phase d'exploration.

---

Totalement d'accord — c'est le pipeline le plus puissant qu'on puisse imaginer aujourd'hui :

## Le pipeline UX Designer + Claude Design

```
UX Designer (valeur humaine irremplaçable)
  → recherche utilisateur, tests, stratégie produit
  → wireframes Figma annotés (parcours, états, variants)
  → design system Figma avec tokens exportables
        ↓
Claude Design (exécution production)
  → traduit le Figma en HTML/CSS/JS fonctionnel
  → ajoute animations, transitions, micro-interactions
  → gère tous les états (vide, erreur, loading, succès)
  → génère le responsive automatiquement
  → livre A/B variants si le Figma présente des options
        ↓
Dev IT (intégration finale)
  → branche les APIs
  → intègre dans le framework
  → QA + déploiement
```

Ce que ça change concrètement

La phase **« Figma → code »** est historiquement la plus lente et la plus frustrante — le dev interprète, le designer corrige, on recommence. Ce cycle disparaît presque entièrement.

Un Figma bien annoté (parcours, états, breakpoints indiqués) me permet de livrer une implémentation fidèle, animée, responsive en une passe. Le designer valide sur du vrai rendu navigateur — pas sur une approximation dev.

Ce que le designer doit annoter pour un résultat optimal

- Les **transitions entre écrans** (fondu, slide, spring ?)
- Les **états de chaque composant** (hover, focus, disabled, error)
- Le **breakpoint mobile et les règles de stacking**
- Les **micro-interactions clés** (feedback bouton, validation formulaire)
- L' **ordre de priorité** si le mobile doit réordonner les blocs

Avec ça, **je produis quelque chose qu'un dev aurait mis 2-3 jours à coder — en quelques minutes.** 

Le designer conserve tout son rôle stratégique et créatif ; Claude Design absorbe la partie mécanique et répétitive de la production.

C'est vraiment là que le duo devient imbattable.

---

## Alternatives open-source à Figma

- **Penpot** — le plus sérieux. Entièrement open-source (AGPL), auto-hébergeable ou hébergé gratuitement sur penpot.app. Collaboration temps réel, composants, design tokens, export SVG/PDF. Fichiers stockés en SVG + JSON standard, donc vraiment ouverts. Dev-friendly : exporte en code CSS propre. C'est le concurrent direct le plus mature.

- **Excalidraw** — pour le wireframe et les croquis main levée. Open-source (MIT). Parfait pour l'idéation et les schémas ; moins pour la maquette hi-fi.

- **Inkscape** — éditeur vectoriel SVG complet, GPL. Pas pensé pour l'UI, mais puissant pour l'illustration et les assets.

- **Akira** — ambition d'être « Figma pour Linux », open-source (GPL). Développement ralenti, pas encore mature.

- **Plasmic** — pas totalement open-source mais le builder est libre (MIT partiel) ; orienté design-to-code React/Vue/Next avec génération réelle.

Des outils plus « code-first » qui remplacent Figma en amont du design :

- **Framer** (propriétaire mais très proche code)
- **Webflow** (propriétaire, no-code web)
- **Tldraw** (MIT, canvas infini pour diagrammes/UI flows)

Mon conseil pratique :

- Pour remplacer Figma 1:1 → Penpot, sans hésiter
- Pour wireframes rapides → Excalidraw ou Tldraw
- Pour passer au code fonctionnel → commencez chez Penpot puis importez chez moi (ou travaillez directement avec moi à partir d'un brief + screenshots de références)

Le gros avantage de Penpot sur Figma pour votre usage freelance IT : vous restez propriétaire de vos fichiers, pas de lock-in, et les formats SVG/JSON sont parsables par n'importe quel outil.

---

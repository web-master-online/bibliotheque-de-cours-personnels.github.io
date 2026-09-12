# Mes cours

Bibliothèque personnelle de cours au format HTML, avec une page d'accueil qui regroupe tous les guides sous forme de cartes classées par thème et par couleur.

Aucune dépendance, aucun build : chaque page est un fichier `.html` autonome (HTML + CSS inline, sans Tailwind ni framework externe) qui s'ouvre directement dans un navigateur.

## Structure du projet

```
.
├── Accueil.html                 # Page d'accueil (grille de cartes)
├── sql.html                     # Guide SQL — Base de données
├── lois_ohm.html                # Guide Lois d'Ohm — Électronique
├── gpio_esp32.html              # Guide GPIO / ESP32 — Microcontrôleur
├── energie_cinetique.html       # Guide Énergie cinétique — Physique
├── xml_android.html             # Guide XML Android — Développement mobile
├── kotlin.html                  # Guide Kotlin — Programmation
└── README.md
```

> ⚠️ Les liens des cartes sur `Accueil.html` pointent vers ces noms de fichiers exacts (`sql.html`, `lois_ohm.html`, etc.). Si tu gardes des noms différents (ex. `Lois_d_Ohm_v2.html`), renomme tes fichiers ou mets à jour les `href` correspondants dans `Accueil.html`.

## Thèmes et badges

Chaque cours a une couleur d'accent dédiée, utilisée à la fois sur sa propre page et sur son badge dans l'accueil, pour repérer le thème d'un coup d'œil.

| Couleur | Thème | Cours |
|---|---|---|
| 🟣 Violet | Base de données | SQL |
| 🟢 Vert | Électronique | Lois d'Ohm |
| 🔵 Bleu | Microcontrôleur | GPIO / ESP32 |
| 🟠 Orange | Physique | Énergie cinétique |
| 🌸 Rose | Développement mobile | XML Android |
| 🟦 Bleu-vert | Programmation | Kotlin |

## Fonctionnalités communes à chaque page

- **Sommaire latéral fixe** (desktop) avec surlignage automatique de la section lue, via `IntersectionObserver`.
- **Mode nuit** persistant (bouton en en-tête, sauvegardé dans `localStorage`).
- **Cards** pour chaque notion, avec exemples de code / formules mis en avant.
- Design 100% CSS "maison" (classes utilitaires façon Tailwind, écrites à la main, sans dépendance externe).

## Ajouter un nouveau cours

1. Dupliquer un guide existant (ex. `kotlin.html`) comme point de départ.
2. Adapter le titre, le sommaire, les sections et les exemples au nouveau thème.
3. Choisir une couleur d'accent qui n'est pas déjà utilisée (voir tableau ci-dessus) et l'appliquer aux classes `bg-*`, `text-*`, `border-*`, `.tag`, `.sidebar-link`, etc.
4. Sur `Accueil.html` :
   - Ajouter un bloc `.theme-<couleur>` dans le CSS (badge, dot, barre du haut, lien "Ouvrir le cours") + son équivalent en mode nuit.
   - Ajouter une nouvelle carte `<a class="course-card theme-<couleur>">` dans la grille, avec son badge, son titre et sa description.
   - Mettre à jour la phrase récapitulative des couleurs en bas de page.

## Ouvrir le projet

Aucun serveur nécessaire : ouvre `Accueil.html` directement dans ton navigateur, ou héberge le dossier tel quel sur n'importe quel hébergement statique (GitHub Pages, Netlify, etc.).

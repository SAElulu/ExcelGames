# Détente.xlsx

Un classeur de mini casse-têtes relaxants, déguisé en tableur. Site 100 % statique (HTML/CSS/JS, aucune dépendance), prêt pour GitHub Pages.

## Mettre en ligne (GitHub Pages)

1. Crée un dépôt GitHub et pousse le contenu de ce dossier à la racine (`index.html`, `css/`, `js/`).
2. Dans le dépôt : **Settings → Pages → Build and deployment → Deploy from a branch**, choisis `main` et `/ (root)`.
3. Le site est disponible à `https://<ton-pseudo>.github.io/<nom-du-depot>/`.

On peut aussi juste ouvrir `index.html` dans un navigateur pour jouer en local.

## Les 6 feuilles (jeux originaux)

| Feuille | Fonction | Principe |
|---|---|---|
| Couronnes | `=COURONNES()` | Une couronne par ligne, colonne et zone de couleur, sans contact. |
| Binaire | `=BINAIRE()` | Grille de 1 et de 0, équilibrée, avec contraintes `=` et `×`. |
| Liaison | `=LIAISON()` | Un seul trait qui relie les nombres dans l'ordre et remplit tout. |
| Somme cible | `=SOMME.CIBLE()` | Barrer des chiffres pour tomber pile sur les totaux. |
| Pixels | `=MFC.PIXELS()` | Logigraphe : les indices révèlent un dessin en couleurs. |
| RechercheV | `=RECHERCHEV()` | Trouver la catégorie commune à partir d'indices `#N/A`. |

- **Puzzle du jour** : généré à partir de la date, donc identique pour tous les joueurs, sans serveur. Les grilles logiques sont vérifiées à solution unique.
- **Partie libre** : un puzzle aléatoire à volonté (compte dans les points zen, pas dans le comparatif du jour).

## Joueurs, résultats, classement

- Profils (Lucas, Rémi, et autant qu'on veut via *Insertion → Nouveau joueur*).
- Le premier résultat de chaque puzzle du jour est enregistré (temps, aides utilisées).
- Feuille **Classement** : points zen (10 par puzzle du jour, 5 par partie libre, +3 sans aide, +2 par jour de série), série en cours, titres rigolos, tableau du jour avec échelle de couleurs.

## Partager les résultats entre joueurs (sans compte)

*Données → Lien de partage* : le lien contient tes résultats des 45 derniers jours. L'autre l'ouvre et clique **Importer**. Ça marche dans les deux sens et les doublons sont ignorés. Il y a aussi *Copier mon code / Importer un code*, et l'export/import `.json`.

Le stockage est isolé dans `js/core.js` (`results`, `share`) : brancher plus tard une synchro automatique (Firebase, Supabase…) ne touche que ce fichier.

## Petits détails

- Ruban à onglets, barre de formule qui affiche la « formule » de la case survolée, en-têtes de ligne/colonne qui suivent la souris.
- Changement de feuille animé (glissé + « Calcul… » dans la barre d'état), confettis en forme de cellules, vague sur la grille à la victoire.
- Double-clic sur une cellule vide pour écrire dedans : `=SOMME(1;2)`, `=CAFE()`, `=BRAVO()`, `=COURONNES()`…
- Mode sombre, 4 couleurs d'accent, mode zen (chrono masqué), zoom, sons doux désactivables.
- Raccourcis : `Alt + Page suiv./préc.` (feuilles), `H` (indice), `Ctrl+Z`, `F1`, `/` (recherche).
- Menu **Fichier** façon backstage (Ouvrir, Nouveau, Partager, Joueurs).

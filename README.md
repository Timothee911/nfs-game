# 🏎️ NFS Dubai Ultimate

Jeu de course 3D en un seul fichier HTML (Three.js), en français. Tu affrontes une IA sur un circuit de **12,6 km**, avec des virages à bien négocier, plusieurs cartes et une météo qui change.

## Jouer

Ouvre `index.html` dans un navigateur récent (Chrome, Edge, Firefox). Une connexion internet est nécessaire : Three.js est chargé depuis un CDN (cdnjs, avec jsDelivr en secours).

## Contrôles

| Touche | Action |
|---|---|
| `Z` ou `↑` | Accélérer |
| `S` ou `↓` | Freiner |
| `Q` / `D` ou `←` / `→` | Gauche / droite |
| `Espace` | Nitro (la jauge bleue se recharge) |
| `C` | Changer de caméra (poursuite / capot) |
| `P` ou `Échap` | Pause |
| `M` | Couper / remettre le son |

Dans le garage : flèches `↑` `↓` pour naviguer, `Entrée` pour valider, `Échap` pour revenir.

## Le jeu

- **Virages** : la voiture est poussée vers l'extérieur proportionnellement au carré de la vitesse. Freine avant les virages, un mur te fait perdre beaucoup de vitesse. Le trait blanc de la jauge de vitesse indique le seuil au-delà duquel tu ne tiens plus un virage.
- **Cartes** : Dubaï (désert et gratte-ciel), Alpes (sapins et montagnes), Tokyo de nuit (néons et lampadaires), Arctique (neige).
- **Météo** : dégagé, brouillard, pluie, orage (éclairs et tonnerre). La pluie et l'orage réduisent l'adhérence. En mode « Aléatoire », la carte et la météo sont tirées au sort à chaque course.
- **IA** : 4 niveaux (Facile, Normal, Difficile, Impossible). L'IA freine avant les virages et peut en rater un selon son niveau.
- **Garage** : menu style NFS Rivals avec la voiture **SAQR X1** en 3D, 6 couleurs au choix, réglages de carte et de météo.
- **Speedlistes** : séries de missions (route, virages, légende) affichées à droite du garage. Chaque mission réussie rapporte des SP, et finir une liste donne un bonus.
- **Améliorer performance** : dépense tes SP dans le moteur, le turbo, les pneus et le nitro.
- **Changer de voiture** : d'autres voitures arriveront plus tard.
- **Sauvegarde** : victoires, meilleur temps, SP, améliorations, Speedliste, couleur, carte et météo sont mémorisés dans le navigateur (`localStorage`). Le bouton « Réinitialiser mes stats » du lobby remet tout à zéro.

## Régler le jeu

Dans le script de `index.html` :

- `SPEED_SCALE` : vitesse générale.
- `TOTAL_SEGMENTS` : longueur du parcours (un segment fait 45 m).
- `aiSpeed` dans `difficultySettings` : vitesse de l'IA à chaque niveau.
- `MAPS` et `WEATHERS` : ajouter ou modifier des cartes et des météos.
- Le facteur `0.6` de `curve * speed * speed * 0.6 * slip` : force de poussée dans les virages.

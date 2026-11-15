# 🏎️ NFS Dubai Ultimate

Jeu de conduite 3D en monde ouvert, en un seul fichier HTML (Three.js), en français. Tu roules librement dans un comté de **9 × 9 km** parcouru par **49 km de routes**, dans une lumière de fin de journée après la pluie. Il n'y a plus de course : tu gagnes des SP en enchaînant les figures.

## Jouer

Ouvre `index.html` dans un navigateur récent (Chrome, Edge, Firefox). Une connexion internet est nécessaire : Three.js est chargé depuis un CDN (cdnjs, avec jsDelivr en secours).

## Contrôles

| Touche | Action |
|---|---|
| `Z` ou `↑` | Accélérer |
| `S` ou `↓` | Freiner, puis marche arrière |
| `Q` / `D` ou `←` / `→` | Tourner |
| `Espace` | Frein à main (drift) |
| `Maj` ou `N` | Nitro |
| `M` ou `Tab` | Ouvrir / fermer la carte (met le jeu en pause) |
| `C` | Changer de caméra (poursuite / capot) |
| `R` | Replacer la voiture sur la route la plus proche |
| `X` | Couper / remettre le son |
| `Échap` | Retour au garage |

Dans le garage : flèches `↑` `↓` pour naviguer, `Entrée` pour valider, `Échap` pour revenir.

## Le jeu

- **Carte** : une rocade à quatre voies de 21 km, une boucle intérieure, six radiales et deux traversantes, sur un relief de collines, avec forêts, glissières, lampadaires, lignes électriques et montagnes à l'horizon.
- **Conduite** : la voiture a une vraie vitesse, une inertie et une adhérence limitée. Le braquage se réduit avec la vitesse, il faut freiner avant les virages serrés, et le frein à main fait décrocher l'arrière. Hors de la route, l'herbe freine et accroche moins. Les glissières, les arbres et le trafic abîment la voiture ; à zéro, elle est replacée sur la route.
- **Séries de points** : haute vitesse (plus de 250 km/h), drift, frôlement du trafic, contresens et radars alimentent une série. Le multiplicateur monte jusqu'à ×5, puis la série est encaissée en SP après 4 s sans figure. Un accident la fait perdre.
- **Radars** : 12 radars à flasher, avec ta meilleure vitesse mémorisée.
- **Planques** : 4 planques (faisceau vert). S'y arrêter sous 60 km/h ramène au garage.
- **Interface** : mini-carte, compte-tours avec rapport et vitesse, jauge de nitro, état de la voiture, SP, série en cours et objectifs de la Speedliste.
- **Garage** : menu style NFS Rivals avec la voiture **SAQR X1** en 3D, la peinture (10 couleurs), les Speedlistes (objectifs à remplir en roulant) et les améliorations (moteur, turbo, pneus, nitro) à payer en SP.
- **Sauvegarde** : SP, améliorations, Speedliste, radars et couleur sont mémorisés dans le navigateur (`localStorage`). Le bouton « Réinitialiser ma progression » du garage remet tout à zéro.

## Régler le jeu

Dans le script de `index.html` :

- `hAt` : relief du terrain.
- `ringPts` et `makeRoad` : tracé des routes.
- `stepPlayer` : physique de la voiture (accélération, adhérence `mu`, braquage, frein à main).
- `SPEEDLISTS` : objectifs et récompenses.
- `spawnTraffic` : trafic.

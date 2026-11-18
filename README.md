# 🏎️ NFS Dubai Ultimate

Jeu de conduite 3D en monde ouvert, en un seul fichier HTML (Three.js), en français. Tu roules librement dans un comté de **14 × 14 km** parcouru par **105 km de routes**, entouré de montagnes, dans une lumière de fin de journée après la pluie. Il n'y a plus de course : tu gagnes des SP en enchaînant les figures.

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

### Réglages (garage → Réglages)

Sensibilité de la direction (1 à 10), réactivité du stick, vibrations, caméra au départ, volume, herbe en volume (désactivée / légère / dense), mini-carte (suit la voiture ou nord en haut). Les réglages sont mémorisés.

### Carte (`M`)

Carte plein écran : molette, `+` / `-` ou gâchettes pour zoomer, glisser, `ZQSD` / flèches ou stick pour se déplacer, `C` ou Croix pour recentrer sur la voiture.

### Manette (Xbox, PlayStation, générique : branchée ou en Bluetooth)

| Bouton | Action |
|---|---|
| Gâchette droite (RT / R2) | Accélérer (progressif) ; démarre aussi le moteur |
| Gâchette gauche (LT / L2) | Freiner, puis marche arrière (progressif) |
| Stick gauche ou croix directionnelle | Tourner (progressif) |
| Carré (PlayStation) / X (Xbox) | Frein à main (drift) |
| Croix (PlayStation) / A (Xbox) | Nitro |
| Triangle / Y | Replacer la voiture |
| Share / View | Carte |
| Options / Menu | Retour au garage |
| L1 / R1 | Changer de caméra |

Dans le garage : croix ou stick pour naviguer, Croix / A pour valider, Rond / B pour revenir. La manette vibre sur les chocs, les glissades et le nitro.

## Le jeu

- **Carte** : une rocade à quatre voies de 36 km, deux boucles intérieures, treize routes de liaison sinueuses et deux traversantes, sur un relief de collines et de vallons, avec trois lacs, des forêts, des glissières, des lampadaires, des lignes électriques, des balises et des chevrons dans les virages serrés.
- **Villes** : 4 villes posées sur un terrain aplani : **Saqr City** (centre d'affaires aux tours de verre, dont une tour emblème de 318 m), **Al Waha** et **Qasr Al Sahra** sont dessinées par le jeu ; **Port Rimal** est une vraie ville en 3D (fichier ``ville.glb``, environ 1,2 × 1 km, en colline : ses rues montent de 6 à 45 m). Elle est posée à côté de la rocade intermédiaire et reliée par une bretelle à l'avenue qui entre par l'est ; le terrain épouse son sol, on y roule sur ses rues et rampes, et ses immeubles arrêtent la voiture (sol et murs relevés dans le modèle au chargement, sur une grille de 2 m). Les panneaux à chevrons qui fermaient les rues dans le décor d'origine ont été retirés. Les villes dessinées ont une grille de rues reliée au réseau (GPS et trafic compris), des immeubles de bureaux, des immeubles d'habitation à balcons, des commerces avec vitrines et enseignes au rez-de-chaussée, des villas, des équipements sur les toits, des trottoirs à bordure, des lampadaires et des palmiers. Les immeubles arrêtent la voiture. Les villes et leurs immeubles apparaissent sur la mini-carte et la grande carte, et leur nom s'affiche quand tu y entres.
- **Décor** : nuages volumétriques calculés au chargement (cumulus et cirrus éclairés par le soleil), brume qui s'éclaircit avec l'altitude, chaîne de montagnes continue autour du comté (forêts, roche, neige selon l'altitude et la pente), arbres peints (épicéas, pins, feuillus d'automne, bouleaux) qui bougent dans le vent, buissons et herbes hautes au bord des routes, lacs qui reflètent le ciel.
- **Conduite** : la voiture a une vraie vitesse, une inertie et une adhérence limitée. Le braquage se réduit avec la vitesse, il faut freiner avant les virages serrés, et le frein à main fait décrocher l'arrière. La caisse bouge sur sa suspension (plongée au freinage, léger roulis vers l'extérieur des virages) et les routes sont presque plates en travers, avec un remblai côté aval. Hors de la route, l'herbe freine et accroche moins. Les glissières, les arbres et le trafic abîment la voiture ; à zéro, ou si elle tombe dans un lac, elle est replacée sur la route.
- **Trafic** : 14 petites voitures du quotidien en 5 modèles (citadine, compacte, berline, break, ludospace), aux couleurs courantes, avec vitres, jantes, passages de roues, feux, rétroviseurs, joints de portes et plaques. Elles sont posées sur leurs 4 roues avec une ombre de contact : les roues tournent, les roues avant braquent et la caisse bouge sur sa suspension.
- **Séries de points** : haute vitesse (plus de 250 km/h), drift, frôlement du trafic, contresens et radars alimentent une série. Le multiplicateur monte jusqu'à ×5, puis la série est encaissée en SP après 4 s sans figure. Un accident la fait perdre.
- **Radars** : 20 radars à flasher, avec ta meilleure vitesse mémorisée.
- **Planques** : 6 planques. En quittant le garage, tu pars d'une planque tirée au hasard, sur le parvis face à la route. Pour rentrer au garage, touche la ligne verte peinte au sol devant la porte d'une autre planque (ou de la même, une fois que tu t'en es éloigné de 70 m).
- **GPS** : la mini-carte montre le relief, les forêts, les lacs, les villes et les routes, et trace en vert l'itinéraire par la route jusqu'à la planque la plus proche. Elle dézoome quand tu vas vite.
- **Interface** : mini-carte GPS, compte-tours avec rapport et vitesse, jauge de nitro, état de la voiture, SP, série en cours et objectifs de la Speedliste.
- **Ferrari SF90 Spider** : la voiture est le modèle 3D `ferrari.glb` (« 2021 Ferrari SF90 Spider », Sketchfab, licence **CC BY-NC** : usage non commercial, crédit obligatoire). Au chargement, ses quelque 1 200 morceaux sont regroupés par matière pour rester fluide ; les roues tournent et braquent, les étriers restent fixes, les feux arrière s'allument au freinage et la peinture suit la couleur choisie au garage. Le fichier doit rester à côté de `index.html` et la page doit être servie par un serveur (GitHub Pages, ou « Live Server » dans VS Code) : ouverte en double-cliquant, ou si le fichier manque, le jeu garde l'ancienne voiture dessinée (SAQR X1).
- **Garage** : menu style NFS Rivals avec la **Ferrari SF90 Spider** en 3D, la peinture (10 couleurs), les Speedlistes (objectifs à remplir en roulant) et les améliorations (moteur, turbo, pneus, nitro) à payer en SP.
- **Sauvegarde** : SP, améliorations, Speedliste, radars et couleur sont mémorisés dans le navigateur (`localStorage`). Le bouton « Réinitialiser ma progression » du garage remet tout à zéro.

## Régler le jeu

Dans le script de `index.html` :

- `hills`, `ridged` et `hAt` : relief du terrain et des montagnes.
- `ringPts`, `linkRoad` et `makeRoad` : tracé des routes.
- `cloudMat` : forme et éclairage des nuages (`CLOUD_Q` règle leur finesse).
- `paintTreeAtlas` : dessin des arbres.
- `stepPlayer` : physique de la voiture (accélération, adhérence `mu`, braquage, frein à main).
- `SPEEDLISTS` : objectifs et récompenses.
- `spawnTraffic` : trafic.

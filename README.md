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
- **Villes** : 4 villes posées sur un terrain aplani : **Saqr City** (centre d'affaires aux tours de verre, dont une tour emblème de 318 m), **Al Waha** et **Qasr Al Sahra** sont dessinées par le jeu ; **Port Rimal** est une vraie ville en 3D (fichier ``ville.glb``, environ 1,2 × 1 km, en colline : ses rues montent de 6 à 45 m). Elle est posée à côté de la rocade intermédiaire ; le terrain épouse son sol, on y roule sur ses rues et rampes, et ses immeubles arrêtent la voiture (sol et murs relevés dans le modèle au chargement, sur une grille de 2 m). Ses 57 rues (axes relevés dans le modèle, avec la hauteur de la chaussée) font partie du réseau du jeu : adhérence de route, GPS, mini-carte et trafic, qui y roule à 40-55 km/h et suit les rues de carrefour en carrefour. Le centre, vide dans le modèle d'origine (une colline d'herbe), est devenu un quartier : sol lisse au niveau des rues voisines, 8 rues nouvelles qui prolongent les impasses, et des immeubles qui reprennent les façades du modèle. En plus de la bretelle de l'est, 4 routes de raccordement relient des sorties de la ville au réseau du comté, en pente douce (9 % au plus) avec le terrain retaillé dessous. Les panneaux à chevrons qui fermaient les rues dans le décor d'origine ont été retirés. Les villes dessinées ont une grille de rues reliée au réseau (GPS et trafic compris), des immeubles de bureaux, des immeubles d'habitation à balcons, des commerces avec vitrines et enseignes au rez-de-chaussée, des villas, des équipements sur les toits, des trottoirs à bordure, des lampadaires et des palmiers. Les immeubles arrêtent la voiture. Les villes et leurs immeubles apparaissent sur la mini-carte et la grande carte, et leur nom s'affiche quand tu y entres.
- **Décor** : nuages volumétriques calculés au chargement (cumulus et cirrus éclairés par le soleil), brume qui s'éclaircit avec l'altitude, chaîne de montagnes continue autour du comté (forêts, roche, neige selon l'altitude et la pente), arbres peints (épicéas, pins, feuillus d'automne, bouleaux) qui bougent dans le vent, buissons et herbes hautes au bord des routes, lacs qui reflètent le ciel.
- **Conduite** : la voiture a une vraie vitesse, une inertie et une adhérence limitée. Le braquage se réduit avec la vitesse, il faut freiner avant les virages serrés, et le frein à main fait décrocher l'arrière. La caisse bouge sur sa suspension (plongée au freinage, léger roulis vers l'extérieur des virages) et les routes sont presque plates en travers, avec un remblai côté aval. Hors de la route, l'herbe freine et accroche moins. Les glissières, les arbres et le trafic abîment la voiture ; à zéro, ou si elle tombe dans un lac, elle est replacée sur la route.
- **Trafic** : 14 petites voitures du quotidien en 5 modèles (citadine, compacte, berline, break, ludospace), aux couleurs courantes, avec vitres, jantes, passages de roues, feux, rétroviseurs, joints de portes et plaques. Elles sont posées sur leurs 4 roues avec une ombre de contact : les roues tournent, les roues avant braquent et la caisse bouge sur sa suspension.
- **Séries de points** : haute vitesse (plus de 250 km/h), drift, frôlement du trafic, contresens et radars alimentent une série. Le multiplicateur monte jusqu'à ×5, puis la série est encaissée en SP après 4 s sans figure. Un accident la fait perdre.
- **Radars** : 20 radars à flasher, avec ta meilleure vitesse mémorisée.
- **Planques** : 6 planques. En quittant le garage, tu pars d'une planque tirée au hasard, sur le parvis face à la route. Pour rentrer au garage, touche la ligne verte peinte au sol devant la porte d'une autre planque (ou de la même, une fois que tu t'en es éloigné de 70 m).
- **GPS** : la mini-carte montre le relief, les forêts, les lacs, les villes et les routes, et trace en vert l'itinéraire par la route jusqu'à la planque la plus proche. Elle dézoome quand tu vas vite.
- **Interface** : mini-carte GPS, compte-tours avec rapport et vitesse, jauge de nitro, état de la voiture, SP, série en cours et objectifs de la Speedliste.
- **6 voitures** (onglet « Changer de voiture » du garage, une vignette par modèle) : la Ferrari est offerte, les autres ont un cadenas jusqu'au **niveau pilote** qui les débloque, puis s'achètent en SP : Mercedes-AMG GT3 (niveau 2, 4 000 SP), McLaren P1 (niveau 3, 8 000 SP), Aventador SVJ (niveau 4, 15 000 SP), Veneno (niveau 5, 25 000 SP), Koenigsegg One:1 (niveau 6, 40 000 SP). Le niveau pilote monte de 1 chaque fois qu'une Speedliste est terminée (tous ses objectifs), au retour au garage : une animation montre le nouveau niveau, puis chaque voiture débloquée est présentée (avant, côté gauche, arrière, côté droit, puis toute la voiture). La Speedliste terminée repart alors de zéro pour pouvoir être rejouée. Chaque voiture a sa propre couleur (SF90 rouge, AMG blanc sur sa déco rouge, P1 orange, SVJ vert, Veneno gris, Koenigsegg bleu), modifiable voiture par voiture dans « Peinture ». La voiture survolée s'affiche en 3D, `Entrée` ou un 2e clic l'achète ou la choisit, et le choix est mémorisé. Fichiers des modèles 3D :
  - **Ferrari SF90 Spider** : `ferrari.glb` ;
  - **Lamborghini Aventador SVJ** : `cars/aventador.glb` ;
  - **Lamborghini Veneno** : `cars/veneno.glb` ;
  - **McLaren P1** : `cars/p1.glb` ;
  - **Mercedes-AMG GT3** : `cars/amg-gt3.glb`.

  Seule la voiture choisie est téléchargée. Au chargement, ses morceaux sont regroupés par matière pour rester fluide ; les roues tournent et braquent, les étriers restent fixes, les feux arrière s'allument au freinage et la peinture suit la couleur choisie au garage. La page doit être servie par un serveur (GitHub Pages, ou « Live Server » dans VS Code) : ouverte en double-cliquant, ou si le fichier manque, le jeu garde l'ancienne voiture dessinée (SAQR X1).
- **Garage** : menu style NFS Rivals avec la voiture choisie en 3D, les Speedlistes (objectifs à remplir en roulant), les améliorations (moteur, turbo, pneus, nitro) à payer en SP, et deux pages : **Carte** (touche `A` ou L1) et **Garage** (touche `E` ou R1).
  - **Carte** : carte du comté avec un curseur en réticule ; clique sur une planque (ou vise-la au clavier et appuie sur Entrée), le jeu demande « Apparaître ici ? » et la sortie démarre dans cette planque. Molette pour zoomer, glisser pour déplacer.
  - **Personnaliser la voiture** (réglages propres à chaque voiture) : peinture (10 couleurs), finition (brillant, métallisé, nacré, satiné, mat, chrome), motif peint (double bande, bande centrale, bandes latérales, toit contrasté, bas de caisse) et sa couleur, couleur des étriers de frein, teinte des jantes, teinte des vitres, néons sous caisse (7 couleurs), et retour à l'origine.
  - **Plaque d'immatriculation** : texte de 8 caractères et style (Dubaï, européenne, américaine, noire, jaune de course), posée à l'arrière de toutes les voitures (et à l'avant de la McLaren).
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

# Cahier des charges du jeu

## Plateformes et modes de jeu

- Jeu utilisable sur PC, iPhone et Android. Une application web adaptée aux trois types d’appareils est une piste à retenir.
- De 2 à 6 joueurs par partie, adversaires contrôlés par le jeu compris.
- Trois modes de jeu au lancement : solo contre le jeu, multijoueur sur le même appareil en se le passant, et multijoueur en ligne.
- Sauvegarde et reprise en solo et sur appareil partagé. Les parties en ligne se jouent en une seule session.
- Des adversaires contrôlés par le jeu peuvent compléter les places dans les parties entre amis, en local comme en ligne. Trois difficultés : Facile, Normal et Difficile. La difficulté est commune à tous les robots d’une partie. Facile achète et négocie simplement, Normal cherche à compléter ses groupes de couleur, Difficile optimise ses enchères, ses échanges et ses constructions selon les règles actives.
- Le premier joueur est tiré au sort. Les suivants jouent dans l’ordre d’inscription, en revenant au début de la liste si nécessaire.
- Chaque joueur choisit un pion encore disponible avant le départ. Les mêmes pions sont proposés sur tous les plateaux.

## Parties en ligne

- Un pseudo suffit. Pour rejoindre une salle privée entre amis, saisir le code d’invitation et le pseudo.
- En public, le joueur choisit la variante et le jeu le place automatiquement dans une salle disponible correspondante. La ville est tirée au sort pour toute la salle.
- Une partie publique démarre automatiquement à 4 joueurs. Après 5 minutes, elle démarre à 3 humains, ou à 2 humains avec un robot.
- Durée maximale d’un tour en ligne : 30 secondes par défaut, modifiable à la création de la partie. À l’expiration, le joueur passe son tour.
- Les enchères en ligne ont leur propre chronomètre : 20 secondes par propriété. Une offre dans les 5 dernières secondes remet le compteur à 5 secondes. Sans offre, la propriété redevient libre et le prochain joueur qui tombe dessus peut l’acheter au prix affiché.

## Variantes

| Variante | Déroulement |
|---|---|
| Classique | La partie se termine lorsqu’il ne reste qu’un joueur. |
| Express | 10 tours de table complets par défaut, modifiables au lancement. Chaque joueur reçoit au hasard un lot de 3 propriétés. Les lots ont des valeurs proches, ne donnent aucun groupe de couleur complet et les écarts sont compensés en argent. |
| Chrono | 30 minutes par défaut, modifiables au lancement. À l’expiration, on termine le tour de table en cours avant de calculer le classement. |
| Règles maison | Le créateur choisit les options de la partie. Une cagnotte sur le Parc gratuit a été évoquée comme exemple. |

En Express et en Chrono, le classement se fait au patrimoine net : argent disponible + valeur des propriétés et des bâtiments − dettes. À patrimoine net égal, l’argent disponible départage les joueurs. Si les deux montants sont égaux en tête, la victoire est ex æquo.

## Plateaux

- 55 plateaux, présentés dans une liste alphabétique.
- Chaque plateau adapte les noms et les visuels à sa ville. Les montants, les règles de base et les événements sont communs. Les soldes, prix et loyers gardent les mêmes chiffres dans la devise locale, par exemple 1 500 € à Paris, 1 500 ¥ à Tokyo et 1 500 $ US à Las Vegas.
- Chaque ville propose 2 à 3 monuments illustrés, visibles au centre du plateau et sur leurs cases achetables.
- Les autres propriétés portent de vrais noms de grandes rues ou de quartiers. Les groupes de couleur suivent le prestige, des secteurs les plus populaires aux adresses les plus prestigieuses.
- Les quatre cases de type « Gare » représentent une gare, un aéroport desservant la ville et deux lieux emblématiques. Ces deux lieux peuvent reprendre des monuments illustrés. Les quatre cases suivent les mêmes règles de loyer.
- San Francisco–San José et Essen–Duisbourg ont chacun un plateau commun à leur agglomération. Les lieux peuvent provenir de toute l’agglomération.
- À Las Vegas, les propriétés portent des noms d’hôtels-casinos classés par prestige. Les quatre cases de type « Gare » représentent quatre grandes attractions, dont 2 ou 3 sont aussi illustrées au centre.

### Liste alphabétique des 55 plateaux

| | | | | |
|---|---|---|---|---|
| Athènes | Bandung | Bangkok | Barcelone | Berlin |
| Birmingham | Bogotá | Buenos Aires | Calcutta (Kolkata) | Canton (Guangzhou) |
| Chicago | Essen–Duisbourg (Ruhr) | Guadalajara | Hô Chi Minh-Ville | Houston |
| Istanbul | Kinshasa | Kuala Lumpur | Kyiv | Lagos |
| Lahore | Las Vegas | Le Caire | Lima | Londres |
| Los Angeles | Madrid | Manille | Mexico | Miami |
| Milan | Monterrey | Montréal | Moscou | Mumbai |
| Naples | New Delhi | New York | Osaka | Paris |
| Pékin | Rio de Janeiro | Saint-Domingue | Saint-Pétersbourg | San Francisco–San José |
| São Paulo | Séoul | Shanghai | Shenzhen | Singapour |
| Taipei | Téhéran | Tokyo | Toronto | Washington D.C. |

## Achats, échanges et construction

- Par défaut, lorsqu’un joueur refuse une propriété libre au prix affiché, elle reste libre. Le créateur peut activer la mise aux enchères immédiate en cas de refus.
- Les échanges de propriétés et d’argent sont désactivés par défaut. Le créateur peut les activer au lancement. Seul le joueur dont c’est le tour peut faire une proposition. Le destinataire peut accepter, refuser ou faire une contre-offre. En ligne, les offres et contre-offres sans réponse expirent à la fin du tour.
- Les propriétés hypothéquées sont exclues des échanges. Les maisons et hôtels peuvent être transmis avec le terrain. Dès qu’un groupe de couleur est construit, il doit être échangé en entier.
- Par défaut, la construction est équilibrée : une maison sur chaque terrain du groupe avant d’en poser une deuxième. Le créateur peut autoriser la construction libre au sein d’un groupe complet.
- Construire, vendre des bâtiments et hypothéquer sont des actions réservées au tour du joueur.

## Dettes et prêts

- Un loyer impayé doit être réglé au plus tard au prochain tour du débiteur. Le joueur peut demander un prêt à un autre joueur.
- Les prêts entre joueurs sont activés par défaut et désactivables au lancement. Les deux joueurs conviennent du montant prêté, du montant à rembourser et du délai maximal exprimé en tours de table complets. Par exemple, recevoir 1 000 et rembourser 1 200.
- Le remboursement peut se faire en plusieurs fois si les deux joueurs sont d’accord. Si le prêt n’est pas soldé à l’échéance, l’emprunteur a jusqu’à son prochain tour pour régler le solde.
- Avec l’accord des deux joueurs, l’emprunteur peut céder une ou plusieurs propriétés pour couvrir tout ou partie de la dette, même si les échanges sont désactivés.

## Faillite et déconnexion

- En cas de faillite, les propriétés sont mises aux enchères sans maisons, hôtels ni hypothèques. Le solde du joueur et le produit des enchères sont répartis entre ses créanciers au prorata des montants dus.
- En ligne, si un joueur se déconnecte, la partie continue et ses tours sont sautés. Il peut revenir avant la fin du troisième tour de table complet d’absence. Au-delà, il est éliminé.
- Après cette élimination, les propriétés sont immédiatement mises aux enchères une par une, sans maisons, hôtels ni hypothèques. Le solde et le produit des enchères servent d’abord à rembourser les créanciers au prorata des dettes. Le surplus est partagé à parts égales entre les joueurs restants.
- Lorsqu’il ne reste qu’un joueur après une faillite ou une déconnexion définitive, il gagne immédiatement, avant les enchères.

## Détails à préciser

- Noms des propriétés, choix des monuments, des gares, des aéroports et des attractions, et modèles de pions.
- Comportement d’une salle publique avec moins de deux humains après 5 minutes et difficulté du robot ajouté automatiquement.
- Barème de valorisation du patrimoine en fin de partie et règle d’arrondi des répartitions au prorata.

## Stack technique retenue

- Option 1 : PWA avec React et TypeScript, serveur multijoueur Node.js avec Colyseus et sauvegardes locales dans IndexedDB.

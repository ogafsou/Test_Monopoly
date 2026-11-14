# Backlog du jeu

## 1. Initialiser le projet vide et son test
Goal: Obtenir un projet vide dont la construction et le test de démarrage passent.
Description: Initialiser un client React et TypeScript ainsi qu’un serveur Node.js prévu pour Colyseus, sans écran ni règle de jeu. Ajouter un test minimal de démarrage et indiquer les commandes pour lancer le test et construire le projet.

## 2. Trancher les règles encore ouvertes
Goal: Consigner les décisions qui conditionnent le matchmaking et les calculs financiers.
Description: Faire valider le sort d’une salle publique avec moins de deux humains après cinq minutes, la difficulté du robot ajouté automatiquement, le barème du patrimoine et les arrondis au prorata. Reporter les décisions dans le cahier des charges.

## 3. Définir le format des plateaux
Goal: Décrire les 55 villes avec un même format de données.
Description: Séparer la structure commune du plateau, les groupes de couleur, les montants et les événements des noms, de la devise et des visuels propres à chaque ville. Contrôler le nombre et le type des cases, l’unicité de leurs identifiants et les références aux illustrations.

## 4. Renseigner le plateau de Paris
Goal: Disposer d’un plateau complet pour développer et tester le jeu.
Description: Renseigner les rues ou quartiers par prestige, une gare, un aéroport et deux lieux emblématiques, avec deux à trois monuments illustrables et l’euro comme devise. Valider la fiche avec le format de la tâche 3.

## 5. Initialiser une partie et ses joueurs
Goal: Créer un état de départ valide pour deux à six joueurs, robots compris.
Description: Enregistrer le mode, la variante, le plateau, les options et la difficulté commune des robots. Attribuer uniquement des pions disponibles dans le catalogue commun, tirer au sort le premier joueur, puis conserver l’ordre d’inscription pour les suivants.

## 6. Gérer les déplacements et les tours
Goal: Faire avancer la partie d’un tour à l’autre avec les mêmes règles en local et en ligne.
Description: Dans un moteur TypeScript partagé, gérer le lancer, le déplacement et la résolution de l’arrivée sur une case, avec une source de hasard contrôlable en test. Vérifier que seul le joueur actif agit et que l’ordre défini à la création est respecté.

## 7. Acheter une propriété libre
Goal: Permettre au joueur actif d’acheter ou de refuser une propriété libre.
Description: Débiter le prix affiché et transférer la propriété si le joueur dispose des fonds nécessaires. En cas de refus, laisser la propriété libre par défaut ou ouvrir une enchère si cette option est active.

## 8. Appliquer les loyers et les événements
Goal: Résoudre les effets communs des cases sur tous les plateaux.
Description: Appliquer les loyers selon le type de propriété, son groupe et ses bâtiments, avec un même barème pour les quatre cases de type Gare. Appliquer aussi les événements communs et transmettre les loyers impayés au mécanisme de dettes de la tâche 14.

## 9. Gérer les enchères
Goal: Résoudre une enchère sur une propriété de manière cohérente.
Description: Valider les offres, identifier le gagnant et lui transférer la propriété au montant de son offre. Sans offre, remettre la propriété en vente au prix affiché au prochain passage sur la case.

## 10. Construire et vendre des bâtiments
Goal: Appliquer les règles de construction et de vente pendant le tour du propriétaire.
Description: Exiger un groupe complet et appliquer par défaut la construction équilibrée, une maison par terrain avant le niveau suivant. Prendre en charge l’option de construction libre et vérifier les coûts et les changements de bâtiments.

## 11. Hypothéquer une propriété
Goal: Appliquer une hypothèque pendant le tour du propriétaire.
Description: Vérifier que la propriété est admissible, enregistrer son statut et créditer le montant prévu. Rendre ce statut accessible aux règles de loyer, d’échange et de liquidation.

## 12. Négocier un échange
Goal: Permettre les propositions, refus, acceptations et contre-offres.
Description: Réserver l’initiative au joueur actif quand les échanges sont activés, avec propriétés et argent comme éléments négociables. En ligne, expirer les propositions restées sans réponse en fin de tour.

## 13. Appliquer un échange accepté
Goal: Transférer ensemble tous les éléments d’un échange valide.
Description: Revérifier les soldes et la propriété des biens à l’acceptation, puis exclure les terrains hypothéqués. Transférer les bâtiments avec leurs terrains et exiger le groupe entier dès qu’il comporte une construction.

## 14. Suivre les loyers impayés
Goal: Enregistrer une dette de loyer et contrôler son échéance.
Description: Conserver le créancier, le montant dû et l’échéance au prochain tour du débiteur. Permettre le règlement et déclencher la procédure de faillite si la dette reste exigible et impayée.

## 15. Créer un prêt entre joueurs
Goal: Enregistrer un prêt accepté par les deux joueurs.
Description: Autoriser les prêts par défaut et respecter l’option qui les désactive au lancement. Vérifier les fonds du prêteur et enregistrer le montant versé, le total à rembourser et l’échéance en tours de table complets.

## 16. Rembourser un prêt
Goal: Suivre les paiements et les cessions de propriétés liés à un prêt.
Description: Autoriser les versements partiels et les cessions de biens avec accord mutuel, y compris si les échanges ordinaires sont désactivés. Si un solde reste dû à l’échéance, donner à l’emprunteur jusqu’à son prochain tour pour le régler.

## 17. Mettre aux enchères les biens d’un joueur éliminé
Goal: Liquider les propriétés après une faillite ou une déconnexion définitive.
Description: Retirer maisons, hôtels et hypothèques, puis ouvrir les enchères, une propriété à la fois. S’il ne reste qu’un joueur, déclarer sa victoire immédiatement et terminer la partie.

## 18. Répartir le produit d’une liquidation
Goal: Distribuer le solde du joueur éliminé et le produit des enchères.
Description: Rembourser les créanciers au prorata des sommes dues selon l’arrondi validé à la tâche 2. En cas de déconnexion définitive, partager le surplus à parts égales entre les joueurs restants.

## 19. Calculer le classement au patrimoine
Goal: Classer les joueurs dans les variantes Express et Chrono.
Description: Additionner argent et valeur des propriétés et bâtiments, puis soustraire les dettes selon le barème validé à la tâche 2. Départager au montant d’argent disponible et déclarer les premiers ex æquo si les deux valeurs sont égales.

## 20. Distribuer les lots de départ en Express
Goal: Donner à chacun trois propriétés de valeur comparable.
Description: Tirer au sort des lots de trois propriétés sans groupe de couleur complet et sans attribuer deux fois la même propriété. Compenser les écarts de valeur en argent.

## 21. Terminer les parties Classique et Express
Goal: Appliquer la condition de fin de chaque variante.
Description: En Classique, terminer dès qu’il reste un seul joueur. En Express, compter les tours de table complets et calculer le classement au nombre prévu, dix par défaut et modifiable au lancement.

## 22. Terminer une partie Chrono
Goal: Calculer le classement après le dernier tour de table de la variante Chrono.
Description: Utiliser une durée de 30 minutes par défaut, modifiable au lancement. À l’expiration, terminer le tour de table en cours avant d’appeler le calcul du patrimoine.

## 23. Configurer les règles maison
Goal: Permettre au créateur de choisir les options de sa partie.
Description: Proposer les options définies pour les enchères après refus, les échanges, la construction libre et les prêts, avec leurs valeurs par défaut. Faire valider la cagnotte sur le Parc gratuit avant de l’ajouter aux options proposées.

## 24. Écrire les décisions du robot Facile
Goal: Faire jouer un adversaire automatique selon des choix simples et valides.
Description: Utiliser les actions disponibles du moteur pour acheter et, si les échanges sont activés, répondre simplement aux négociations. Vérifier que le robot peut finir son tour si aucune action intéressante n’est disponible.

## 25. Écrire les décisions du robot Normal
Goal: Donner la priorité aux groupes de couleur.
Description: Privilégier les achats et les échanges autorisés qui complètent ou rapprochent le robot d’un groupe complet. Vérifier son comportement quand plusieurs groupes sont possibles et quand son solde limite les achats.

## 26. Écrire les décisions du robot Difficile
Goal: Évaluer les enchères, les échanges et les constructions selon les règles actives.
Description: Définir des critères de décision pour plafonner une enchère, évaluer une proposition et choisir où construire. Vérifier les décisions avec des situations où les options de partie changent les actions possibles.

## 27. Créer l’écran de lancement local
Goal: Démarrer une partie solo ou sur un appareil partagé.
Description: Permettre de choisir le plateau, la variante, les options, les joueurs, leurs pions et la difficulté commune des robots. Afficher les pions déjà pris et refuser une configuration hors de la limite de deux à six joueurs.

## 28. Afficher le plateau sur PC et mobile
Goal: Rendre toutes les cases lisibles et consultables à la souris ou au toucher.
Description: Afficher les cases, groupes de couleur, pions et monuments à partir des données de la ville choisie. Vérifier le rendu d’un petit écran en portrait et d’un écran de PC avec le plateau de Paris.

## 29. Afficher l’état du joueur et ses actions courantes
Goal: Permettre de jouer un tour depuis le plateau.
Description: Afficher le joueur actif, le solde, les propriétés et les actions disponibles, dont le lancer, l’achat, le refus et la fin de tour. En mode appareil partagé, indiquer clairement à qui passer l’appareil.

## 30. Ajouter l’interface des enchères
Goal: Permettre de suivre une enchère et de soumettre une offre.
Description: Afficher la propriété, la meilleure offre, le meneur et le résultat de l’enchère. En ligne, afficher le temps restant communiqué par le serveur et signaler les offres refusées.

## 31. Ajouter l’interface de gestion des propriétés
Goal: Permettre de construire, vendre des bâtiments et hypothéquer depuis le jeu.
Description: Afficher le groupe, les bâtiments, le statut d’hypothèque et les montants associés aux actions. Actualiser les choix affichés après chaque action et au changement de tour.

## 32. Ajouter l’interface des échanges
Goal: Négocier des biens et de l’argent pendant une partie.
Description: Permettre de composer une proposition, puis de l’accepter, de la refuser ou de faire une contre-offre. Afficher son expiration et le résultat final aux deux participants.

## 33. Ajouter l’interface des dettes et des prêts
Goal: Donner accès aux échéances et aux actions de règlement.
Description: Afficher les créanciers, les montants restant dus et les échéances. Permettre de proposer ou d’accepter un prêt, un versement partiel ou une cession de propriété selon les actions autorisées.

## 34. Afficher la fin de partie
Goal: Présenter le vainqueur ou le classement final.
Description: Afficher le dernier joueur restant en Classique et le détail des montants du patrimoine en Express et Chrono. Gérer les victoires ex æquo et donner accès à l’écran de lancement.

## 35. Sauvegarder et reprendre une partie locale
Goal: Retrouver une partie solo ou partagée après fermeture du navigateur.
Description: Enregistrer dans IndexedDB un état de partie versionné après chaque action validée, avec le tour et les étapes en cours. Ajouter une action de reprise et vérifier qu’une réouverture restaure le même état.

## 36. Rendre la PWA installable et jouable hors ligne
Goal: Ouvrir le jeu local après installation et mise en cache.
Description: Ajouter le manifeste et la mise en cache de l’interface et des données nécessaires à une partie locale. Vérifier sur PC, iPhone et Android qu’un plateau mis en cache peut être joué et qu’une sauvegarde peut être reprise après coupure du réseau.

## 37. Synchroniser une partie avec Colyseus
Goal: Faire du serveur la référence de l’état de la partie en ligne.
Description: Relier une salle Colyseus au moteur TypeScript partagé et valider chaque action reçue avant de diffuser le nouvel état. Vérifier que plusieurs clients voient le même état et qu’une action interdite ne le modifie pas.

## 38. Créer et rejoindre une salle privée
Goal: Permettre à des amis de jouer ensemble avec un pseudo et un code.
Description: Générer un code d’invitation, permettre de rejoindre la salle sans compte et gérer le choix de pions disponibles. Donner au créateur le choix des options et la possibilité de compléter les places avec des robots, dans la limite de six joueurs.

## 39. Affecter les joueurs aux salles publiques
Goal: Placer chaque joueur en ligne dans une salle publique de la variante demandée.
Description: Utiliser le pseudo et la variante choisis pour rejoindre une salle disponible ou en ouvrir une. Tirer au sort une ville pour la salle entière et vérifier que les arrivées simultanées respectent la capacité.

## 40. Déclencher le départ des salles publiques
Goal: Lancer automatiquement la partie au bon moment.
Description: Démarrer dès quatre joueurs, ou après cinq minutes avec trois humains ou deux humains et un robot. Appliquer les décisions validées à la tâche 2 pour les salles moins remplies et la difficulté du robot.

## 41. Appliquer le délai de tour en ligne
Goal: Faire passer le tour automatiquement à son expiration.
Description: Gérer côté serveur le délai configuré à la création, de 30 secondes par défaut, et communiquer l’échéance aux clients. Vérifier qu’une action reçue juste après l’expiration ne peut pas modifier le tour précédent.

## 42. Appliquer le chronomètre des enchères en ligne
Goal: Faire respecter la durée de chaque enchère côté serveur.
Description: Démarrer à 20 secondes et ramener le temps restant à cinq secondes lorsqu’une offre valide arrive pendant les cinq dernières secondes. À l’expiration, résoudre l’enchère et communiquer l’échéance actualisée à tous les clients.

## 43. Reconnecter ou éliminer un joueur absent
Goal: Faire continuer la partie en ligne pendant une déconnexion.
Description: Sauter les tours du joueur absent et lui rendre sa place s’il revient avant la fin de son troisième tour de table complet d’absence. Au-delà, l’éliminer et lancer la liquidation prévue aux tâches 17 et 18.

## 44. Brancher les robots sur les trois modes de jeu
Goal: Permettre aux robots de compléter une partie locale ou en ligne.
Description: Exécuter les décisions des robots sur l’appareil en solo et en mode partagé, puis côté serveur dans les salles en ligne. Vérifier qu’ils utilisent les mêmes actions que les humains, partagent une difficulté commune et jouent aussi pendant les enchères.

## 45. Afficher le catalogue des villes
Goal: Présenter les 55 plateaux dans une liste alphabétique.
Description: Afficher les noms français du cahier des charges et charger les données et illustrations du plateau choisi. Formater les prix et soldes dans la devise locale en conservant les mêmes montants numériques.

## 46. Fixer les paramètres communs du plateau
Goal: Disposer des règles chiffrées nécessaires au moteur.
Description: Relever les valeurs et effets encore absents du cahier des charges, dont le solde initial, les loyers, les coûts de bâtiment et les montants d’hypothèque. Faire valider une grille commune et les effets de chaque type de case.

## 47. Créer le catalogue commun des pions
Goal: Proposer des pions distincts sur tous les plateaux.
Description: Choisir et illustrer au moins six pions reconnaissables sur un écran mobile. Associer à chacun un identifiant stable et un libellé pour sa sélection.

## 48. Ajouter l’écran des salles privées
Goal: Permettre de créer une salle et de s’y retrouver entre amis.
Description: Afficher le code d’invitation et la liste des participants dans la salle. Permettre de saisir un pseudo et un code pour rejoindre, puis de choisir un pion libre.

## 49. Ajouter l’écran des parties publiques
Goal: Permettre de rejoindre une file d’attente et de suivre son départ.
Description: Demander un pseudo et une variante, puis afficher la ville tirée au sort, les participants et le temps d’attente restant. Ouvrir le plateau au démarrage de la partie et afficher le résultat si l’attente prend fin sans départ.

## 50. Illustrer le plateau de Paris
Goal: Afficher deux à trois monuments facilement reconnaissables.
Description: Préparer les illustrations sélectionnées dans la fiche de Paris et les associer au centre du plateau ainsi qu’aux cases correspondantes. Vérifier leur lisibilité et consigner leur provenance.

## 51. Vérifier le parcours local
Goal: Rejouer les parcours solo et sur appareil partagé sur PC, iPhone et Android.
Description: Tester le lancement, une partie avec robot, le passage d’appareil et la reprise après fermeture. Vérifier aussi la reprise après coupure du réseau sur un plateau mis en cache.

## 52. Vérifier le parcours en ligne
Goal: Valider les interactions entre clients sur des appareils différents.
Description: Tester une salle privée et une salle publique, puis provoquer une expiration de tour, une prolongation d’enchère et une déconnexion suivie d’un retour. Vérifier que les appareils convergent vers le même état et affichent le même résultat final.

## 53. Renseigner les plateaux de Athènes et Bandung
Goal: Valider les fiches de Athènes et Bandung.
Description: Pour chaque ville, renseigner la devise, les rues ou quartiers par groupe de prestige, la gare, l’aéroport et deux lieux emblématiques. Choisir deux à trois monuments par plateau et valider chaque fiche avec le format de la tâche 3.

## 54. Renseigner les plateaux de Bangkok et Barcelone
Goal: Valider les fiches de Bangkok et Barcelone.
Description: Pour chaque ville, renseigner la devise, les rues ou quartiers par groupe de prestige, la gare, l’aéroport et deux lieux emblématiques. Choisir deux à trois monuments par plateau et valider chaque fiche avec le format de la tâche 3.

## 55. Renseigner les plateaux de Berlin et Birmingham
Goal: Valider les fiches de Berlin et Birmingham.
Description: Pour chaque ville, renseigner la devise, les rues ou quartiers par groupe de prestige, la gare, l’aéroport et deux lieux emblématiques. Choisir deux à trois monuments par plateau et valider chaque fiche avec le format de la tâche 3.

## 56. Renseigner les plateaux de Bogotá et Buenos Aires
Goal: Valider les fiches de Bogotá et Buenos Aires.
Description: Pour chaque ville, renseigner la devise, les rues ou quartiers par groupe de prestige, la gare, l’aéroport et deux lieux emblématiques. Choisir deux à trois monuments par plateau et valider chaque fiche avec le format de la tâche 3.

## 57. Renseigner les plateaux de Calcutta (Kolkata) et Canton (Guangzhou)
Goal: Valider les fiches de Calcutta (Kolkata) et Canton (Guangzhou).
Description: Pour chaque ville, renseigner la devise, les rues ou quartiers par groupe de prestige, la gare, l’aéroport et deux lieux emblématiques. Choisir deux à trois monuments par plateau et valider chaque fiche avec le format de la tâche 3.

## 58. Renseigner les plateaux de Chicago et Essen–Duisbourg (Ruhr)
Goal: Valider les fiches de Chicago et Essen–Duisbourg (Ruhr).
Description: Pour chaque ville, renseigner la devise, les rues ou quartiers par groupe de prestige, la gare, l’aéroport et deux lieux emblématiques. Choisir deux à trois monuments par plateau et valider chaque fiche avec le format de la tâche 3. Pour le plateau commun, choisir les lieux à l’échelle de toute l’agglomération.

## 59. Renseigner les plateaux de Guadalajara et Hô Chi Minh-Ville
Goal: Valider les fiches de Guadalajara et Hô Chi Minh-Ville.
Description: Pour chaque ville, renseigner la devise, les rues ou quartiers par groupe de prestige, la gare, l’aéroport et deux lieux emblématiques. Choisir deux à trois monuments par plateau et valider chaque fiche avec le format de la tâche 3.

## 60. Renseigner les plateaux de Houston et Istanbul
Goal: Valider les fiches de Houston et Istanbul.
Description: Pour chaque ville, renseigner la devise, les rues ou quartiers par groupe de prestige, la gare, l’aéroport et deux lieux emblématiques. Choisir deux à trois monuments par plateau et valider chaque fiche avec le format de la tâche 3.

## 61. Renseigner les plateaux de Kinshasa et Kuala Lumpur
Goal: Valider les fiches de Kinshasa et Kuala Lumpur.
Description: Pour chaque ville, renseigner la devise, les rues ou quartiers par groupe de prestige, la gare, l’aéroport et deux lieux emblématiques. Choisir deux à trois monuments par plateau et valider chaque fiche avec le format de la tâche 3.

## 62. Renseigner les plateaux de Kyiv et Lagos
Goal: Valider les fiches de Kyiv et Lagos.
Description: Pour chaque ville, renseigner la devise, les rues ou quartiers par groupe de prestige, la gare, l’aéroport et deux lieux emblématiques. Choisir deux à trois monuments par plateau et valider chaque fiche avec le format de la tâche 3.

## 63. Renseigner les plateaux de Lahore et Las Vegas
Goal: Valider les fiches de Lahore et Las Vegas.
Description: Pour chaque ville, renseigner la devise, les rues ou quartiers par groupe de prestige, la gare, l’aéroport et deux lieux emblématiques. Choisir deux à trois monuments par plateau et valider chaque fiche avec le format de la tâche 3. Pour Las Vegas, classer les hôtels-casinos par prestige et choisir quatre attractions à la place des gares.

## 64. Renseigner les plateaux de Le Caire et Lima
Goal: Valider les fiches de Le Caire et Lima.
Description: Pour chaque ville, renseigner la devise, les rues ou quartiers par groupe de prestige, la gare, l’aéroport et deux lieux emblématiques. Choisir deux à trois monuments par plateau et valider chaque fiche avec le format de la tâche 3.

## 65. Renseigner les plateaux de Londres et Los Angeles
Goal: Valider les fiches de Londres et Los Angeles.
Description: Pour chaque ville, renseigner la devise, les rues ou quartiers par groupe de prestige, la gare, l’aéroport et deux lieux emblématiques. Choisir deux à trois monuments par plateau et valider chaque fiche avec le format de la tâche 3.

## 66. Renseigner les plateaux de Madrid et Manille
Goal: Valider les fiches de Madrid et Manille.
Description: Pour chaque ville, renseigner la devise, les rues ou quartiers par groupe de prestige, la gare, l’aéroport et deux lieux emblématiques. Choisir deux à trois monuments par plateau et valider chaque fiche avec le format de la tâche 3.

## 67. Renseigner les plateaux de Mexico et Miami
Goal: Valider les fiches de Mexico et Miami.
Description: Pour chaque ville, renseigner la devise, les rues ou quartiers par groupe de prestige, la gare, l’aéroport et deux lieux emblématiques. Choisir deux à trois monuments par plateau et valider chaque fiche avec le format de la tâche 3.

## 68. Renseigner les plateaux de Milan et Monterrey
Goal: Valider les fiches de Milan et Monterrey.
Description: Pour chaque ville, renseigner la devise, les rues ou quartiers par groupe de prestige, la gare, l’aéroport et deux lieux emblématiques. Choisir deux à trois monuments par plateau et valider chaque fiche avec le format de la tâche 3.

## 69. Renseigner les plateaux de Montréal et Moscou
Goal: Valider les fiches de Montréal et Moscou.
Description: Pour chaque ville, renseigner la devise, les rues ou quartiers par groupe de prestige, la gare, l’aéroport et deux lieux emblématiques. Choisir deux à trois monuments par plateau et valider chaque fiche avec le format de la tâche 3.

## 70. Renseigner les plateaux de Mumbai et Naples
Goal: Valider les fiches de Mumbai et Naples.
Description: Pour chaque ville, renseigner la devise, les rues ou quartiers par groupe de prestige, la gare, l’aéroport et deux lieux emblématiques. Choisir deux à trois monuments par plateau et valider chaque fiche avec le format de la tâche 3.

## 71. Renseigner les plateaux de New Delhi et New York
Goal: Valider les fiches de New Delhi et New York.
Description: Pour chaque ville, renseigner la devise, les rues ou quartiers par groupe de prestige, la gare, l’aéroport et deux lieux emblématiques. Choisir deux à trois monuments par plateau et valider chaque fiche avec le format de la tâche 3.

## 72. Renseigner les plateaux de Osaka et Pékin
Goal: Valider les fiches de Osaka et Pékin.
Description: Pour chaque ville, renseigner la devise, les rues ou quartiers par groupe de prestige, la gare, l’aéroport et deux lieux emblématiques. Choisir deux à trois monuments par plateau et valider chaque fiche avec le format de la tâche 3.

## 73. Renseigner les plateaux de Rio de Janeiro et Saint-Domingue
Goal: Valider les fiches de Rio de Janeiro et Saint-Domingue.
Description: Pour chaque ville, renseigner la devise, les rues ou quartiers par groupe de prestige, la gare, l’aéroport et deux lieux emblématiques. Choisir deux à trois monuments par plateau et valider chaque fiche avec le format de la tâche 3.

## 74. Renseigner les plateaux de Saint-Pétersbourg et San Francisco–San José
Goal: Valider les fiches de Saint-Pétersbourg et San Francisco–San José.
Description: Pour chaque ville, renseigner la devise, les rues ou quartiers par groupe de prestige, la gare, l’aéroport et deux lieux emblématiques. Choisir deux à trois monuments par plateau et valider chaque fiche avec le format de la tâche 3. Pour le plateau commun, choisir les lieux à l’échelle de toute l’agglomération.

## 75. Renseigner les plateaux de São Paulo et Séoul
Goal: Valider les fiches de São Paulo et Séoul.
Description: Pour chaque ville, renseigner la devise, les rues ou quartiers par groupe de prestige, la gare, l’aéroport et deux lieux emblématiques. Choisir deux à trois monuments par plateau et valider chaque fiche avec le format de la tâche 3.

## 76. Renseigner les plateaux de Shanghai et Shenzhen
Goal: Valider les fiches de Shanghai et Shenzhen.
Description: Pour chaque ville, renseigner la devise, les rues ou quartiers par groupe de prestige, la gare, l’aéroport et deux lieux emblématiques. Choisir deux à trois monuments par plateau et valider chaque fiche avec le format de la tâche 3.

## 77. Renseigner les plateaux de Singapour et Taipei
Goal: Valider les fiches de Singapour et Taipei.
Description: Pour chaque ville, renseigner la devise, les rues ou quartiers par groupe de prestige, la gare, l’aéroport et deux lieux emblématiques. Choisir deux à trois monuments par plateau et valider chaque fiche avec le format de la tâche 3.

## 78. Renseigner les plateaux de Téhéran et Tokyo
Goal: Valider les fiches de Téhéran et Tokyo.
Description: Pour chaque ville, renseigner la devise, les rues ou quartiers par groupe de prestige, la gare, l’aéroport et deux lieux emblématiques. Choisir deux à trois monuments par plateau et valider chaque fiche avec le format de la tâche 3.

## 79. Renseigner les plateaux de Toronto et Washington D.C.
Goal: Valider les fiches de Toronto et Washington D.C..
Description: Pour chaque ville, renseigner la devise, les rues ou quartiers par groupe de prestige, la gare, l’aéroport et deux lieux emblématiques. Choisir deux à trois monuments par plateau et valider chaque fiche avec le format de la tâche 3.

## 80. Illustrer les plateaux de Athènes et Bandung
Goal: Afficher les monuments de Athènes et Bandung.
Description: Préparer deux à trois illustrations par plateau à partir des monuments sélectionnés dans les fiches des villes concernées. Les associer au centre du plateau et aux cases correspondantes, puis vérifier leur lisibilité et consigner leur provenance.

## 81. Illustrer les plateaux de Bangkok et Barcelone
Goal: Afficher les monuments de Bangkok et Barcelone.
Description: Préparer deux à trois illustrations par plateau à partir des monuments sélectionnés dans les fiches des villes concernées. Les associer au centre du plateau et aux cases correspondantes, puis vérifier leur lisibilité et consigner leur provenance.

## 82. Illustrer les plateaux de Berlin et Birmingham
Goal: Afficher les monuments de Berlin et Birmingham.
Description: Préparer deux à trois illustrations par plateau à partir des monuments sélectionnés dans les fiches des villes concernées. Les associer au centre du plateau et aux cases correspondantes, puis vérifier leur lisibilité et consigner leur provenance.

## 83. Illustrer les plateaux de Bogotá et Buenos Aires
Goal: Afficher les monuments de Bogotá et Buenos Aires.
Description: Préparer deux à trois illustrations par plateau à partir des monuments sélectionnés dans les fiches des villes concernées. Les associer au centre du plateau et aux cases correspondantes, puis vérifier leur lisibilité et consigner leur provenance.

## 84. Illustrer les plateaux de Calcutta (Kolkata) et Canton (Guangzhou)
Goal: Afficher les monuments de Calcutta (Kolkata) et Canton (Guangzhou).
Description: Préparer deux à trois illustrations par plateau à partir des monuments sélectionnés dans les fiches des villes concernées. Les associer au centre du plateau et aux cases correspondantes, puis vérifier leur lisibilité et consigner leur provenance.

## 85. Illustrer les plateaux de Chicago et Essen–Duisbourg (Ruhr)
Goal: Afficher les monuments de Chicago et Essen–Duisbourg (Ruhr).
Description: Préparer deux à trois illustrations par plateau à partir des monuments sélectionnés dans les fiches des villes concernées. Les associer au centre du plateau et aux cases correspondantes, puis vérifier leur lisibilité et consigner leur provenance.

## 86. Illustrer les plateaux de Guadalajara et Hô Chi Minh-Ville
Goal: Afficher les monuments de Guadalajara et Hô Chi Minh-Ville.
Description: Préparer deux à trois illustrations par plateau à partir des monuments sélectionnés dans les fiches des villes concernées. Les associer au centre du plateau et aux cases correspondantes, puis vérifier leur lisibilité et consigner leur provenance.

## 87. Illustrer les plateaux de Houston et Istanbul
Goal: Afficher les monuments de Houston et Istanbul.
Description: Préparer deux à trois illustrations par plateau à partir des monuments sélectionnés dans les fiches des villes concernées. Les associer au centre du plateau et aux cases correspondantes, puis vérifier leur lisibilité et consigner leur provenance.

## 88. Illustrer les plateaux de Kinshasa et Kuala Lumpur
Goal: Afficher les monuments de Kinshasa et Kuala Lumpur.
Description: Préparer deux à trois illustrations par plateau à partir des monuments sélectionnés dans les fiches des villes concernées. Les associer au centre du plateau et aux cases correspondantes, puis vérifier leur lisibilité et consigner leur provenance.

## 89. Illustrer les plateaux de Kyiv et Lagos
Goal: Afficher les monuments de Kyiv et Lagos.
Description: Préparer deux à trois illustrations par plateau à partir des monuments sélectionnés dans les fiches des villes concernées. Les associer au centre du plateau et aux cases correspondantes, puis vérifier leur lisibilité et consigner leur provenance.

## 90. Illustrer les plateaux de Lahore et Las Vegas
Goal: Afficher les monuments de Lahore et Las Vegas.
Description: Préparer deux à trois illustrations par plateau à partir des monuments sélectionnés dans les fiches des villes concernées. Les associer au centre du plateau et aux cases correspondantes, puis vérifier leur lisibilité et consigner leur provenance.

## 91. Illustrer les plateaux de Le Caire et Lima
Goal: Afficher les monuments de Le Caire et Lima.
Description: Préparer deux à trois illustrations par plateau à partir des monuments sélectionnés dans les fiches des villes concernées. Les associer au centre du plateau et aux cases correspondantes, puis vérifier leur lisibilité et consigner leur provenance.

## 92. Illustrer les plateaux de Londres et Los Angeles
Goal: Afficher les monuments de Londres et Los Angeles.
Description: Préparer deux à trois illustrations par plateau à partir des monuments sélectionnés dans les fiches des villes concernées. Les associer au centre du plateau et aux cases correspondantes, puis vérifier leur lisibilité et consigner leur provenance.

## 93. Illustrer les plateaux de Madrid et Manille
Goal: Afficher les monuments de Madrid et Manille.
Description: Préparer deux à trois illustrations par plateau à partir des monuments sélectionnés dans les fiches des villes concernées. Les associer au centre du plateau et aux cases correspondantes, puis vérifier leur lisibilité et consigner leur provenance.

## 94. Illustrer les plateaux de Mexico et Miami
Goal: Afficher les monuments de Mexico et Miami.
Description: Préparer deux à trois illustrations par plateau à partir des monuments sélectionnés dans les fiches des villes concernées. Les associer au centre du plateau et aux cases correspondantes, puis vérifier leur lisibilité et consigner leur provenance.

## 95. Illustrer les plateaux de Milan et Monterrey
Goal: Afficher les monuments de Milan et Monterrey.
Description: Préparer deux à trois illustrations par plateau à partir des monuments sélectionnés dans les fiches des villes concernées. Les associer au centre du plateau et aux cases correspondantes, puis vérifier leur lisibilité et consigner leur provenance.

## 96. Illustrer les plateaux de Montréal et Moscou
Goal: Afficher les monuments de Montréal et Moscou.
Description: Préparer deux à trois illustrations par plateau à partir des monuments sélectionnés dans les fiches des villes concernées. Les associer au centre du plateau et aux cases correspondantes, puis vérifier leur lisibilité et consigner leur provenance.

## 97. Illustrer les plateaux de Mumbai et Naples
Goal: Afficher les monuments de Mumbai et Naples.
Description: Préparer deux à trois illustrations par plateau à partir des monuments sélectionnés dans les fiches des villes concernées. Les associer au centre du plateau et aux cases correspondantes, puis vérifier leur lisibilité et consigner leur provenance.

## 98. Illustrer les plateaux de New Delhi et New York
Goal: Afficher les monuments de New Delhi et New York.
Description: Préparer deux à trois illustrations par plateau à partir des monuments sélectionnés dans les fiches des villes concernées. Les associer au centre du plateau et aux cases correspondantes, puis vérifier leur lisibilité et consigner leur provenance.

## 99. Illustrer les plateaux de Osaka et Pékin
Goal: Afficher les monuments de Osaka et Pékin.
Description: Préparer deux à trois illustrations par plateau à partir des monuments sélectionnés dans les fiches des villes concernées. Les associer au centre du plateau et aux cases correspondantes, puis vérifier leur lisibilité et consigner leur provenance.

## 100. Illustrer les plateaux de Rio de Janeiro et Saint-Domingue
Goal: Afficher les monuments de Rio de Janeiro et Saint-Domingue.
Description: Préparer deux à trois illustrations par plateau à partir des monuments sélectionnés dans les fiches des villes concernées. Les associer au centre du plateau et aux cases correspondantes, puis vérifier leur lisibilité et consigner leur provenance.

## 101. Illustrer les plateaux de Saint-Pétersbourg et San Francisco–San José
Goal: Afficher les monuments de Saint-Pétersbourg et San Francisco–San José.
Description: Préparer deux à trois illustrations par plateau à partir des monuments sélectionnés dans les fiches des villes concernées. Les associer au centre du plateau et aux cases correspondantes, puis vérifier leur lisibilité et consigner leur provenance.

## 102. Illustrer les plateaux de São Paulo et Séoul
Goal: Afficher les monuments de São Paulo et Séoul.
Description: Préparer deux à trois illustrations par plateau à partir des monuments sélectionnés dans les fiches des villes concernées. Les associer au centre du plateau et aux cases correspondantes, puis vérifier leur lisibilité et consigner leur provenance.

## 103. Illustrer les plateaux de Shanghai et Shenzhen
Goal: Afficher les monuments de Shanghai et Shenzhen.
Description: Préparer deux à trois illustrations par plateau à partir des monuments sélectionnés dans les fiches des villes concernées. Les associer au centre du plateau et aux cases correspondantes, puis vérifier leur lisibilité et consigner leur provenance.

## 104. Illustrer les plateaux de Singapour et Taipei
Goal: Afficher les monuments de Singapour et Taipei.
Description: Préparer deux à trois illustrations par plateau à partir des monuments sélectionnés dans les fiches des villes concernées. Les associer au centre du plateau et aux cases correspondantes, puis vérifier leur lisibilité et consigner leur provenance.

## 105. Illustrer les plateaux de Téhéran et Tokyo
Goal: Afficher les monuments de Téhéran et Tokyo.
Description: Préparer deux à trois illustrations par plateau à partir des monuments sélectionnés dans les fiches des villes concernées. Les associer au centre du plateau et aux cases correspondantes, puis vérifier leur lisibilité et consigner leur provenance.

## 106. Illustrer les plateaux de Toronto et Washington D.C.
Goal: Afficher les monuments de Toronto et Washington D.C..
Description: Préparer deux à trois illustrations par plateau à partir des monuments sélectionnés dans les fiches des villes concernées. Les associer au centre du plateau et aux cases correspondantes, puis vérifier leur lisibilité et consigner leur provenance.


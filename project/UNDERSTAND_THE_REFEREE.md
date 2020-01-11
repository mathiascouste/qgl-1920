# Comprendre l'arbitre

*A compléter...*

## Déroulé d'une partie
### Initialisation de la partie
### Exécution d'un tour

## Exécutions des actions
A chaque tour, chaque matelot ne peut faire qu’une seule action.
Seule exception le déplacement. En effet, un marin peut se déplacer et exécuter une action.

Avant d’effectuer la moindre action, l’arbitre vérifie les conditions d’activation de cette dernière. En cas de non validité de l’action cette dernière est ignorée.

Les actions sont exécutées par l’arbitre dans l’ordre suivant:
 1. Déplacement de marin
 2.  Ramage
 3.  Hissage de voile
 4.  Affalage de voile
 5.  Actionnage du gouvernail
 6.  Monter la garde
 7.  Orienter canon
 8.  Charger canon
 9.  Tirer au canon
 
## Déplacements
Un tour dans le jeu représente une trentaine de seconde dans la vrai vie.

### Calcul de la vitesse linéaire
La vitesse linéaire est la combinaison des vitesses (vecteurs) suivantes:

#### Vitesse des rames:

-   Direction: direction du bateau
-   Valeur: 165 x nombre de rames active / nombre total de rames
#### Vitesse du vent:

-   Direction: direction du bateau
-   Valeur: (nombre de voile ouverte / nombre de voile) x vitesse du vent x cosinus(angle entre la direction du vent et la direction du bateau)
    

#### Vitesse du courant:

Uniquement si le bateau est en contact avec un ou plusieurs courant.
-   Direction: direction du courant
-   Valeur: force du courant
    

### Calcul de la vitesse angulaire
La vitesse angulaire est la somme des vitesses angulaires suivantes:

#### Vitesse des rames:
La vitesse radiale issue des rames est comprise entre -PI/2 et PI/2.

Cet angle est découpé en n+1 parts (n étant égal au nombre total de rames).

Exemple: un bateau possédant 4 rames (2 de chaque côté) peut avoir les vitesses radiales suivantes: -PI/2, -PI/4, 0, PI/4, et PI/2.

Chaque rames actionnées d’une coté du bateau tend à l’orienter vers le côté opposé.

*Exemple:*

| Rames actives à bâbord | Rames actives à tribord | Vitesse angulaire |
|--|--|--|
| 0 | 0 | 0 |
| 0 | 1 | PI/4 |
| 0 | 2 | PI/2 |
| 1 | 0 | -PI/4 |
| 1 | 1 | 0 |
| 1 | 2 | PI/4 |
| 2 | 0 | -PI/2 |
| 2 | 1 | -PI/4 |
| 2 | 2 | 0 |
#### Vitesse angulaire du gouvernail:

L’angle induit par le gouvernail est de zéro s’il n’est pas utilisé.  
Si le gouvernail est utilisé, l’angle induit correspond à l’angle du gouvernail (donné en paramètre de l’action d’activation).  
Si aucune action d’actionnage du gouvernail est envoyée pendant un tour, l’angle est de zéro.

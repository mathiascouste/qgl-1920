# Spécifications techniques

*A compléter...*

## Structure du projet
Votre projet doit conserver la structure telle que donnée dans le [template](https://github.com/mathiascouste/qgl-template).

Lorsque la commande `mvn clean package` est exécutée, un fichier jar nommé `<teamId>-0.1-SNAPSHOT.jar` doit être présent dans le répertoire `target`.

## Librairie externes
Si vous ressentez le besoin d’utiliser une librairie externe, cette dernière doit être présente dans [le repository maven officiel](https://mvnrepository.com/).

De plus, il est obligatoire de prévenir le responsable du module au moins 5 jours avant la livraison de la semaine. S’il accepte, il vous donnera la version de la librairie dont vous avez besoin. Et indiquera aux autres équipes la disponibilité de cette librairie pour tous via le canal de diffusion officiel.

## Cockpit.java
Votre projet doit obligatoirement contenir une classe nommée `Cockpit` tel que donnée dans le [template](https://github.com/mathiascouste/qgl-template/blob/master/src/main/java/fr/unice/polytech/si3/qgl/teamid/Cockpit.java).  
Cette classe doit être positionnée dans le package `fr.unice.polytech.si3.qgl.<teamid>`.

La classe Cockpit doit contenir les deux méthodes suivantes:

    public void initGame(String game);

Cette méthode sera invoquée avec en paramètre une instance de String contenant

un JSON au format initGame (voir plus bas).

    public String nextRound(String round);
    

Cette méthode sera invoquée avec en paramètre une instance de String contenant un JSON au format nextRound (voir plus bas).

Cette méthode doit retourner une instance de String contenant un JSON au format actions (voir plus bas).

## Interfaces JSON
### initGame

### nextRound

### actions


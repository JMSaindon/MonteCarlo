<img align="left" height="160" src=img/logotrans.png>

Le contenu de ce dépôt correspond à un rendu de TP dans le cadre de l'option IA enseignée à l'Enseirb-Matmeca. Cela vaut pour le module de Représentation des connaissances. Le TP choisi présente différentes méthodes permettant de jouer au jeu Réversi et notamment le Monte Carlo Tree Search.   

Auteur : Jean-Marie Saindon      
Encadrant : Laurent Simon  

---

# Monte Carlo

## Quickstart
- modules nécessaires: numpy et matplotlib
- ré-utilisation partielle du code du projet de l'an passé
- [myPlayer.py](myPlayer.py) contient le code de Monte Carlo, Iterative deepening, AlphaBeta (NegAlphaBeta), MinMax (NegaMax)
- [myPlayer.py](myPlayer.py) contient également les heuristiques Parity et Ultimate (Trouvée l'an dernier)
- le dossier [specialplayers](specialplayers) contient des joueurs utilisant des stratégies variées (pour faire des matchs)

### commandes
```
$ python localGame.py                 #permet un affrontemment entre 2 joueurs (myPlayer ou specialplayers)
$ python localGameMultiExecution.py   #lance plusieurs duels entre 2 joueurs faire des statistiques
$ python plotComparison.py            #graphique des performances de plusieurs joueurs contre le randomPlayer
```

## Description

### Implémentation

L'implémentation se base sur le code python fournit pour l'environnement de jeu Reversi. Elle ré-utilise une partie de ce qui avait été développé l'an dernier dans le cadre du projet. Ainsi, en plus du Monte Carlo, on retrouve le MinMax et le AlphaBeta avec leurs heuristiques (Parity et Ultimate). Ultimate est l'heuristique trouvée l'an dernier. J'ai également ajouté les versions NegaMax et NegAlphaBeta ainsi qu'un iterative deepening à mon code pour avoir un opposant de taille à se mesurer à mon Monte Carlo tree search.

Deux implémentations de Monte Carlo sont disponibles dans le code du fichier [myPlayer.py](myPlayer.py). L'une effectue un nombre de tree walk donné (MonteCarlo) et l'autre en effectue autant qu'elle peut dans un temps imparti (MonteCarloTime).

les [specialplayers](specialplayers) contiennent des versions réduites des stratégies de [myPlayer.py](myPlayer.py) et permettent de facilement faire des affrontemments et donc des tests. Ils utilisent principalement des iterative deepening pour pouvoir leur donner un temps de recherche par coup équivalent. A noter que je n'ai pas eu le temps de parfaitement terminer le iterative deepening et qu'il dépasse le temps imparti mais renvoi bien le move qu'il devrait s'il le respectait (une version devant bien interrompre l'execution était en cours mais n'a pas donné de résultats satisfaisants et n'a donc pas été inclue dans le code).

### Tests et Résultats

Monte Carlo a été testé de différentes manières, contre lui-même dans [localGame.py](localGame.py) et contre les [specialplayers](specialplayers).

Globalement, le résultat obtenu en testant tous mes joueurs contre un randomPlayer sur 100 confrontations en faisant varier le temps de recherche par coups (horizon) donne :

<p align="center">
  <img src=img/graphmontecarlo.png>
</p>

Monte Carlo parvient au cours du temps à tirer son épingle du jeu en obtenant un score parfait contre le randomPlayer à partir de l'horizon d'une seconde mais reste inférieur à la combinaison iterative deepening - alpha beta - heuristique ultimate.

<p align="center">
  <img width="650" src=img/res.PNG>
</p>

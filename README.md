<img align="left" height="160" src=img/logotrans.png>

Le contenu de ce dépôt correspond à un rendu de TP dans le cadre de l'option IA enseignée à l'Enseirb-Matmeca. Cela vaut pour le module de Représentation des connaissances. Le TP choisi présente différentes méthodes permettant de jouer au jeu Réversi et notamment le Monte Carlo Tree Search.   

Auteur : Jean-Marie Saindon      
Encadrant : Laurent Simon  

---

# Monte Carlo

## Quickstart
- modules nécessaires: numpy et matplotlib
- ré-utilisation partielle du code du projet de l'an passé
- myPlayer contient le code de Monte Carlo, Iterative deepening, AlphaBeta (NegAlphaBeta), MinMax (NegaMax)
- myPlayer contient également les heuristiques Parity et Ultimate (Trouvée l'an dernier)

## commandes :
```
$ python localGame.py               #pour Monte Carlo vs Monte Carlo
$ python localGameMultiExecution.py #pour Monte Carlo vs RandomPlayer plusieurs fois
```

L'implémentation se base sur le code python fournit pour l'environnement de jeu Reversi. Elle ré-utilise une partie de ce qui avait été développé l'an dernier dans le cadre du projet. Ainsi, en plus du Monte Carlo, on retrouve le MinMax et le AlphaBeta avec leurs heuristiques (Parity et Ultimate). Ultimate est l'heuristique trouvée l'an dernier. J'ai également ajouté les versions NegaMax et NegAlphaBeta ainsi qu'un iterative deepening à mon code pour avoir un opposant de taille à se mesurer à mon Monte Carlo tree search (mon alphabeta associé a l'heuristique ultimate avait été plutôt performant l'an dernier)

Deux implémentations de Monte Carlo sont disponibles dans le code du fichier myPlayer.py. L'une effectue un nombre de tree walk donné MonteCarlo et l'autre en effectue autant qu'elle peut dans un temps imparti MonteCarloTime.

ultiPlayer.py contient sensiblement le même code que \textit{myPlayer.py} mais est destiné à lancer un Iterative deepening avec Alpha Beta et l'heuristique Ultimate lors de possibles affrontements)

Monte Carlo a été testé de différentes manières, contre des joueurs aléatoires (localGameWithRandom et localGameWithRandomMultiExecution), contre lui-même (localGame) et enfin contre ma meilleure alternative (ultiPlayer).

Le taux de réussite de Monte Carlo contre le RandomPlayer a été de ... contre ... pour ultiPlayer avec pour chacun un temps de réflexion de ... . Les matchs lancés entre MonteCarlo et ultiPlayer ont quasiment exclusivement abouti a des victoire de Monte Carlo pour des temps de réflexion équivalents.




<p align="center">
  <img width="650" src=img/GameOfLife.PNG>
</p>



Pour exécuter l'agent Q-learning dans Pacman, il semble que les instructions spécifiques ne soient pas directement disponibles sur la page web que nous avons consultée. Cependant, je peux vous donner des indications générales sur la façon dont on exécute généralement un agent Q-learning dans le cadre du projet Pacman de Berkeley :

1. Assurez-vous d'avoir téléchargé et installé le code source du projet Pacman de Berkeley.

2. Ouvrez un terminal et naviguez jusqu'au répertoire contenant les fichiers du projet Pacman.

3. La commande d'exécution typique pour un agent Pacman est généralement de la forme :

```
python pacman.py -p PacmanQAgent -x N -n M -l layout
```

Où :
- `-p PacmanQAgent` spécifie l'utilisation de l'agent Q-learning
- `-x N` définit le nombre N d'épisodes d'entraînement
- `-n M` définit le nombre total M d'épisodes (entraînement + test)
- `-l layout` spécifie le labyrinthe à utiliser

4. Pour démontrer l'impact de alpha (taux d'apprentissage), vous pouvez exécuter plusieurs fois la commande en modifiant la valeur de alpha :

```
python pacman.py -p PacmanQAgent -a alpha=0.1 -x 2000 -n 2100 -l smallGrid
python pacman.py -p PacmanQAgent -a alpha=0.5 -x 2000 -n 2100 -l smallGrid
python pacman.py -p PacmanQAgent -a alpha=0.9 -x 2000 -n 2100 -l smallGrid
```

5. Vous pouvez également ajouter l'option `-g DirectionalGhost` pour utiliser des fantômes directionnels, ce qui rend l'environnement plus difficile et peut mieux illustrer l'impact de alpha.

6. Pour visualiser les résultats, vous pouvez utiliser l'option `-q` qui désactive l'interface graphique et accélère l'exécution, puis rediriger la sortie vers un fichier pour une analyse ultérieure :

```
python pacman.py -p PacmanQAgent -a alpha=0.5 -x 2000 -n 2100 -l smallGrid -q > results_alpha_0.5.txt
```

N'oubliez pas que ces commandes sont basées sur la structure typique du projet Pacman de Berkeley. Si votre implémentation diffère, vous devrez peut-être ajuster ces commandes en conséquence.

Pour une démonstration efficace à vos étudiants, je vous recommande de préparer un script qui exécute automatiquement ces différentes configurations et qui trace ensuite les résultats (par exemple, le score moyen en fonction du nombre d'épisodes pour différentes valeurs de alpha) pour une comparaison visuelle claire.






---------------------
---------------------


Je comprends votre souhait d'avoir une démonstration plus courte. Pour exécuter l'agent Q-learning sur seulement 10 épisodes, vous pouvez modifier la commande de la manière suivante :

```
python pacman.py -p PacmanQAgent -n 10 -l smallGrid -a alpha=0.5,gamma=0.8,epsilon=0.1
```

Cette commande va :

1. Utiliser l'agent PacmanQAgent
2. Exécuter 10 épisodes au total (-n 10)
3. Utiliser le labyrinthe smallGrid
4. Définir alpha (taux d'apprentissage) à 0.5, gamma (facteur de réduction) à 0.8 et epsilon (taux d'exploration) à 0.1

Pour démontrer l'impact de alpha, vous pouvez exécuter plusieurs fois cette commande en changeant la valeur de alpha :

```
python pacman.py -p PacmanQAgent -n 10 -l smallGrid -a alpha=0.1,gamma=0.8,epsilon=0.1
python pacman.py -p PacmanQAgent -n 10 -l smallGrid -a alpha=0.5,gamma=0.8,epsilon=0.1
python pacman.py -p PacmanQAgent -n 10 -l smallGrid -a alpha=0.9,gamma=0.8,epsilon=0.1
```

Si vous voulez que l'agent apprenne pendant un certain nombre d'épisodes avant de le voir jouer, vous pouvez utiliser l'option -x. Par exemple, pour 8 épisodes d'entraînement et 2 de test :

```
python pacman.py -p PacmanQAgent -n 10 -x 8 -l smallGrid -a alpha=0.5,gamma=0.8,epsilon=0.1
```

Cela fera en sorte que l'agent s'entraîne pendant 8 épisodes (sans affichage graphique) et joue ensuite 2 épisodes que vous pourrez observer[1].

Pour ralentir l'affichage et mieux voir ce qui se passe, vous pouvez ajouter l'option --frameTime 0.1 (ou une autre valeur) à la commande[1].

Ces modifications devraient vous permettre d'avoir une démonstration plus courte et plus facile à observer pour vos étudiants, tout en montrant clairement l'impact de différentes valeurs de alpha sur l'apprentissage de l'agent.

Citations:
[1] https://stanford-cs221.github.io/spring2024/assignments/pacman/index.html
[2] https://courses.cs.washington.edu/courses/cse573/10au/pacman/reinforcement/docs/learningAgents.html
[3] https://ai.berkeley.edu/reinforcement.html

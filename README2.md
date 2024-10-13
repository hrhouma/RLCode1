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

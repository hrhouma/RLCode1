```cmd
C:\Python27>python --version ou C:\Python27\python.exe --version
C:\Python27> pip install virtualenv (si nécessaire dans un autre path pas dans celui de python2)
C:\Python27>python3 -m venv mon_env_python2
C:\Python27>mon_env_python2\Scripts\activate -p C:\Python27\python.exe mon_env_python2
ou C:\Python27>mon_env_python2\Scripts\activate -p python mon_env_python2
C:\Python27> cd C:\Users\rehou\Desktop\Apprentissage-Par-Renforcement-3
C:\Users\rehou\Desktop\Apprentissage-Par-Renforcement-3> C:\Python27\python.exe gridworld.py -a value -i 100 -k 10
doskey /history
```



# ou

```cmd
doskey /history
C:\Python27\Scripts\virtualenv.exe -p C:\Python27\python.exe mon_env_python2
mon_env_python2\Scripts\activate
python --version
python gridworld.py -a value -i 100 -k 10
python gridworld.py -a value -i 100 -k 10 -
python gridworld.py -g BookGrid -d 0.9 -r 0.1 -n 0.2 -a value -i 100 -k 10
python gridworld.py -i 10 --livingReward -2
python gridworld.py -a value -i 1 10 --livingReward -2
python gridworld.py -a value -i 1 100 --livingReward -2
Get-History
doskey /history
deactivate
doskey /history
```

```cmd
python -m venv mon_env_python3
mon_env_python3\Scripts\activate
python --version
python gridworld.py -a q -k 100 
python gridworld.py -a q -k 100 -g MazeGrid
python gridworld.py -g BridgeGrid --discount 0.9 --noise 0.2 -a value -i 100
python gridworld.py -g DiscountGrid -a value -i 100
python gridworld.py -a q -k 50 -n 0.3 -e 0.5
python gridworld.py -a q -k 50 --learningRate 0.8 --epsilon 0.2
python crawler.py
deactivate
doskey /history
```





## Convergence rapide

```
python gridworld.py -a q -k 50 -n 0.2 -e 0.1 -l 0.8 -g BridgeGrid
```

Cette commande utilise l'agent Q-learning sur BridgeGrid avec :
- 50 épisodes (-k 50)
- Un faible bruit de 0.2 (-n 0.2) 
- Une faible exploration de 0.1 (-e 0.1)
- Un taux d'apprentissage élevé de 0.8 (-l 0.8)

Ces paramètres favorisent une convergence rapide vers la politique optimale[1].

## Convergence lente

```
python gridworld.py -a q -k 100 -n 0.8 -e 0.5 -l 0.1 -g BridgeGrid
```

Ici, nous avons :
- 100 épisodes
- Un bruit élevé de 0.8
- Une exploration élevée de 0.5 
- Un faible taux d'apprentissage de 0.1

Ces paramètres ralentissent la convergence et peuvent mener à une politique sous-optimale[1].

## Démonstration de l'impact du discount

```
python gridworld.py -a q -k 50 -d 0.1 -g DiscountGrid
python gridworld.py -a q -k 50 -d 0.9 -g DiscountGrid
```

Ces commandes montrent comment le facteur de discount (0.1 vs 0.9) affecte la politique apprise sur DiscountGrid[2].

## Comparaison des algorithmes

```
python gridworld.py -a value -i 100 -k 10 -g MazeGrid
python gridworld.py -a q -k 100 -g MazeGrid
```

Ces commandes permettent de comparer l'itération de valeur et le Q-learning sur MazeGrid[3].

## Démonstration de l'apprentissage progressif

```
python gridworld.py -a q -k 1 -m -g BookGrid
python gridworld.py -a q -k 10 -m -g BookGrid
python gridworld.py -a q -k 50 -m -g BookGrid
```

Ces commandes montrent l'évolution de la politique apprise après 1, 10 et 50 épisodes en mode manuel (-m)[4].

Pour chaque exemple, vous pouvez expliquer à vos étudiants :
1. Les paramètres utilisés et leur signification
2. L'impact attendu sur l'apprentissage
3. L'observation des résultats (politique apprise, valeurs Q, etc.)
4. La comparaison avec les résultats théoriques ou attendus

N'oubliez pas d'adapter les chemins et versions selon votre configuration spécifique. Ces exemples devraient offrir une bonne base pour illustrer les concepts clés de l'apprentissage par renforcement à vos étudiants.



Pas de quiz cette semaine

## Vidéo 1 Programmation asynchrone

### Compléments Vidéo 1

### Exercices Vidéo 1



## Vidéo 2 Quelques exemples simples

### Compléments Vidéo 2

* citer https://en.wikipedia.org/wiki/Coroutine

### Exercices Vidéo 2



## Vidéo 3 `asyncio` : historique et écosystème

### Compléments Vidéo 3
### Exercices Vidéo 3



## Vidéo 4 Extensions asynchrones du langage

### Compléments Vidéo 4

* à faire: itérations asynchrones
  async for; compréhension asynchrone;
  [await foo(x) for x in iterator]
  [await foo(x) async for x in async_iterator]
  montrer que c'est différent d'un gather()
  et a creuser
  expressions generatrices asynchrones ?
  generateurs asynchrones ?
  montrer qu'un objet *peut* être context manager synchrone et asynchrone
  dire qu'il manque juste les lambda asynchrones dans 3.6

### Exercices Vidéo 4



## Vidéo 5 coroutines et awaitables

* Le protocole awaitable, send(), la pile, await et yield

## Compléments 5



## Vidéo 6 Boucles d'événements


* ensure_future & run_forever() - Queue()
* ensure_future pour ajouter une tâche au milieu d'un scénario
* parler de get_event_loop()

### Compléments Vidéo 6

* montrer l'importance de get-event_loop pour accéder à la boucle
  courante depuis le code asynchrone (trouver un exemple ou le code
  asynchrone a besoin d'accéder à la boucle..)

* un complément sur stop() et close() et ces choses-là ce serait
  vraiment bien, est-ce facile à faire ? il faudra sans doute que les
  apprenants interrompent le kernel, ça peut être tricky, mais pas
  sûr...

* un complément sur la notion de Tâche
  voir dans tutorial.ipynb la section avec monitor_tasks()
  qu'il faudra sans doute simplifier un peu

* un complément sur wait() - cf. asynciojobs
  https://docs.python.org/3/library/asyncio-task.html#asyncio.wait

### Exercices Vidéo 6



## Vidéo 7 Tâches et exceptions

* animation de la boucle, les piles, et comment sont gérées les exceptions

### Compléments Vidéo 7

* des exemples de tâches qu'on cancelle, de boucle qu'on arrête, ce
  genre de trucs

* peut-être le bon endroit pour parler de wait() ?



### Compléments Vidéo 7

* s'inspirer de raise2.py qui montre comment monitorer les tâches
  d'une boucle, regarder les résultats et les exceptions..



## Vidéo 8 La librairie `asyncio`


* Queue

* ~~Subprocess~~ je crois que finalement subprocess j'ai pas le temps
  d'en parler

* transition: insister sur le fait que la boucle d'évenements sait dialoguer avec
  l'OS pour faire son job de manière efficace

* mentionner Transport/Protocol + Stream
  -> compléments / utiliser des lib. de haut niveau
     comme aiohttp asyncssh

### Compléments Vidéo 8

* a minima un exemple avec Lock
  parler de connection partagée (e.g. ssh) par plusieurs sessions ->
  tout de même besoin de gérer les accès parallèles
* un protocole de bas niveau avec connection_made() connection_lost()
* montrer un serveur TCP encore + basique tel que dans
  https://www.python.org/dev/peps/pep-0492/#types-coroutine
  se méfier tout de même, on risque d'être limité par l'infra de
  notebooks, qui utilise localhost...

### Exercices Vidéo 8


## Vidéo 9 Bonnes pratiques

* quels appels entre monde synchrone et monde asynchrone sont légaux ou pas
* bien penser à ne pas bloquer pendant trop longtemps
* lire les exceptions des tâches

NOTES

* tout ce qui est là dedans ce sont des redites, je me
demande si ça vaut le coup de tourner ça ou pas; on pourrait
transformer le notebook en compléments, car ça vaut qd même le coup de
bien insister sur ces deux points.

### Compléments Vidéo 9
### Exercices Vidéo 9

*****

# Idées

* pour les complements, ajouter un lien vers
  https://www.youtube.com/watch?v=2ZFFv-wZ8_g
  le talk de Yuri Selivanov - etat de asyncio pour PyCon'17

* contagion: exemple d'un parser; un parser travaille sur un fichier
  complet et pas à priori de manière incrémentale

* trade-off entre une approche 'monkey-patch' à la gevent, vs une
  approche explicite avec async/await

* très intéressant - pour un complément:
  https://mdk.fr/blog/python-coroutines-with-async-and-await.html
  pour implémenter sa propre mini-loop et bien comprendre send et yield et StopIteration et tout ça

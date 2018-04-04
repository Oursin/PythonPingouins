# Atelier Pingouin - Python

## Introduction

Pour vous qui avez déjà codé en C, il est fort probable que Python vous semble être un langage "facile". En effet, Python est un langage dit "haut niveau", bien plus proche du langage naturel que le C. Par exemple, certains opérateurs C sont remplacés par des mots courants (le `&&` devient `and`, ...).

Pour les projets autorisant le Python à Epitech (les maths par exemple), vous n'aurez pas de norme à suivre (même si la norme PEP8 est conseillée car standard en Python) ni de fonctions interdites à éviter. Pour cet atelier, vous aurez donc le droit à tout ce que la bibliothèque standard de Python vous propose.

## Task 1 - Revoyons les bases

### Présentation

Considérant que vous avez tous déjà codé en C, il me semble important de revenir sur les quelques différences importantes entre le C et le Python.

* Python est un langage interprété, le C est un langage compilé. Dans tous les cas vous aurez besoin d'un programme pour que votre code puisse fonctionner, mais la méthode utilisée est différente. En C, un programme va transformer votre code en langage machine, en Python c'est un programme qui va directement lire votre code et l'éxecuter. Le principal avantage de cette méthode est d'assurer que votre code fonctionnera sur n'importe quelle machine, pour peu que l'interpréteur Python soit installé.

* Le type des variables est dynamique. En C, si je veux convertir une chaîne de caractères en un entier, il me faut avoir deux variables, un char * et un int. En Python une même variable peut très bien changer de type au cours de son utilisation. Également, les entiers en Python ne souffrent pas de la même limite qu'en C, vous pouvez aller aussi loin que vous le souhaîtez.

* Pas de fonction main en Python. Python est un langage de script, vous pouvez écrire votre code tel quel dans votre fichier, l'interpréteur le lira de haut en bas.

Voici la syntaxe pour créer une fonction en Python :

```python
def ma_fonction(arg):
	<code>
```

**Note** : Comme vous l'aurez remarqué, il n'y a pas d'accolades en Python. Pour cette raison, l'indentation est extrêmement importante, c'est elle qui permet à l'interpréteur de savoir ou se termine la fonction.

### Exercice

Codons un peu, voulez vous ? Commencez par écrire une fonction qui prend deux valeurs en paramètre, puis retourne leur somme, puis appelez un Pingouin.

## Task 2 - Structures de contrôle

### Présentation

Si jamais le titre ne vous parle pas, n'ayez pas peur, on va juste parler de conditions et de boucles (et puis on va faire un point sur les tableaux aussi), rien de grave.

Pour commencer, voici la syntaxe des conditions :

```python
if <condition>:
	<code>
```

Rien de plus simple. Pas de parenthèses, pas d'accolades, les parenthèses ne sont nécessaires que si la priorité des opérateurs pose soucis.
Concernant la syntaxe des conditions, les opérateurs de comparaison sont les même qu'en C (==, <= et autres). Par contre les oparateurs logiques sont en toutes lettres ("and" à la place de "&&", "or" à la place de "||", "not" la place de "!"...).

Les structures `while` ont une structure identique, je ne m'attarderais donc pas dessus. La structure `for` quand à elle diffère assez fortement du C, il est probablement utile de faire un point dessus. Voici donc la syntaxe.

```python
for <elem> in <group>:
	<code>
```

**Note** : Vous l'aurez compris, en dans un for en Python, la variable <elem> prendra successivement la valeur de chaque élément du <group>. Bonne nouvelle, la boucle s'arrêtera d'elle même une fois la fin de <group> atteinte.

__Première question :__ Comment faire pour avoir un entier qui aille d'une valeur à une autre comme on a l'habitude en C ?

Et bien Python arrive avec une fonction builtin appellée `range`, qui vous permettra de générer la liste des valeurs que votre élément devra prendre.

__Deuxième question :__ Que puis-je mettre à la place du champ <group> ?

N'importe quelle valeur itérable, c'st à dire n'importe quelle séquence de données, que ce soit une chaîne de caractères, une liste ou n'importe quel autre type dont seul Python a le secret.

_Une liste ?_

Oui. En python on ne parle pas de tableau mais de liste (voyez ça comme une liste chaînée mais en facile). Une liste se note entre crochets, et est une collection ordonnée de données. Une liste en python peut comporter des données de n'importe quel type, on peut très bien voir se suivre un nombre et une chaîne de caractères par exemple.

### Exercice

Jouons un peu avec les structures de contrôle à présent :

* Commencez par écrire une fonction qui vérifie si un nombre est positif. Cette fonction devra renvoyer la valeur `True` si la valeur est positive, `False` sinon.

* Créez ensuite une fonction qui vérifie si l'ensemble des valeurs d'une liste est positif. Cette fonction renverra les mêmes valeurs que la précédente, et on supposera que l'ensemble des valeurs de cette liste sont des nombres.

* Créez enfin une fonction qui prend une liste en paramètre, et renvoie une nouvelle liste ne contenant que les valeurs positives de la liste initiale. Par exemple si je donne la liste `[-1, 6, 8, -56]`, cette fonction me renverra la liste `[6, 8]`.

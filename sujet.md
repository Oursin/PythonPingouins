# Atelier Pingouin - Python

## Introduction

Pour vous qui avez déjà codé en C, il est fort probable que Python vous semble être un langage "facile". En effet, Python est un langage dit "haut niveau", bien plus proche du langage naturel que le C. Par exemple, certains opérateurs C sont remplacés par des mots courants (le `&&` devient `and`, ...).

Pour les projets autorisant le Python à Epitech (les maths par exemple), vous n'aurez pas de norme à suivre (même si la norme PEP8 est conseillée car standard en Python) ni de fonctions interdites à éviter. Pour cet atelier, vous aurez donc le droit à tout ce que la bibliothèque standard de Python vous propose.

## Partie 1 - Revoyons les bases

### Présentation

Considérant que vous avez tous déjà codé en C, il me semble important de revenir sur les quelques différences importantes entre le C et le Python.

* Python est un langage interprété, le C est un langage compilé. Dans tous les cas vous aurez besoin d'un programme pour que votre code puisse fonctionner, mais la méthode utilisée est différente. En C, un programme va transformer votre code en langage machine, en Python c'est un programme qui va directement lire votre code et l'éxecuter. Le principal avantage de cette méthode est d'assurer que votre code fonctionnera sur n'importe quelle machine, pour peu que l'interpréteur Python soit installé.

* Pour lancer votre programme, vous pouvez utiliser la commande `python3 <fichier>.py`.

* Le type des variables est dynamique. En C, si je veux convertir une chaîne de caractères en un entier, il me faut avoir deux variables, un char * et un int. En Python une même variable peut très bien changer de type au cours de son utilisation. Également, les entiers en Python ne souffrent pas de la même limite qu'en C, vous pouvez aller aussi loin que vous le souhaîtez.

* Pas de fonction `main` en Python. Python est un langage de script, vous pouvez écrire votre code tel quel dans votre fichier, l'interpréteur le lira de haut en bas.

Voici la syntaxe pour créer une fonction en Python :

```python
def ma_fonction(arg):
    <code>
```

**Note** : Comme vous l'aurez remarqué, il n'y a pas d'accolades en Python. Pour cette raison, l'indentation est extrêmement importante, c'est elle qui permet à l'interpréteur de savoir où se termine la fonction.

### Exercice

Codons un peu, voulez vous ? Commencez par écrire une fonction qui prend deux valeurs en paramètre, puis retourne leur somme. Appelez enfin un Pingouin.

## Partie 2 - Structures de contrôle

### Présentation

Si jamais le titre ne vous parle pas, n'ayez pas peur, on va juste parler de conditions et de boucles (et puis on va faire un point sur les tableaux aussi), rien de grave.

Pour commencer, voici la syntaxe des conditions :

```python
if <condition>:
    <code>
```

Rien de plus simple. Pas de parenthèses, pas d'accolades, les parenthèses ne sont nécessaires que si la priorité des opérateurs pose soucis.
Concernant la syntaxe des conditions, les opérateurs de comparaison sont les même qu'en C (==, <= et autres). Par contre les oparateurs logiques sont en toutes lettres ("and" à la place de "&&", "or" à la place de "||", "not" la place de "!"...).

Les structures `while` ont une structure identique, je ne m'attarderais donc pas dessus. La structure `for` quand à elle diffère assez fortement du C, il est probablement utile de faire un point dessus. Voici donc sa syntaxe :

```python
for <elem> in <group>:
    <code>
```

**Note** : Vous l'aurez compris, dans un for en Python, la variable `<elem>` prendra successivement la valeur de chaque élément du `<group>`. Bonne nouvelle, la boucle s'arrêtera d'elle même une fois la fin de `<group>` atteinte.

__Première question :__ Comment faire pour avoir un entier qui aille d'une valeur à une autre comme on a l'habitude en C ?

Et bien Python arrive avec une fonction builtin appellée `range`, qui vous permettra de générer la liste des valeurs que votre élément devra prendre.

__Deuxième question :__ Que puis-je mettre à la place du champ `<group>` ?

N'importe quelle valeur itérable, c'est à dire n'importe quelle séquence de données, que ce soit une chaîne de caractères, une liste ou n'importe quel autre type dont seul Python a le secret.

_Une liste ?_

Oui. En python on ne parle pas de tableau mais de liste (voyez ça comme une liste chaînée mais en facile). Une liste se note entre crochets, et est une collection ordonnée de données. Une liste en python peut comporter des données de n'importe quel type, on peut très bien voir se suivre un nombre et une chaîne de caractères par exemple.

### Exercice

Jouons un peu avec les structures de contrôle à présent :

* Commencez par écrire une fonction qui vérifie si un nombre est positif. Cette fonction devra renvoyer la valeur `True` si la valeur est positive, `False` sinon.

* Créez ensuite une fonction qui vérifie si l'ensemble des valeurs d'une liste est positif. Cette fonction renverra les mêmes valeurs que la précédente, et on supposera que toutes les valeurs sont des nombres.

* Créez enfin une fonction qui prend une liste en paramètre, et renvoie une nouvelle liste ne contenant que les valeurs positives de la liste initiale. Par exemple si je donne la liste `[-1, 6, 8, -56]`, cette fonction me renverra la liste `[6, 8]`.

## Partie 3 - Parlons objet

### Présentation

#### Généralités

Nous voici dans la partie la plus technique de cet atelier, car elle s'éloigne beaucoup de ce à quoi vous êtes habitués en C. Si vous avez la moindre question, n'hésitez pas à appeller un Pingouin.

Python est ce qu'on appelle un langage multi-paradigme, il permet la cohabitation de plusieurs manières de programmer. L'une de ces manières est dite procédurale, comme c'est le cas en C. L'autre, et celle qui nous intéresse aujourd'hui est appellée Programmation Orienté Objet (POO).

En POO on manipule des objets, qui sont des sortes de super variables surboostées aux hormones, et qui représentent la base de notre code. D'un certain point de vue on pourrait voir un objet comme un type de variable similaire à une structure en C, mais on passerait à côté de bien des possibilités.

Pour faire simple, un objet en POO, c'est quelque chose d'assez similaire à la définition d'un "objet" dans la vraie vie. Il s'agit de quelque chose qui peut être décrit, et qui peut être utilisé de différentes façons. En POO on parlera d'__attribut__ pour décrire un objet, et de __méthode__ pour ses utilisations.

Mais un exemple vaudra mieux que de longues explications. Supposons que l'on veuille gérer un personnage dans un jeu vidéo :

Ce personnage a un certain nombre de caractéristiques :
* Ses points de vie
* Ses points d'attaque
* Son apparence (sprite)
* etc...

Ce personnage aura aussi des actions possibles :
* Se déplacer
* Attaquer
* Perdre de la vie
* etc...

Avec de la programmation orientée objet, on pourra créer une seule structure de données qui combine tous ces aspects. Regardons à présent comment on pourrait implémenter les caractéristiques de notre objet en Python :

```python
class Personnage:
    def __init__(self, pv, pa, sprite):
        self.pv = pv
        self.pa = pa
        self.sprite = sprite
        self.pos = [0, 0]

mon_perso = Personnage(100, 5, "sprite.jpg")
```

Comme vous pouvez le voir, la création d'un objet en Python se fait via le mot-clé `class`. Interessons nous à la méthode `__init__`, qui est une méthode assez particulière. En effet, cette fonction sera appelée lors de la création d'une variable de cette classe, ce qu'on appelle une méthode _constructeur_.

Le premier argument de cette méthode est `self`, variable qui représente l'objet lui même. La méthode prend aussi les points de vie, d'attaque et le sprite en argument. L'intérêt de la fonction est de définir les valeurs par défaut des différents attributs de l'objet.

Voyons à présent comment on pourrait implémenter une méthode permettant le déplacement du personnage, ainsi que comment appeller cette méthode.

```python
class Personnage:
    def __init__(self, pv, pa, sprite):
        self.pv = pv
        self.pa = pa
        self.sprite = sprite
        self.pos = [0, 0]

    def move(self, x, y):
        self.pos[0] += x
        self.pos[1] += y

mon_perso = Personnage(100, 5, "sprite.jpg")
mon_perso.move(10, -10)
```

Notre méthode modifie la valeur de l'attribut pos de l'objet, pour effectuer le déplacement. La méthode n'a pas besoin de return de valeur, car comme indiqué précédemment, le mot-clé self représente l'objet lui même. On modifie ses caractéristiques directement.

#### Parenthèse : Les méthodes spéciales

Tout comme la méthode `__init__` présentée au dessus est une méthode appelée pour une occasion particulière, il existe un certain nombre de méthodes qui seront appelées lors d'occasions spéciales.

Supposons que j'aie un objet dont dont j'aimerais pouvoir afficher les paramètres. Si j'utilise simplement la fonction print j'obtiendrais l'emplacement mémoire de ma variable, sa classe et c'est tout. Pour pouvoir afficher les données que je veux, il est possible d'utiliser la méthode `__str__`. Cette méthode doit renvoyer une chaîne de caractères, au développeur de la définir comme il le souhaite.

De la même manière, il est possible de définir la méthode `__add__` pour spécifier le comportement de l'opérateur `+` sur des instances de la classe.

**Note :** une liste complète de ces méthodes est disponibles à cette adresse : https://docs.python.org/3/reference/datamodel.html#special-method-names

### Exercice

Notre Personnage a besoin d'ennemis !

Créez une classe Ennemi. Chaque ennemi doit posséder un stock de point de vie, des points d'attaque, une position, un sprite, une vitesse de déplacement, et doit savoir s'il est vivant. Chaque ennemi doit être capable de se déplacer en prenant en compte sa vitesse de déplacement, être capable de changer de vitesse de déplacement ainsi que perdre des points de vie, en plus de vérifier s'il est vivant.

Appelez un Pingouin quand vous pensez avoir fini et présentez lui vos choix !

## Pour finir

Merci d'être venus à cet atelier et bon courage pour vos futurs projets en Python !

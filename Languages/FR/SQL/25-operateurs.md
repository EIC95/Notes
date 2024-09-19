# Opérateurs SQL

## Opérateurs Arithmétiques

Les opérateurs arithmétiques sont utilisés pour effectuer des opérations mathématiques simples.

- **+** : Addition
- **-** : Soustraction
- **\*** : Multiplication
- **/** : Division
- **%** : Modulo (reste d'une division)

## Opérateurs Binaires

Les opérateurs binaires permettent d'effectuer des opérations logiques sur des bits.

- **&** : ET binaire (les deux bits doivent être 1 pour que le résultat soit 1)
- **^** : OU exclusif (XOR binaire) (le résultat est 1 si les bits sont différents)

## Opérateurs de Comparaison

Les opérateurs de comparaison sont utilisés pour comparer deux valeurs.

- **=** : Égal à
- **>** : Supérieur à
- **<** : Inférieur à
- **>=** : Supérieur ou égal à
- **<=** : Inférieur ou égal à
- **<>** : Différent de

## Opérateurs d'Affectation

Les opérateurs d'affectation sont utilisés pour mettre à jour les valeurs d'une colonne.

- **+=** : Addition et égal (ajoute une valeur et assigne le résultat)
- **-=** : Soustraction et égal
- **\*=** : Multiplication et égal
- **/=** : Division et égal
- **%=** : Modulo et égal
- **&=** : ET binaire et égal
- **^=** : OU exclusif et égal

## Opérateurs Logiques

Les opérateurs logiques permettent de combiner plusieurs conditions ou de tester la véracité d'une condition.

- **ALL** : VRAI si toutes les valeurs de la sous-requête satisfont la condition.
- **AND** : VRAI si toutes les conditions séparées par AND sont VRAIES.
- **ANY** : VRAI si une des valeurs de la sous-requête satisfait la condition.
- **BETWEEN** : VRAI si l'opérande est dans la plage de comparaisons.
- **EXISTS** : VRAI si la sous-requête retourne un ou plusieurs enregistrements.
- **IN** : VRAI si l'opérande est égal à une des expressions de la liste.
- **LIKE** : VRAI si l'opérande correspond à un modèle.
- **NOT** : Affiche un enregistrement si la condition n'est pas satisfaite.
- **OR** : VRAI si une des conditions séparées par OR est VRAIE.
- **SOME** : VRAI si une des valeurs de la sous-requête satisfait la condition.
```
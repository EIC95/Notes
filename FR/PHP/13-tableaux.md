# Tableaux en PHP

En PHP, vous pouvez créer des tableaux à l'aide de la fonction `array()` ou en utilisant une syntaxe plus courte avec les crochets `[]`.

## Création de tableau

### Exemple avec `array()`

```php
<?php
$tableau = array(1, 2, 3, 4);
?>
```

### Exemple avec `[]`

```php
<?php
$tableau = [1, 2, 3, 4];
?>
```

Les éléments d'un tableau peuvent être de n'importe quel type, y compris des fonctions.

## Parcourir un tableau avec `foreach`

Pour parcourir toutes les valeurs d'un tableau, vous pouvez utiliser la boucle `foreach`.

```php
<?php
$tableau = [1, 2, 3, 4];

foreach ($tableau as $valeur) {
    echo $valeur;
}
?>
```

## Tableaux associatifs

Les tableaux associatifs utilisent des clés nommées. Vous pouvez accéder aux éléments en utilisant des guillemets simples ou doubles.

```php
<?php
$tableauAssociatif = [
    "nom" => "Ibrahima",
    "age" => 21
];

echo $tableauAssociatif['nom']; // Ibrahima
?>
```

## Modifier les valeurs avec `foreach` par référence

Pour modifier les éléments d'un tableau dans une boucle `foreach`, vous pouvez utiliser la référence avec `&`. N'oubliez pas d'utiliser `unset()` après la boucle.

```php
<?php
$tableau = [1, 2, 3];

foreach ($tableau as &$valeur) {
    $valeur *= 2; // Double chaque valeur
}
unset($valeur); // Libère la référence
?>
```

## Ajouter plusieurs éléments à un tableau

Pour ajouter plusieurs éléments à un tableau existant, vous pouvez utiliser l'opérateur `+=`.

```php
<?php
$tableau1 = [1, 2];
$tableau2 = [3, 4];

$tableau1 += $tableau2;

print_r($tableau1); // [1, 2, 3, 4]
?>
```

## Tableaux multidimensionnels

Vous pouvez créer un tableau multidimensionnel en PHP avec des tableaux imbriqués.

```php
<?php
$tableauMultidimensionnel = [
    ["Nom" => "Ibrahima", "Age" => 21],
    ["Nom" => "Fatou", "Age" => 23]
];
```

## Fonctions Utiles pour les Tableaux

### Ajouter et retirer des éléments

- `array_push()`: Ajoute un ou plusieurs éléments à la fin d'un tableau.

```php
<?php
array_push($tableau, 5, 6);
```

- `array_pop()`: Retire le dernier élément d'un tableau.

```php
<?php
array_pop($tableau);
```

- `array_shift()`: Retire le premier élément d'un tableau.

```php
<?php
array_shift($tableau);
```

- `array_unshift()`: Ajoute un ou plusieurs éléments au début d'un tableau.

```php
<?php
array_unshift($tableau, 0);
```

### Fusionner et extraire

- `array_merge()`: Fusionne un ou plusieurs tableaux.

```php
<?php
$tableauFusionne = array_merge($tableau1, $tableau2);
```

- `array_slice()`: Extrait une portion d'un tableau.

```php
<?php
$slice = array_slice($tableau, 1, 2);
```

### Trier et obtenir des valeurs

- `array_values()`: Retourne toutes les valeurs d'un tableau.

```php
<?php
$valeurs = array_values($tableauAssociatif);
```

- `sort()`: Trie un tableau en ordre croissant.

```php
<?php
sort($tableau);
```
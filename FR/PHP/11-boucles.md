# Boucles en PHP

Les boucles en PHP permettent de répéter un bloc de code plusieurs fois selon certaines conditions.

## `for`

La boucle `for` est utilisée lorsque le nombre d'itérations est connu à l'avance.

```php
<?php
for ($i = 0; $i < 5; $i++) {
    echo $i . " ";
}
// Résultat : 0 1 2 3 4
?>
```

## `while`

La boucle `while` continue d'exécuter le bloc de code tant que la condition est vraie.

```php
<?php
$i = 0;
while ($i < 5) {
    echo $i . " ";
    $i++;
}
// Résultat : 0 1 2 3 4
?>
```

## `do...while`

La boucle `do...while` est similaire à la boucle `while`, mais elle garantit que le bloc de code est exécuté au moins une fois.

```php
<?php
$i = 0;
do {
    echo $i . " ";
    $i++;
} while ($i < 5);
// Résultat : 0 1 2 3 4
?>
```

## `foreach`

La boucle `foreach` est utilisée pour itérer sur les éléments d'un tableau ou d'un objet.

```php
<?php
$fruits = array("Pomme", "Banane", "Cerise");
foreach ($fruits as $fruit) {
    echo $fruit . " ";
}
// Résultat : Pomme Banane Cerise
?>
```
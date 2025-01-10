# Conditions en PHP

## Instruction `if`

L'instruction `if` permet d'exécuter un bloc de code si une condition est vraie.

```php
<?php
if ($a > $b) {
    echo "$a est plus grand que $b";
}
?>
```

## Instruction `if...else`

L'instruction `if...else` permet d'exécuter un bloc de code si la condition est vraie, sinon elle exécute un autre bloc de code.

```php
<?php
if ($a > $b) {
    echo "$a est plus grand que $b";
} else {
    echo "$a n'est pas plus grand que $b";
}
?>
```

## Instruction `else if`

L'instruction `else if` permet de tester plusieurs conditions de manière séquentielle.

```php
<?php
if ($a > $b) {
    echo "$a est plus grand que $b";
} elseif ($a == $b) {
    echo "$a est égal à $b";
} else {
    echo "$a est plus petit que $b";
}
?>
```

## Instruction `switch case`

L'instruction `switch` permet de tester une variable contre plusieurs valeurs possibles et d'exécuter le bloc de code correspondant à la valeur trouvée.

```php
<?php
switch ($fruit) {
    case 'pomme':
        echo "C'est une pomme";
        break;
    case 'banane':
        echo "C'est une banane";
        break;
    case 'orange':
        echo "C'est une orange";
        break;
    default:
        echo "Fruit inconnu";
}
?>
```

## Opérateur ternaire

L'opérateur ternaire est une façon concise d'écrire une instruction `if...else`.

```php
<?php
$message = ($a > $b) ? "$a est plus grand que $b" : "$a n'est pas plus grand que $b";
echo $message;
?>
```

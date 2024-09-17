# Structure Conditionnelles en PHP

## if

La structure de base pour une instruction `if` en PHP est la suivante :

```php
<?php
$age = 20;
if ($age >= 18) {
    echo "Vous êtes majeur.";
}
?>
```

## if...else

La structure de base pour une instruction `if...else` en PHP est la suivante :

```php
<?php
$age = 16;
if ($age >= 18) {
    echo "Vous êtes majeur.";
} else {
    echo "Vous êtes mineur.";
}
?>

```

## else if

La structure de base pour une instruction `else if` en PHP est la suivante :

```php
<?php
$note = 75;
if ($note >= 90) {
    echo "Excellent";
} elseif ($note >= 70) {
    echo "Bon";
} else {
    echo "Satisfaisant";
}
?>

```

## switch case

La structure de base pour une instruction `switch` en PHP est la suivante :

```php
<?php
$jour = "Lundi";
switch ($jour) {
    case "Lundi":
        echo "Début de la semaine";
        break;
    case "Vendredi":
        echo "Fin de la semaine";
        break;
    default:
        echo "Jour normal";
}
?>

```

## Opérateur ternaire

La structure de base pour une instruction ternaire en PHP est la suivante :

```php
<?php
$age = 18;
echo ($age >= 18) ? "Adulte" : "Mineur";
?>
```
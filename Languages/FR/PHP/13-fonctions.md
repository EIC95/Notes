# Fonctions en PHP

PHP propose plus de 1000 fonctions intégrées, et vous pouvez également créer vos propres fonctions personnalisées. Une déclaration de fonction définie par l'utilisateur commence par le mot-clé `function`, suivi du nom de la fonction. Voici quelques concepts clés liés aux fonctions en PHP.

## Déclaration de fonction

Voici comment déclarer une fonction et l'appeler :

```php
<?php
function direBonjour() {
    return "Bonjour!";
}

echo direBonjour();
?>
```

## Paramètres et arguments

Les informations peuvent être passées aux fonctions via des **arguments**.

```php
<?php
function direBonjour($nom) {
    return "Bonjour, " . $nom;
}

echo direBonjour("Ibrahima");
?>
```

## Paramètres par défaut

Une fonction peut avoir des paramètres avec des valeurs par défaut :

```php
<?php
function direBonjour($nom = "Visiteur") {
    return "Bonjour, " . $nom;
}

echo direBonjour(); // Bonjour, Visiteur
echo direBonjour("Ibrahima"); // Bonjour, Ibrahima
?>
```

## Arguments passés par référence

Les arguments sont généralement passés par valeur, mais vous pouvez utiliser le symbole `&` pour passer une variable par référence, permettant ainsi à la fonction de modifier la variable d'origine.

```php
<?php
function ajouterExclamation(&$str) {
    $str .= "!";
}

$message = "Bonjour";
ajouterExclamation($message);
echo $message; // Bonjour!
?>
```

## Fonction variadique (nombre d'arguments illimité)

En utilisant l'opérateur `...` devant un paramètre de fonction, celle-ci peut accepter un nombre illimité d'arguments (fonction variadique). Ces arguments sont alors reçus sous forme de tableau.

```php
<?php
function additionner(...$nombres) {
    return array_sum($nombres);
}

echo additionner(1, 2, 3, 4); // 10
?>
```

## Déclaration de type et strict mode

PHP 7 introduit les **déclarations de type**, qui permettent de spécifier le type de données attendu dans une fonction.

Pour activer le mode strict, ajoutez cette ligne en haut du fichier PHP :
```php
declare(strict_types=1);
```

Voici un exemple d'utilisation des déclarations de type :

```php
<?php
declare(strict_types=1);

function multiplier(int $a, int $b): int {
    return $a * $b;
}

echo multiplier(3, 4); // 12
?>
```
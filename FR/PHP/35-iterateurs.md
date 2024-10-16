# Itérables en PHP

Un **itérable** en PHP est une valeur pouvant être parcourue avec une boucle `foreach()`. Depuis PHP 7.1, le pseudo-type `iterable` a été introduit pour simplifier le traitement des types de données itérables.

## Utilisation du type `iterable`

Le type `iterable` peut être utilisé pour les arguments et les valeurs de retour de fonctions, ce qui permet de spécifier que la fonction accepte ou retourne tout type de données pouvant être itéré.

### Déclaration d'un argument de fonction

```php
<?php
function afficherElements(iterable $elements) {
    foreach ($elements as $element) {
        echo $element;
    }
}
?>
```

### Déclaration d'un type de retour de fonction

```php
<?php
function obtenirElements(): iterable {
    return [1, 2, 3, 4];
}
?>
```

Le type `iterable` englobe les tableaux et les objets qui implémentent l'interface `Traversable`, offrant ainsi une flexibilité accrue pour la manipulation des collections de données.

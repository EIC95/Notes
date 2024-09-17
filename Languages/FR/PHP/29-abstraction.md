# Classes abstraites en PHP

Une **classe abstraite** est une classe qui ne peut pas être instanciée directement. Elle est conçue pour être étendue par d'autres classes. Une classe abstraite peut contenir des méthodes abstraites, qui sont des méthodes déclarées sans implémentation. Les classes dérivées doivent fournir une implémentation pour ces méthodes abstraites.

## Déclaration d'une classe abstraite

Pour déclarer une classe abstraite, utilisez le mot-clé `abstract` avant le mot-clé `class`. Les méthodes abstraites doivent également être précédées du mot-clé `abstract` et ne doivent pas avoir de corps.

### Exemple de déclaration
```php
<?php
abstract class Animal {
    // Méthode abstraite
    abstract protected function faireDuBruit();

    // Méthode non abstraite
    public function dormir() {
        echo "L'animal dort.";
    }
}
?>
```

## Implémentation des méthodes abstraites

Les classes qui étendent une classe abstraite doivent implémenter toutes les méthodes abstraites déclarées dans la classe parente.

### Exemple d'Implémentation
```php
<?php
class Chien extends Animal {
    // Implémentation de la méthode abstraite
    protected function faireDuBruit() {
        echo "Le chien aboie.";
    }
}

$monChien = new Chien();
$monChien->faireDuBruit(); // Affiche: Le chien aboie.
$monChien->dormir(); // Affiche: L'animal dort.
?>
```
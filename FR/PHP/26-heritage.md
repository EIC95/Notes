# Héritage en PHP

## Définition de la classe héritée

En PHP, une classe peut hériter des propriétés et des méthodes d'une autre classe en utilisant le mot-clé `extends`. La classe qui hérite est appelée classe dérivée ou sous-classe, tandis que la classe d'origine est appelée classe de base ou super-classe.

```php
<?php
class Animal {
    public $nom;

    public function __construct($nom) {
        $this->nom = $nom;
    }

    public function parler() {
        return "Je suis un animal.";
    }
}

class Chien extends Animal {
    public function parler() {
        return "Je suis un chien et j'aboie.";
    }
}

$monChien = new Chien("Rex");
echo $monChien->parler(); // Je suis un chien et j'aboie.
?>
```

## Utilisation du mot-clé `final`

Le mot-clé `final` peut être utilisé dans deux contextes différents :

- **Pour empêcher l'héritage d'une classe :** Une classe marquée comme `final` ne peut pas être étendue par d'autres classes.

```php
<?php
final class FinalClass {
    public function afficher() {
        return "Je suis une classe finale.";
    }
}

// La ligne suivante générera une erreur
// class DerivedClass extends FinalClass {}
?>
```

- **Pour empêcher le remplacement d'une méthode :** Une méthode marquée comme `final` dans une classe ne peut pas être remplacée par une sous-classe.

```php
<?php
class BaseClass {
    final public function method() {
        return "Méthode finale.";
    }
}

class DerivedClass extends BaseClass {
    // La ligne suivante générera une erreur
    // public function method() {
    //     return "Tentative de remplacement.";
    // }
}
?>
```
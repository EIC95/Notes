# Modificateurs d'accès en PHP

Les modificateurs d'accès en PHP définissent la visibilité des propriétés et des méthodes d'une classe. Voici les trois principaux modificateurs d'accès :

## `public`

Le modificateur `public` permet à la propriété ou méthode d'être accessible depuis n'importe où, à l'intérieur ou à l'extérieur de la classe.

```php
<?php
class Personne {
    public $nom;

    public function __construct($nom) {
        $this->nom = $nom;
    }

    public function sePresenter() {
        return "Je m'appelle " . $this->nom;
    }
}

$personne = new Personne("Alice");
echo $personne->sePresenter(); // Je m'appelle Alice
?>
```

## `protected`

Le modificateur `protected` permet à la propriété ou méthode d'être accessible uniquement depuis l'intérieur de la classe et ses sous-classes.

```php
<?php
class Personne {
    protected $nom;

    public function __construct($nom) {
        $this->nom = $nom;
    }
}

class Employe extends Personne {
    public function afficherNom() {
        return "Nom de l'employé : " . $this->nom;
    }
}

$employe = new Employe("Bob");
echo $employe->afficherNom(); // Nom de l'employé : Bob
?>
```

## `private`

Le modificateur `private` permet à la propriété ou méthode d'être accessible uniquement depuis l'intérieur de la classe où elle est définie.

```php
<?php
class Personne {
    private $nom;

    public function __construct($nom) {
        $this->nom = $nom;
    }

    public function obtenirNom() {
        return $this->nom;
    }
}

$personne = new Personne("Charlie");
echo $personne->obtenirNom(); // Charlie
?>
```

Ces modificateurs permettent de contrôler l'accès aux données et aux méthodes, renforçant ainsi l'encapsulation et la sécurité dans la programmation orientée objet.

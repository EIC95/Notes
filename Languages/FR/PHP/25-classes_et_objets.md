# Classes en PHP

En PHP, une classe est une structure fondamentale pour la programmation orientée objet. Voici comment définir et utiliser des classes :

## Définition d'une classe

Une classe est définie avec le mot-clé `class`, suivi du nom de la classe et d'une paire d'accolades (`{}`). Les propriétés et méthodes de la classe sont placées à l'intérieur de ces accolades.

```php
<?php
class Personne {
    public $nom;
    public $age;

    public function __construct($nom, $age) {
        $this->nom = $nom;
        $this->age = $age;
    }

    public function sePresenter() {
        return "Je m'appelle " . $this->nom . " et j'ai " . $this->age . " ans.";
    }
}
?>
```

## Création d'objets

Pour créer un objet d'une classe, utilisez le mot-clé `new`.

```php
<?php
$personne = new Personne("Alice", 25);
echo $personne->sePresenter(); // Je m'appelle Alice et j'ai 25 ans.
?>
```

## Utilisation de `$this`

Le mot-clé `$this` fait référence à l'objet actuel et est utilisé pour accéder aux propriétés et méthodes de l'objet depuis l'intérieur de la classe.

```php
<?php
class Personne {
    public $nom;

    public function __construct($nom) {
        $this->nom = $nom;
    }

    public function direBonjour() {
        return "Bonjour, je suis " . $this->nom;
    }
}
?>
```

## Constructeur et destructeur

- **Constructeur (`__construct()`)** : Fonction spéciale appelée automatiquement lors de la création d'un objet.
  ```php
  <?php
  class Personne {
      public function __construct() {
          echo "Une nouvelle personne a été créée.";
      }
  }
  new Personne(); // Une nouvelle personne a été créée.
  ?>
  ```

- **Destructeur (`__destruct()`)** : Fonction spéciale appelée automatiquement lorsque l'objet est détruit ou la fin du script est atteinte.
  ```php
  <?php
  class Personne {
      public function __destruct() {
          echo "L'objet Personne est détruit.";
      }
  }
  $personne = new Personne();
  unset($personne); // L'objet Personne est détruit.
  ?>
  ```

## Vérification d'Instance

Utilisez l'opérateur `instanceof` pour vérifier si un objet appartient à une classe spécifique.

```php
<?php
class Personne {}

$personne = new Personne();

if ($personne instanceof Personne) {
    echo "C'est une instance de Personne.";
}
?>
```
# Interfaces en PHP

Les **interfaces** en PHP permettent de définir un ensemble de méthodes qu'une classe doit implémenter, sans fournir d'implémentation. Elles sont utiles pour définir des contrats que les classes doivent suivre, facilitant ainsi le polymorphisme en permettant à différentes classes d'être traitées de manière uniforme.

## Déclaration d'une interface

Pour déclarer une interface, utilisez le mot-clé `interface` suivi du nom de l'interface. Les méthodes définies dans une interface n'ont pas de corps et doivent être publiques.

### Exemple de déclaration
```php
<?php
interface Animaux {
    public function faireDuBruit();
    public function manger();
}
?>
```

## Implémentation d'une interface

Une classe qui implémente une interface doit fournir une implémentation pour toutes les méthodes définies dans l'interface. Utilisez le mot-clé `implements` pour indiquer qu'une classe suit le contrat de l'interface.

### Exemple d'implémentation
```php
<?php
class Chat implements Animaux {
    public function faireDuBruit() {
        echo "Le chat miaule.";
    }

    public function manger() {
        echo "Le chat mange.";
    }
}

$monChat = new Chat();
$monChat->faireDuBruit(); // Affiche: Le chat miaule.
$monChat->manger(); // Affiche: Le chat mange.
?>
```
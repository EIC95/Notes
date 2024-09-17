# Espaces de noms en PHP

Les **espaces de noms** (namespaces) en PHP sont utilisés pour organiser et qualifier des classes, interfaces, fonctions et constantes. Ils résolvent les problèmes de collisions de noms et améliorent la structure du code.

## Avantages des espaces de noms

1. **Organisation** : Regroupe les classes qui travaillent ensemble pour une tâche spécifique, facilitant ainsi la gestion du code.
2. **Éviter les Collisions** : Permet d'utiliser le même nom pour plusieurs classes sans conflit.

## Déclaration

Les espaces de noms sont déclarés au début d'un fichier avec le mot-clé `namespace`. Il est possible d'avoir des espaces de noms imbriqués.

### Exemple de déclaration
```php
<?php
namespace MonNamespace\SousNamespace;

class MaClasse {
    // Code de la classe
}
?>
```

## Accès aux classes

Pour utiliser des classes ou des éléments d'un espace de noms différent, vous devez soit spécifier le nom complet avec le nom de l'espace de noms, soit créer un alias avec le mot-clé `use`.

### Exemple d'utilisation avec `use`
```php
<?php
namespace MonNamespace;

use MonNamespace\SousNamespace\MaClasse as ClasseAlias;

$instance = new ClasseAlias();
?>
```

### Exemple d'accès direct
```php
<?php
$instance = new \MonNamespace\SousNamespace\MaClasse();
?>
```

## Aliases

Vous pouvez donner un alias à un espace de noms ou à une classe pour simplifier son utilisation.

### Exemple de création d'alias
```php
<?php
namespace MonNamespace;

use MonNamespace\SousNamespace\MaClasse as ClasseAlias;

function maFonction() {
    $instance = new ClasseAlias();
}
?>
```
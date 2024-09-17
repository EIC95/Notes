# Méthodes et propriétés statiques en PHP

Les **méthodes** et **propriétés statiques** en PHP appartiennent à la classe elle-même plutôt qu'à une instance spécifique de la classe. Elles peuvent être appelées directement via le nom de la classe, sans avoir besoin de créer une instance de la classe.

## Déclaration

Les méthodes et propriétés statiques sont déclarées avec le mot-clé `static`.

### Exemple de déclaration
```php
<?php
class MaClasse {
    public static $proprieteStatique = "Valeur statique";

    public static function methodeStatique() {
        echo "Méthode statique appelée.";
    }
}
?>
```

## Utilisation

Pour accéder aux propriétés et méthodes statiques, utilisez l'opérateur de résolution de portée `::` avec le nom de la classe.

### Exemple d'utilisation
```php
<?php
// Accès à une propriété statique
echo MaClasse::$proprieteStatique; // Affiche: Valeur statique

// Appel d'une méthode statique
MaClasse::methodeStatique(); // Affiche: Méthode statique appelée.
?>
```

## Limites

- Les méthodes et propriétés statiques ne peuvent pas accéder aux membres non statiques de la classe. Elles ne peuvent pas utiliser `$this` car elles ne sont pas liées à une instance spécifique.
- Elles sont généralement utilisées pour des fonctionnalités ou des données partagées entre toutes les instances d'une classe.

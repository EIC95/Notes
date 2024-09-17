# Constantes de classe en PHP

Les **constantes de classe** sont déclarées à l'aide du mot-clé `const` et ne peuvent pas être modifiées après leur initialisation. Elles sont utilisées pour stocker des valeurs constantes et immuables. Les constantes sont sensibles à la casse et il est recommandé de les nommer en majuscules par convention.

## Déclaration et utilisation des constantes

### Déclaration
```php
<?php
class MaClasse {
    const MA_CONSTANTE = 'Valeur constante';
}
```

### Accès aux constantes
- **Depuis l'extérieur de la classe** : Utilisez le nom de la classe suivi de l'opérateur `::`.
```php
<?php
echo MaClasse::MA_CONSTANTE; // Affiche: Valeur constante
?>
```

- **Depuis l'intérieur de la classe** : Utilisez `self::` pour accéder à la constante.
```php
<?php
class MaClasse {
    const MA_CONSTANTE = 'Valeur constante';

    public function afficherConstante() {
        return self::MA_CONSTANTE;
    }
}

$obj = new MaClasse();
echo $obj->afficherConstante(); // Affiche: Valeur constante
?>
```
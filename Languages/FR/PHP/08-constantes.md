# Constantes en PHP

Les constantes en PHP sont des identificateurs dont la valeur ne peut pas être modifiée une fois définie. Elles sont utiles pour stocker des valeurs immuables comme des nombres spéciaux, des chemins de fichiers ou des paramètres de configuration.

## Méthodes de définition

Il existe deux principales méthodes pour définir des constantes en PHP :

* **`const`:** Permet de définir des constantes au niveau global.
* **`define()`:** Offre une plus grande flexibilité, permettant de définir des constantes à l'intérieur de fonctions ou de classes.

### Exemples

```php
// Utilisation de const
const PI = 3.14159;

// Utilisation de define()
define('VERSION', '1.0');
```
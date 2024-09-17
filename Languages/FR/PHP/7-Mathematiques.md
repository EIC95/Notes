# Fonctions nathématiques en PHP

PHP propose diverses fonctions mathématiques pour effectuer des tâches sur des nombres. Voici quelques-unes des fonctions les plus courantes :

- **`pi()`** : Renvoie la valeur de PI.

    ```php
    <?php
        echo pi(); // Affiche 3.1415926535898
    ?>
    ```

- **`min()`** et **`max()`** : Trouvent la valeur la plus basse ou la plus élevée dans une liste.

    ```php
    <?php
        echo min(1, 2, 3, 4, 5); // Affiche 1
        echo max(1, 2, 3, 4, 5); // Affiche 5
    ?>
    ```

- **`abs()`** : Renvoie la valeur absolue d'un nombre.

    ```php
    <?php
        echo abs(-10); // Affiche 10
    ?>
    ```

- **`sqrt()`** : Renvoie la racine carrée d'un nombre.

    ```php
    <?php
        echo sqrt(16); // Affiche 4
    ?>
    ```

- **`round()`** : Arrondit un nombre à l'entier le plus proche.

    ```php
    <?php
        echo round(3.6); // Affiche 4
        echo round(3.4); // Affiche 3
    ?>
    ```

- **`rand(min, max)`** : Génère un nombre aléatoire entre `min` et `max`.

    ```php
    <?php
        echo rand(1, 100); // Affiche un nombre aléatoire entre 1 et 100
    ?>
    ```

- **`ceil()`** : Arrondit un nombre à l'entier supérieur le plus proche.

    ```php
    <?php
        echo ceil(4.3); // Affiche 5
    ?>
    ```

- **`floor()`** : Arrondit un nombre à l'entier inférieur le plus proche.

    ```php
    <?php
        echo floor(4.7); // Affiche 4
    ?>
    ```

- **`pow(x, y)`** : Renvoie `x` à la puissance `y`.

    ```php
    <?php
        echo pow(2, 3); // Affiche 8
    ?>
    ```

- **`exp(x)`** : Renvoie `e^x` (exponentielle de `x`).

    ```php
    <?php
        echo exp(1); // Affiche 2.718281828459
    ?>
    ```

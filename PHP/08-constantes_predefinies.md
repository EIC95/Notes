# Constantes Magiques en PHP

PHP dispose de neuf constantes prédéfinies, appelées « constantes magiques », dont les valeurs varient en fonction du contexte où elles sont utilisées.

## Liste des Constantes Magiques

- **`__CLASS__`** : Renvoie le nom de la classe si utilisé à l'intérieur d'une classe.

    ```php
    <?php
        class MyClass {
            public function showClassName() {
                echo __CLASS__; // Affiche "MyClass"
            }
        }
    ?>
    ```

- **`__DIR__`** : Renvoie le répertoire du fichier.

    ```php
    <?php
        echo __DIR__; // Affiche le répertoire du fichier courant
    ?>
    ```

- **`__FILE__`** : Renvoie le nom du fichier, y compris le chemin complet.

    ```php
    <?php
        echo __FILE__; // Affiche le chemin complet du fichier courant
    ?>
    ```

- **`__FUNCTION__`** : Renvoie le nom de la fonction si utilisé à l'intérieur d'une fonction.

    ```php
    <?php
        function myFunction() {
            echo __FUNCTION__; // Affiche "myFunction"
        }
    ?>
    ```

- **`__LINE__`** : Renvoie le numéro de la ligne actuelle.

    ```php
    <?php
        echo __LINE__; // Affiche le numéro de la ligne actuelle
    ?>
    ```

- **`__METHOD__`** : Renvoie le nom de la méthode si utilisé à l'intérieur d'une méthode d'une classe.

    ```php
    <?php
        class MyClass {
            public function showMethodName() {
                echo __METHOD__; // Affiche "MyClass::showMethodName"
            }
        }
    ?>
    ```

- **`__NAMESPACE__`** : Renvoie le nom de l'espace de noms si utilisé à l'intérieur d'un espace de noms.

    ```php
    <?php
        namespace MyNamespace;
        echo __NAMESPACE__; // Affiche "MyNamespace"
    ?>
    ```

- **`__TRAIT__`** : Renvoie le nom du trait si utilisé à l'intérieur d'un trait.

    ```php
    <?php
        trait MyTrait {
            public function showTraitName() {
                echo __TRAIT__; // Affiche "MyTrait"
            }
        }
    ?>
    ```

- **`ClassName::class`** : Renvoie le nom de la classe spécifiée, y compris le nom de l'espace de noms, le cas échéant.

    ```php
    <?php
        echo MyClass::class; // Affiche "MyClass"
    ?>
    ```

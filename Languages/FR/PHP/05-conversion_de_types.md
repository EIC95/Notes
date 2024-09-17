# Conversion des types de données en PHP

En PHP, vous pouvez modifier une variable d'un type de données à un autre ou un type de données spécifique avec le casting. Voici les différentes conversions possibles :

- **`(string)`** : Convertit en **String**.

    ```php
    <?php
        $integer = 123;
        $string = (string) $integer;
        echo $string; // Affiche "123"
    ?>
    ```

- **`(int)`** : Convertit en **Integer**.

    ```php
    <?php
        $string = "123";
        $integer = (int) $string;
        echo $integer; // Affiche 123
    ?>
    ```

- **`(float)`** : Convertit en **Float**.

    ```php
    <?php
        $string = "123.45";
        $float = (float) $string;
        echo $float; // Affiche 123.45
    ?>
    ```

- **`(bool)`** : Convertit en **Booléen**.

    ```php
    <?php
        $integer = 1;
        $boolean = (bool) $integer;
        var_dump($boolean); // Affiche bool(true)
    ?>
    ```

- **`(array)`** : Convertit en **Array**.

    ```php
    <?php
        $string = "Hello";
        $array = (array) $string;
        print_r($array); // Affiche Array ( [0] => Hello )
    ?>
    ```

- **`(object)`** : Convertit en **Objet**.

    ```php
    <?php
        $array = array("a" => "apple", "b" => "banana");
        $object = (object) $array;
        print_r($object); // Affiche stdClass Object ( [a] => apple [b] => banana )
    ?>
    ```

- **`unset`** : Convertit en **NULL**.

    ```php
    <?php
        $variable = "Hello";
        unset($variable);
        var_dump($variable); // Affiche NULL
    ?>
    ```

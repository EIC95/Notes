# Chaînes en PHP

Les chaînes en PHP sont entourées soit de guillemets doubles, soit de guillemets simples. Il existe une grande différence entre les guillemets doubles et les guillemets simples en PHP. Les guillemets doubles traitent les caractères spéciaux et les variables, contrairement aux guillemets simples.

Pour concaténer ou combiner deux chaînes, vous pouvez utiliser l'opérateur point **`.`**.

### Caractères spéciaux

- **`\n`** : Nouvelle ligne
- **`\r`** : Retour chariot
- **`\t`** : Tabulation horizontale
- **`\\`** : Antislash
- **`\$`** : Signe de dollar
- **`\"`** : Guillemets doubles
- **`\'`** : Guillemets simples

### Fonctions utiles pour les chaînes

- **`strtoupper()`** : Renvoie la chaîne en majuscule.

    ```php
    <?php
        $string = "hello";
        echo strtoupper($string); // Affiche "HELLO"
    ?>
    ```

- **`strtolower()`** : Renvoie la chaîne en minuscule.

    ```php
    <?php
        $string = "HELLO";
        echo strtolower($string); // Affiche "hello"
    ?>
    ```

- **`str_replace()`** : Remplace certains caractères par d'autres caractères dans une chaîne.

    ```php
    <?php
        $string = "Hello World";
        echo str_replace("World", "PHP", $string); // Affiche "Hello PHP"
    ?>
    ```

- **`strrev()`** : Inverse une chaîne.

    ```php
    <?php
        $string = "hello";
        echo strrev($string); // Affiche "olleh"
    ?>
    ```

- **`explode()`** : Divise une chaîne en un tableau.

    ```php
    <?php
        $string = "apple,banana,orange";
        $array = explode(",", $string);
        print_r($array); // Affiche Array ( [0] => apple [1] => banana [2] => orange )
    ?>
    ```

- **`str_word_count()`** : Compte le nombre de mots dans une chaîne.

    ```php
    <?php
        $string = "Hello world";
        echo str_word_count($string); // Affiche 2
    ?>
    ```

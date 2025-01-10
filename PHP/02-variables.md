# Variables en PHP

En PHP, une variable commence par le signe **`$`**, suivi du nom de la variable. Pour obtenir le type de données d'une variable, utilisez la fonction **`var_dump()`**.

## Types de données en PHP

PHP prend en charge les types de données suivants :

- **String** (chaînes de caractères)
- **Integer** (entiers)
- **Float** (nombres à virgule flottante, également appelés doubles)
- **Boolean** (booléen)
- **Array** (tableau)
- **Object** (objet)
- **NULL** (une variable de type de données NULL est une variable à laquelle aucune valeur n'est attribuée)

### Exemple de types de données en PHP

```php
<?php
    $str = "Hello, PHP!";
    $int = 10;
    $float = 3.14;
    $bool = true;
    $arr = array("one", "two", "three");
    $obj = new stdClass();
    $null = null;

    var_dump($str);
    var_dump($int);
    var_dump($float);
    var_dump($bool);
    var_dump($arr);
    var_dump($obj);
    var_dump($null);
?>
```
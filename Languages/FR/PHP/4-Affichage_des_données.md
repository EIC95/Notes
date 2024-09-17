# Affichage des données en PHP

En PHP, il y a deux façons principales d'afficher des données : **`echo`** et **`print`**.

- **`echo`** n'a pas de valeur de retour.
- **`print`** retourne **1**, ce qui permet son utilisation dans des expressions.

### Exemple d'utilisation de `echo` et `print`

```php
<?php
    echo "Hello, world!";
    print "Hello, again!";
    
    $result = print("This will return 1");
    echo $result; // Affiche 1
?>
```
# Sessions en PHP

Une session permet de stocker des informations sur le serveur, accessibles sur plusieurs pages web. Contrairement aux cookies, qui sont stockés sur l'ordinateur de l'utilisateur, les sessions offrent une méthode plus sécurisée pour gérer des données utilisateur telles que les noms ou les préférences.

## Démarrer une session

Pour utiliser des sessions, commencez par appeler `session_start()` au début de votre script PHP, avant toute sortie HTML :

```php
<?php
session_start();
?>
```

## Stocker des données dans une session

Les variables de session sont stockées dans la superglobale `$_SESSION` :

```php
<?php
$_SESSION['user_name'] = 'Jean Dupont';
?>
```

## Supprimer des variables de session

Pour supprimer toutes les variables de session mais conserver la session active :

```php
<?php
session_unset();
?>
```

## Détruire une session

Pour supprimer toutes les variables de session et détruire la session :

```php
<?php
session_destroy();
?>
```

Pour un stockage permanent des données, il est recommandé d'utiliser une base de données, car les sessions sont effacées lorsque le navigateur est fermé.
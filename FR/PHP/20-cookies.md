# Cookies en PHP

## Création de cookies

Les cookies sont de petits fichiers stockés sur l'ordinateur de l'utilisateur par le serveur. Ils sont utilisés pour conserver des informations entre les sessions ou identifier l'utilisateur lors des visites ultérieures. En PHP, vous pouvez créer un cookie avec la fonction `setcookie()`. Cette fonction doit être appelée avant tout envoi de contenu HTML.

```php
<?php
// Définir un cookie
setcookie("nom", "valeur", time() + 3600, "/");
?>
```

### Paramètres de `setcookie()`

- **nom** : Nom du cookie.
- **valeur** : Valeur à stocker.
- **temps** : Expiration du cookie (timestamp Unix). Par exemple, `time() + 3600` pour une heure.
- **chemin** : Le chemin sur le serveur où le cookie est disponible ("/" pour tout le domaine).

## Récupération de Cookies

Pour accéder à la valeur d'un cookie, utilisez la superglobale `$_COOKIE`. Cette variable contient tous les cookies envoyés par le navigateur.

```php
<?php
// Accéder à un cookie
if(isset($_COOKIE["nom"])) {
    echo $_COOKIE["nom"];
}
?>
```

## Suppression de Cookies

Pour supprimer un cookie, vous devez définir son expiration à une date passée.

```php
<?php
// Supprimer un cookie
setcookie("nom", "", time() - 3600, "/");
?>
```

### Note

La suppression d'un cookie ne le retire pas immédiatement. Le navigateur doit recevoir l'instruction pour effacer le cookie à la prochaine requête.
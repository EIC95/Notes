# Variables superglobales en PHP

En PHP, certaines variables prédéfinies sont des **superglobales**, ce qui signifie qu'elles sont accessibles partout dans le script, quelle que soit leur portée. Elles sont automatiquement disponibles dans toutes les fonctions, classes, et fichiers.

## Liste des superglobales PHP

### `$_GET`
Cette superglobale contient les données envoyées en paramètres dans l'URL de la requête HTTP (méthode GET).

**Exemple :**

```php
<?php
// URL : example.com?nom=Ibrahima
echo $_GET['nom']; // Affiche "Ibrahima"
?>
```

### `$_POST`
Elle contient les données envoyées via un formulaire HTTP utilisant la méthode POST.

**Exemple :**

```php
<?php
// Formulaire avec méthode POST
echo $_POST['nom']; // Affiche la valeur saisie dans le champ "nom"
?>
```

### `$_SESSION`
Cette superglobale contient les variables de session, permettant de stocker des informations à travers plusieurs pages.

**Exemple :**

```php
<?php
session_start();
$_SESSION['user'] = "Ibrahima";
echo $_SESSION['user']; // Affiche "Ibrahima"
?>
```

### `$_COOKIE`
Elle contient les cookies envoyés par le navigateur.

**Exemple :**

```php
<?php
// Définir un cookie
setcookie("nom", "Ibrahima", time() + 3600);
echo $_COOKIE['nom']; // Affiche "Ibrahima"
?>
```

### `$_FILES`
Cette superglobale contient les informations des fichiers téléchargés via un formulaire HTML.

**Exemple :**

```php
<?php
// Téléchargement d'un fichier
echo $_FILES['monFichier']['name']; // Affiche le nom du fichier téléchargé
?>
```

### `$_ENV`
Elle contient les variables d'environnement.

**Exemple :**

```php
<?php
echo $_ENV['PATH']; // Affiche la variable d'environnement PATH
?>
```

### `$_SERVER`
Cette superglobale contient des informations sur le serveur et l'environnement d'exécution.

**Exemple :**

```php
<?php
echo $_SERVER['SERVER_NAME']; // Affiche le nom du serveur
?>
```

### `$_GLOBALS`
Elle contient une référence à toutes les variables globales disponibles dans le script.

**Exemple :**

```php
<?php
$nom = "Ibrahima";
echo $_GLOBALS['nom']; // Affiche "Ibrahima"
?>
```
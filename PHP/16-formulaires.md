# Gestion des formulaires en PHP

Un formulaire HTML contient des éléments de saisie tels que des champs de texte, des cases à cocher, des boutons radio, et des sélecteurs. Il spécifie une méthode (GET ou POST) et une action (le script PHP qui traitera les données).

## Méthodes GET et POST

- **GET** : Envoie les données via l'URL, visible par tous, limité à 2000 caractères. Ne pas utiliser pour envoyer des informations sensibles.
- **POST** : Envoie les données dans le corps de la requête, invisible, sans limite de taille. Recommandé pour l'envoi de données de formulaire.

Les données envoyées sont accessibles via les superglobales `$_GET` et `$_POST`.

## Sécurisation des formulaires

### Utilisation de `htmlspecialchars()`

L'utilisation de `htmlspecialchars()` en PHP est essentielle pour sécuriser les formulaires contre les attaques Cross-Site Scripting (XSS). Cette fonction convertit les caractères spéciaux en entités HTML, empêchant l'exécution de scripts malveillants injectés dans les URL ou les données de formulaire.

**Exemple :**

```php
<form method="post" action="<?php echo htmlspecialchars($_SERVER["PHP_SELF"]); ?>">
    Name: <input type="text" name="name">
    <input type="submit">
</form>
```

### Nettoyage des données de formulaire

Lors de la soumission d'un formulaire, il est important de nettoyer les données :

- **`trim()`** : Supprime les espaces inutiles (espace supplémentaire, tabulation, nouvelle ligne).
- **`stripslashes()`** : Supprime les barres obliques inverses `\` des données d'entrée utilisateur.

Vous pouvez créer une fonction pour effectuer ces vérifications :

```php
function test_input($data) {
    $data = trim($data);
    $data = stripslashes($data);
    $data = htmlspecialchars($data);
    return $data;
}
```

### Validation des champs

Pour valider les champs de formulaire, utilisez :

- **`empty()`** : Pour vérifier si un champ est vide.
- **`preg_match()`** : Pour valider des motifs comme des noms.
- **`filter_var()`** : Pour valider des adresses email.

**Exemple de validation :**

```php
if ($_SERVER["REQUEST_METHOD"] == "POST") {
    if (empty($_POST["name"])) {
        $nameErr = "Le nom est requis";
    } else {
        $name = test_input($_POST["name"]);
        if (!preg_match("/^[a-zA-Z-' ]*$/", $name)) {
            $nameErr = "Seules les lettres et espaces sont autorisés";
        }
    }
    
    if (empty($_POST["email"])) {
        $emailErr = "L'email est requis";
    } else {
        $email = test_input($_POST["email"]);
        if (!filter_var($email, FILTER_VALIDATE_EMAIL)) {
            $emailErr = "Format de l'email invalide";
        }
    }
}
```

### Affichage des messages d'erreur et conservation des données

Pour améliorer l'expérience utilisateur, vous pouvez afficher des messages d'erreur près des champs mal remplis et conserver les valeurs saisies après soumission, comme suit :

```php
<form method="post" action="<?php echo htmlspecialchars($_SERVER["PHP_SELF"]); ?>">
    Name: <input type="text" name="name" value="<?php echo $name;?>">
    <span class="error"><?php echo $nameErr;?></span>
    <br><br>
    E-mail: <input type="text" name="email" value="<?php echo $email;?>">
    <span class="error"><?php echo $emailErr;?></span>
    <br><br>
    <input type="submit" name="submit" value="Submit">
</form>
```
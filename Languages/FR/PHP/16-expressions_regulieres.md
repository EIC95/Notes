# Expressions Régulières en PHP

Une expression régulière est une séquence de caractères qui forme un modèle de recherche. Vous pouvez l'utiliser pour identifier des motifs dans une chaîne de caractères, faire des remplacements, ou encore vérifier la validité d'une saisie utilisateur.

## Fonctions Courantes pour les Expressions Régulières

### `preg_match()`

Renvoie `1` si le motif a été trouvé dans la chaîne, sinon renvoie `0`.

**Exemple :**

```php
<?php
$pattern = "/php/i";
$string = "J'apprends le PHP";

if (preg_match($pattern, $string)) {
    echo "Motif trouvé !";
} else {
    echo "Motif non trouvé.";
}
?>
```

### `preg_match_all()`

Renvoie le nombre de fois que le motif a été trouvé dans la chaîne, qui peut également être `0`.

**Exemple :**

```php
<?php
$pattern = "/a/i";
$string = "Ananas";
echo preg_match_all($pattern, $string); // Renvoie 3
?>
```

### `preg_replace()`

Renvoie une nouvelle chaîne où les motifs correspondants ont été remplacés par une autre chaîne.

**Exemple :**

```php
<?php
$pattern = "/le/i";
$replacement = "la";
$string = "J'apprends le PHP";
echo preg_replace($pattern, $replacement, $string); // Renvoie "J'apprends la PHP"
?>
```

### `preg_split()`

Divise une chaîne en un tableau en fonction d'un motif donné.

**Exemple :**

```php
<?php
$pattern = "/[\s,]+/";
$string = "PHP, JavaScript, Python";
$result = preg_split($pattern, $string);
print_r($result); // Renvoie un tableau : ["PHP", "JavaScript", "Python"]
?>
```

### `preg_grep()`

Renvoie un tableau contenant toutes les entrées d'un tableau qui correspondent à un motif.

**Exemple :**

```php
<?php
$pattern = "/php/i";
$array = ["PHP", "JavaScript", "Python"];
$result = preg_grep($pattern, $array);
print_r($result); // Renvoie un tableau avec "PHP"
?>
```

## Modificateurs d'Expressions Régulières

- **i** : Effectue une recherche insensible à la casse.
- **m** : Rend la recherche compatible avec les chaînes sur plusieurs lignes.
- **s** : Rend le caractère "." compatible avec les sauts de ligne.

## Classes de Caractères

- **\d** : Correspond à n'importe quel chiffre.
- **\w** : Correspond à une lettre, un chiffre ou un caractère de soulignement.
- **\s** : Correspond à un espace blanc (espace, tabulation, saut de ligne).
- **.** : Correspond à n'importe quel caractère, sauf les sauts de ligne.

**Exemple avec modificateurs :**

```php
<?php
$pattern = "/php/i"; // Recherche insensible à la casse
$string = "J'apprends le PHP et php.";
echo preg_match_all($pattern, $string); // Renvoie 2
?>
```
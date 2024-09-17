# L'inclusion de fichiers en PHP

L'inclusion de fichiers en PHP est une technique puissante pour réutiliser du code et organiser les projets en modules distincts. Cela permet de centraliser les fichiers communs comme les en-têtes, les pieds de page ou les fonctions dans un seul fichier, puis de les inclure dans plusieurs pages, simplifiant ainsi la maintenance et l'évolution du code.

## Différences entre `include` et `require`

### `include`

L'instruction `include` tente d'inclure le fichier spécifié et, en cas d'échec (par exemple, si le fichier est manquant), elle déclenche un **avertissement** (E_WARNING) mais continue d'exécuter le reste du script.

**Exemple :**

```php
<?php
include 'header.php'; // Si le fichier n'existe pas, un avertissement est généré, mais le script continue
?>
```

### `require`

L'instruction `require` fonctionne de manière similaire à `include`, sauf qu'en cas d'échec, elle déclenche une **erreur fatale** (E_COMPILE_ERROR) et arrête l'exécution du script. Utilisez `require` pour les fichiers critiques au bon fonctionnement du script, comme les fichiers de configuration ou les classes essentielles.

**Exemple :**

```php
<?php
require 'config.php'; // Si le fichier n'existe pas, le script s'arrête
?>
```

## Prévention de la double inclusion avec `include_once` et `require_once`

Les instructions `include_once` et `require_once` ajoutent une vérification supplémentaire : elles garantissent que le fichier ne sera inclus qu'une seule fois, même si l'inclusion est demandée plusieurs fois dans le script. Cela évite des erreurs comme la redéfinition de classes, fonctions ou constantes.

### `include_once`

Utilisez `include_once` lorsque vous souhaitez inclure un fichier, mais que vous êtes prêt à gérer une éventuelle absence du fichier tout en évitant la double inclusion.

**Exemple :**

```php
<?php
include_once 'menu.php'; // Le fichier sera inclus une seule fois
?>
```

### `require_once`

Comme `require`, `require_once` arrête le script si le fichier requis est manquant, mais il empêche aussi la double inclusion du fichier.

**Exemple :**

```php
<?php
require_once 'database.php'; // Le fichier sera requis une seule fois, sinon le script s'arrête
?>
```
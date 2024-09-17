# Connexion à une base de données MySQL avec PDO

Pour se connecter à une base de données MySQL avec PDO, il faut créer une instance de la classe `PDO`. Voici les principales opérations que vous pouvez effectuer :

## Création de la connexion

```php
<?php
$dsn = 'mysql:host=localhost;dbname=nom_de_la_base';
$user = 'utilisateur';
$pass = 'mot_de_passe';

try {
    $pdo = new PDO($dsn, $user, $pass);
    $pdo->setAttribute(PDO::ATTR_ERRMODE, PDO::ERRMODE_EXCEPTION);
} catch (PDOException $e) {
    echo 'Échec de la connexion : ' . $e->getMessage();
}
?>
```

## Exécution d'une requête SQL simple

```php
<?php
$sql = 'SELECT * FROM table';
$stmt = $pdo->query($sql);
$result = $stmt->fetchAll(PDO::FETCH_ASSOC);
?>
```

## Requêtes préparées

Pour des requêtes plus sécurisées, utilisez des requêtes préparées avec des paramètres.

### Exemple avec paramètres positionnels

```php
<?php
$sql = 'SELECT * FROM table WHERE id = ?';
$stmt = $pdo->prepare($sql);
$stmt->execute([$id]);
$result = $stmt->fetchAll(PDO::FETCH_ASSOC);
?>
```

### Exemple avec paramètres nommés

```php
<?php
$sql = 'SELECT * FROM table WHERE id = :id';
$stmt = $pdo->prepare($sql);
$stmt->execute([':id' => $id]);
$result = $stmt->fetchAll(PDO::FETCH_ASSOC);
?>
```

## Insertion de données

```php
<?php
$sql = 'INSERT INTO table (colonne1, colonne2) VALUES (:valeur1, :valeur2)';
$stmt = $pdo->prepare($sql);
$stmt->execute([
    ':valeur1' => $valeur1,
    ':valeur2' => $valeur2
]);
?>
```

## Mise à jour de données

```php
<?php
$sql = 'UPDATE table SET colonne1 = :valeur WHERE id = :id';
$stmt = $pdo->prepare($sql);
$stmt->execute([
    ':valeur' => $valeur,
    ':id' => $id
]);
?>
```

## Suppression de données

```php
<?php
$sql = 'DELETE FROM table WHERE id = :id';
$stmt = $pdo->prepare($sql);
$stmt->execute([':id' => $id]);
?>
```

## Transactions

Pour exécuter plusieurs requêtes en une seule transaction, utilisez les méthodes suivantes :

```php
<?php
try {
    $pdo->beginTransaction();

    // Exécuter plusieurs requêtes
    $pdo->exec('INSERT INTO table (colonne) VALUES (valeur)');
    $pdo->exec('UPDATE table SET colonne = valeur WHERE id = id');

    $pdo->commit();
} catch (Exception $e) {
    $pdo->rollBack();
    echo 'Échec de la transaction : ' . $e->getMessage();
}
?>
```
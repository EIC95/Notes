# Injection SQL et Protection

## Qu'est-ce que l'Injection SQL ?

L'injection SQL est une technique de piratage où un attaquant insère du code SQL malveillant dans les entrées d'un formulaire Web ou d'une URL pour manipuler les instructions SQL exécutées par la base de données. Cette vulnérabilité peut permettre à un attaquant d'accéder, de modifier ou de supprimer des données, ou même de compromettre l'intégrité de la base de données.

### Exemple d'Injection SQL

Supposons que vous ayez une page de connexion qui accepte un nom d'utilisateur et un mot de passe. Si la requête SQL utilisée pour vérifier les informations de connexion est la suivante :

```sql
SELECT * FROM utilisateurs WHERE nom_utilisateur = 'input_nom_utilisateur' AND mot_de_passe = 'input_mot_de_passe';
```

Un utilisateur malveillant pourrait entrer dans le champ "nom_utilisateur" la chaîne suivante :

```sql
' OR '1'='1
```

Cela transformerait la requête SQL en :

```sql
SELECT * FROM utilisateurs WHERE nom_utilisateur = '' OR '1'='1' AND mot_de_passe = 'input_mot_de_passe';
```

Cette requête est toujours vraie (car '1'='1' est toujours vrai) et pourrait permettre à l'attaquant de se connecter sans fournir de véritable nom d'utilisateur ou mot de passe.

## Protection Contre l'Injection SQL

### Utilisation de Paramètres SQL

Pour se protéger contre l'injection SQL, il est recommandé d'utiliser des requêtes préparées avec des paramètres SQL. Les paramètres permettent de séparer le code SQL des données, empêchant ainsi l'injection de code malveillant.

#### Exemple en PHP avec PDO

```php
// Connexion à la base de données
$pdo = new PDO('mysql:host=localhost;dbname=test', 'username', 'password');

// Préparation de la requête
$stmt = $pdo->prepare('SELECT * FROM utilisateurs WHERE nom_utilisateur = :nom_utilisateur AND mot_de_passe = :mot_de_passe');

// Lier les paramètres
$stmt->bindParam(':nom_utilisateur', $nom_utilisateur);
$stmt->bindParam(':mot_de_passe', $mot_de_passe);

// Exécuter la requête
$stmt->execute();
```

### Bonnes Pratiques

1. **Utiliser des Requêtes Préparées** : Préférer les requêtes préparées avec des paramètres pour toutes les interactions avec la base de données.
2. **Éviter les Requêtes Dynamiques** : Réduire l'utilisation de requêtes SQL dynamiques qui incluent des valeurs directement.
3. **Valider et Échapper les Entrées Utilisateur** : Toujours valider et échapper les entrées utilisateur pour s'assurer qu'elles ne contiennent pas de code malveillant.
4. **Limiter les Privilèges de la Base de Données** : Accordez le minimum de privilèges nécessaires aux comptes de base de données utilisés par votre application.

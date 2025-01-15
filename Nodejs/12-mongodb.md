# Connexion de Node.js à MongoDB

Pour connecter **Node.js** à **MongoDB**, vous pouvez utiliser le **MongoDB Node.js Driver** ou **Mongoose**. Dans MongoDB, la création d'une base de données se fait automatiquement lors de la première utilisation. Vous n'avez pas besoin de créer explicitement la base de données avant de vous y connecter. Voici comment cela fonctionne avec **Mongoose**.

## 1. Connexion avec MongoDB Node.js Driver

### Étape 1 : Installer le MongoDB Node.js Driver
Exécutez la commande suivante pour installer le driver MongoDB pour Node.js :

```bash
npm install mongodb
```

### Étape 2 : Connexion à MongoDB

Voici comment établir une connexion avec MongoDB en utilisant le **MongoDB Node.js Driver** sans les options supplémentaires :

```javascript
const { MongoClient } = require('mongodb');

// URL de connexion à MongoDB
const url = 'mongodb://localhost:27017'; // Remplacez par l'URL de votre base de données MongoDB
const dbName = 'maBaseDeDonnees'; // Remplacez par le nom de votre base de données

// Créez une instance MongoClient
const client = new MongoClient(url);

client.connect(function(err) {
  if (err) {
    console.error('Erreur de connexion à MongoDB', err);
    return;
  }
  
  console.log('Connecté à MongoDB');

  // Accédez à la base de données
  const db = client.db(dbName);
  
  // Vous pouvez maintenant effectuer des opérations sur la base de données

  // N'oubliez pas de fermer la connexion après usage
  client.close();
});
```

### Explication :
- **`MongoClient.connect()`** : Méthode utilisée pour se connecter à MongoDB. Elle prend un callback pour gérer la connexion.
- **`client.db(dbName)`** : Accède à la base de données spécifiée.
- **`client.close()`** : Ferme la connexion à MongoDB après usage.

## 2. Connexion avec Mongoose

Si vous préférez utiliser **Mongoose**, un ORM pour MongoDB, voici la méthode pour vous connecter sans les options supplémentaires :

### Étape 1 : Installer Mongoose
Exécutez la commande suivante pour installer **Mongoose** :

```bash
npm install mongoose
```

### Étape 2 : Connexion à MongoDB avec Mongoose

```javascript
const mongoose = require('mongoose');

// URL de connexion à MongoDB
const url = 'mongodb://localhost:27017/maBaseDeDonnees'; // Remplacez par l'URL de votre base de données

mongoose.connect(url, function(err) {
  if (err) {
    console.error('Erreur de connexion à MongoDB avec Mongoose', err);
    return;
  }
  
  console.log('Connecté à MongoDB avec Mongoose');
  
  // Vous pouvez maintenant effectuer des opérations sur la base de données

  // Fermez la connexion après usage
  mongoose.connection.close();
});
```

### Explication :
- **`mongoose.connect()`** : Méthode utilisée pour établir la connexion à MongoDB. Elle prend un callback pour gérer la connexion.
- **`mongoose.connection.close()`** : Ferme la connexion à MongoDB après usage.

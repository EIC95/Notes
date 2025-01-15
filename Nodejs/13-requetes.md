# **MongoDB avec Node.js - Actions Courantes**


## **1. Connexion à la base de données**

Pour utiliser MongoDB avec Node.js sans Mongoose, vous pouvez vous connecter directement à la base de données en utilisant le **MongoDB Native Driver**.

#### Exemple de connexion :

```javascript
const MongoClient = require('mongodb').MongoClient;

const url = 'mongodb://localhost:27017';
const dbName = 'maBaseDeDonnees';

MongoClient.connect(url, function(err, client) {
  if (err) {
    console.error('Erreur de connexion', err);
    return;
  }

  console.log('Connecté à la base de données');
  const db = client.db(dbName);

  // Fermer la connexion après utilisation
  client.close();
});
```

---

## **2. Création de base de données**

MongoDB crée une base de données automatiquement lors de la première opération (par exemple, une insertion de données) si elle n'existe pas déjà.

#### Exemple de création de base de données (par insertion) :

```javascript
const MongoClient = require('mongodb').MongoClient;

const url = 'mongodb://localhost:27017';
const dbName = 'maBaseDeDonnees';

MongoClient.connect(url, function(err, client) {
  if (err) {
    console.error('Erreur de connexion', err);
    return;
  }

  console.log('Connecté à la base de données');
  const db = client.db(dbName);

  // Insertion d'un document pour créer la base de données
  const collection = db.collection('utilisateurs');
  collection.insertOne({ nom: 'Jean', age: 30 }, function(err, res) {
    if (err) {
      console.error('Erreur d\'insertion', err);
      return;
    }
    console.log('Document inséré et base de données créée');
    client.close();
  });
});
```

---

## **3. Insertion de données (insertOne, insertMany)**

Vous pouvez insérer un ou plusieurs documents dans une collection.

#### Exemple avec `insertOne()` :

```javascript
const MongoClient = require('mongodb').MongoClient;

const url = 'mongodb://localhost:27017';
const dbName = 'maBaseDeDonnees';

MongoClient.connect(url, function(err, client) {
  if (err) {
    console.error('Erreur de connexion', err);
    return;
  }

  const db = client.db(dbName);
  const collection = db.collection('utilisateurs');

  collection.insertOne({ nom: 'Marie', age: 25 }, function(err, res) {
    if (err) {
      console.error('Erreur d\'insertion', err);
      return;
    }
    console.log('Document inséré');
    client.close();
  });
});
```

#### Exemple avec `insertMany()` :

```javascript
const MongoClient = require('mongodb').MongoClient;

const url = 'mongodb://localhost:27017';
const dbName = 'maBaseDeDonnees';

MongoClient.connect(url, function(err, client) {
  if (err) {
    console.error('Erreur de connexion', err);
    return;
  }

  const db = client.db(dbName);
  const collection = db.collection('utilisateurs');

  collection.insertMany([{ nom: 'Paul', age: 28 }, { nom: 'Alice', age: 22 }], function(err, res) {
    if (err) {
      console.error('Erreur d\'insertion', err);
      return;
    }
    console.log('Documents insérés');
    client.close();
  });
});
```

---

## **4. Recherche de données (find, findOne)**

### Exemple avec `find()` pour plusieurs documents :

```javascript
const MongoClient = require('mongodb').MongoClient;

const url = 'mongodb://localhost:27017';
const dbName = 'maBaseDeDonnees';

MongoClient.connect(url, function(err, client) {
  if (err) {
    console.error('Erreur de connexion', err);
    return;
  }

  const db = client.db(dbName);
  const collection = db.collection('utilisateurs');

  collection.find({ age: { $gt: 20 } }).toArray(function(err, utilisateurs) {
    if (err) {
      console.error('Erreur de recherche', err);
      return;
    }
    console.log('Utilisateurs trouvés :', utilisateurs);
    client.close();
  });
});
```

### Exemple avec `findOne()` pour un seul document :

```javascript
const MongoClient = require('mongodb').MongoClient;

const url = 'mongodb://localhost:27017';
const dbName = 'maBaseDeDonnees';

MongoClient.connect(url, function(err, client) {
  if (err) {
    console.error('Erreur de connexion', err);
    return;
  }

  const db = client.db(dbName);
  const collection = db.collection('utilisateurs');

  collection.findOne({ nom: 'Jean' }, function(err, utilisateur) {
    if (err) {
      console.error('Erreur de recherche', err);
      return;
    }
    console.log('Utilisateur trouvé :', utilisateur);
    client.close();
  });
});
```

---

## **5. Mise à jour de données (updateOne, updateMany)**

### Exemple avec `updateOne()` :

```javascript
const MongoClient = require('mongodb').MongoClient;

const url = 'mongodb://localhost:27017';
const dbName = 'maBaseDeDonnees';

MongoClient.connect(url, function(err, client) {
  if (err) {
    console.error('Erreur de connexion', err);
    return;
  }

  const db = client.db(dbName);
  const collection = db.collection('utilisateurs');

  collection.updateOne({ nom: 'Jean' }, { $set: { age: 31 } }, function(err, res) {
    if (err) {
      console.error('Erreur de mise à jour', err);
      return;
    }
    console.log('Document mis à jour');
    client.close();
  });
});
```

### Exemple avec `updateMany()` :

```javascript
const MongoClient = require('mongodb').MongoClient;

const url = 'mongodb://localhost:27017';
const dbName = 'maBaseDeDonnees';

MongoClient.connect(url, function(err, client) {
  if (err) {
    console.error('Erreur de connexion', err);
    return;
  }

  const db = client.db(dbName);
  const collection = db.collection('utilisateurs');

  collection.updateMany({ age: { $lt: 30 } }, { $set: { age: 30 } }, function(err, res) {
    if (err) {
      console.error('Erreur de mise à jour', err);
      return;
    }
    console.log('Documents mis à jour');
    client.close();
  });
});
```

---

## **6. Suppression de données (deleteOne, deleteMany)**

### Exemple avec `deleteOne()` :

```javascript
const MongoClient = require('mongodb').MongoClient;

const url = 'mongodb://localhost:27017';
const dbName = 'maBaseDeDonnees';

MongoClient.connect(url, function(err, client) {
  if (err) {
    console.error('Erreur de connexion', err);
    return;
  }

  const db = client.db(dbName);
  const collection = db.collection('utilisateurs');

  collection.deleteOne({ nom: 'Jean' }, function(err, res) {
    if (err) {
      console.error('Erreur de suppression', err);
      return;
    }
    console.log('Document supprimé');
    client.close();
  });
});
```

### Exemple avec `deleteMany()` :

```javascript
const MongoClient = require('mongodb').MongoClient;

const url = 'mongodb://localhost:27017';
const dbName = 'maBaseDeDonnees';

MongoClient.connect(url, function(err, client) {
  if (err) {
    console.error('Erreur de connexion', err);
    return;
  }

  const db = client.db(dbName);
  const collection = db.collection('utilisateurs');

  collection.deleteMany({ age: { $lt: 30 } }, function(err, res) {
    if (err) {
      console.error('Erreur de suppression', err);
      return;
    }
    console.log('Documents supprimés');
    client.close();
  });
});
```

---

## **7. Tri des résultats (sort)**

Vous pouvez trier les documents d'une collection en utilisant la méthode `sort()`.

### Exemple de tri par âge croissant :

```javascript
const MongoClient = require('mongodb').MongoClient;

const url = 'mongodb://localhost:27017';
const dbName = 'maBaseDeDonnees';

MongoClient.connect(url, function(err, client) {
  if (err) {
    console.error('Erreur de connexion', err);
    return;
  }

  const db = client.db(dbName);
  const collection = db.collection('utilisateurs');

  collection.find().sort({ age: 1 }).toArray(function(err, utilisateurs) {
    if (err) {
      console.error('Erreur de recherche', err);
      return;
    }
    console.log('Utilisateurs triés par âge croissant :', utilisateurs);
    client.close();
  });
});
```

### Exemple de tri par âge décroissant :

```javascript
const MongoClient = require('mongodb').MongoClient;

const url = 'mongodb://localhost:27017';
const dbName = 'maBaseDeDonnees';

MongoClient.connect(url, function(err, client) {
  if (err) {
    console.error('Erreur de connexion', err);
    return;
  }

  const db = client.db(dbName);
  const collection = db.collection('utilisateurs');

  collection.find().sort({ age: -1 }).toArray(function(err, utilisateurs) {
    if (err) {
      console.error('Erreur de recherche', err);
      return;
    }
    console.log('Utilisateurs triés par âge décroissant :', utilisateurs);
    client.close();
  });
});
```

---

## **8. Limitation des résultats (limit)**

La méthode `limit()` permet de limiter le nombre de documents retournés.

### Exemple de limitation à 3 documents :

```javascript
const MongoClient = require('mongodb').MongoClient;

const url = 'mongodb://localhost:27017';
const dbName = 'maBaseDeDonnees';

MongoClient.connect(url, function(err, client) {
  if (err) {
    console.error('Erreur de connexion', err);
    return;
  }

  const db = client.db(dbName);
  const collection = db.collection('utilisateurs');

  collection.find().limit(3).toArray(function(err, utilisateurs) {
    if (err) {
      console.error('Erreur de recherche', err);
      return;
    }
    console.log('Utilisateurs (limités à 3) :', utilisateurs);
    client.close();
  });
});
```

---

## **9. Agrégation (aggregate)**

L'agrégation permet d'effectuer des opérations complexes sur les données, telles que des filtres, des groupements, des tris, etc.

### Exemple d'agrégation pour filtrer et compter les utilisateurs par âge :

```javascript
const MongoClient = require('mongodb').MongoClient;

const url = 'mongodb://localhost:27017';
const dbName = 'maBaseDeDonnees';

MongoClient.connect(url, function(err, client) {
  if (err) {
    console.error('Erreur de connexion', err);
    return;
  }

  const db = client.db(dbName);
  const collection = db.collection('utilisateurs');

  collection.aggregate([
    { $match: { age: { $gt: 20 } } },  // Filtrer les utilisateurs de plus de 20 ans
    { $group: { _id: "$age", count: { $sum: 1 } } }  // Compter les utilisateurs par âge
  ]).toArray(function(err, result) {
    if (err) {
      console.error('Erreur d\'agrégation', err);
      return;
    }
    console.log('Résultats de l\'agrégation :', result);
    client.close();
  });
});
```

### Exemple d'agrégation pour obtenir la somme des âges :

```javascript
const MongoClient = require('mongodb').MongoClient;

const url = 'mongodb://localhost:27017';
const dbName = 'maBaseDeDonnees';

MongoClient.connect(url, function(err, client) {
  if (err) {
    console.error('Erreur de connexion', err);
    return;
  }

  const db = client.db(dbName);
  const collection = db.collection('utilisateurs');

  collection.aggregate([
    { $group: { _id: null, totalAge: { $sum: "$age" } } }  // Somme des âges
  ]).toArray(function(err, result) {
    if (err) {
      console.error('Erreur d\'agrégation', err);
      return;
    }
    console.log('Somme des âges :', result);
    client.close();
  });
});
```
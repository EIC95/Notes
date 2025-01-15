# Les modéles

L'utilisation d'un **modèle** avec **Mongoose** n'est pas obligatoire, mais elle est fortement recommandée dans la plupart des cas. Voici pourquoi :

## **1. Utilisation de Mongoose sans modèle :**
Mongoose vous permet d'interagir avec MongoDB sans avoir à créer un modèle, en utilisant directement le client MongoDB via `mongoose.connection` ou en utilisant le **MongoDB native driver**. Cependant, dans ce cas, vous perdez les avantages de la validation, de la gestion des relations, des méthodes de modèle et des fonctionnalités supplémentaires que Mongoose fournit avec un modèle.

## **Exemple sans modèle (avec MongoDB natif via Mongoose) :**

```javascript
const mongoose = require('mongoose');

// Connexion à la base de données
mongoose.connect('mongodb://localhost:27017/maBaseDeDonnees');

// Utilisation directe de la collection
mongoose.connection.once('open', function() {
  mongoose.connection.db.collection('utilisateurs').insertOne({ nom: 'Alice', age: 25 }, function(err, res) {
    if (err) {
      console.error('Erreur d\'insertion', err);
    } else {
      console.log('Document inséré sans modèle');
    }
    mongoose.connection.close();
  });
});
```

Dans cet exemple, on insère directement un document dans la collection `utilisateurs` sans utiliser de modèle Mongoose.

---

## **2. Utilisation d'un modèle :**

Lorsque vous créez un modèle, Mongoose vous permet de définir des règles de validation, de manipuler les données plus facilement, et d'appliquer des méthodes spécifiques à ce modèle.

Voici un exemple d'insertion en utilisant un modèle :

```javascript
const mongoose = require('mongoose');

// Création d'un schéma et d'un modèle
const utilisateurSchema = new mongoose.Schema({
  nom: String,
  age: Number
});

const Utilisateur = mongoose.model('Utilisateur', utilisateurSchema);

// Connexion à la base de données
mongoose.connect('mongodb://localhost:27017/maBaseDeDonnees');

mongoose.connection.once('open', function() {
  // Insertion via le modèle
  const utilisateur = new Utilisateur({ nom: 'Alice', age: 25 });
  utilisateur.save(function(err) {
    if (err) {
      console.error('Erreur d\'insertion', err);
    } else {
      console.log('Document inséré avec modèle');
    }
    mongoose.connection.close();
  });
});
```

## **Pourquoi utiliser un modèle ?**

1. **Validation** : Vous pouvez valider les données avant de les enregistrer dans la base de données.
2. **Middleware** : Vous pouvez utiliser des middlewares (avant/après des opérations comme `save()`, `find()`, etc.).
3. **Méthodes de modèle** : Vous pouvez ajouter des méthodes personnalisées au modèle, comme des fonctions qui traitent les données avant de les renvoyer.
4. **Facilité d'utilisation** : Mongoose fournit des méthodes pratiques comme `save()`, `find()`, `update()`, et `remove()` qui rendent l'interaction avec la base de données plus intuitive et moins sujette aux erreurs.

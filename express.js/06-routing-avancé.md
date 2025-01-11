# Routing Avancé avec Express.js

## 1. Routage Dynamique

Le routage dynamique permet de capturer des parties variables de l'URL, appelées **paramètres de route**. Cela permet de créer des routes flexibles où la ressource est définie dynamiquement dans l'URL.

### Exemple : Route Dynamique avec un Paramètre
```js
app.get('/user/:id', (req, res) => {
  const userId = req.params.id;  // Accéder au paramètre 'id' de l'URL
  res.send(`Profil de l'utilisateur avec ID: ${userId}`);
});
```

**Explication** : 
- `:id` est un paramètre dynamique dans l'URL. Si l'utilisateur accède à `/user/123`, `req.params.id` sera égal à `123`.

### Exemple : Route avec Plusieurs Paramètres Dynamiques
```js
app.get('/product/:category/:id', (req, res) => {
  const category = req.params.category;
  const productId = req.params.id;
  res.send(`Produit ${productId} dans la catégorie ${category}`);
});
```

**Explication** : 
- Cette route capture deux paramètres dynamiques : `category` et `id`.

## 2. Routage Imbriqué

Le routage imbriqué permet de structurer les routes de manière modulaire, avec des sous-routes définies à l'intérieur d'une route principale. Cela permet d'organiser les routes de manière plus propre, surtout pour les applications de grande taille.

### Exemple : Utilisation de `express.Router()`
```js
const express = require('express');
const app = express();
const userRouter = express.Router();

// Définir des routes dans le router 'userRouter'
userRouter.get('/', (req, res) => {
  res.send('Liste des utilisateurs');
});

userRouter.get('/:id', (req, res) => {
  res.send(`Profil de l'utilisateur avec ID: ${req.params.id}`);
});

// Utiliser 'userRouter' pour gérer toutes les routes qui commencent par '/user'
app.use('/user', userRouter);

app.listen(3000, () => {
  console.log('Serveur en cours d\'exécution sur le port 3000');
});
```

**Explication** : 
- Nous avons créé un `userRouter` pour regrouper les routes liées aux utilisateurs.
- Ensuite, nous avons monté `userRouter` sur le chemin `/user` avec `app.use('/user', userRouter)`.

## 3. Utilisation de Fichiers Séparés pour Organiser les Routes

Pour une meilleure organisation, surtout dans des applications plus complexes, il est recommandé de séparer les routes en différents fichiers.

### Exemple : Séparation des Routes dans des Fichiers Différents

#### Fichier `routes/users.js` :
```js
const express = require('express');
const router = express.Router();

// Route pour obtenir la liste des utilisateurs
router.get('/', (req, res) => {
  res.send('Liste des utilisateurs');
});

// Route pour obtenir un utilisateur par ID
router.get('/:id', (req, res) => {
  res.send(`Profil de l'utilisateur avec ID: ${req.params.id}`);
});

module.exports = router;
```

#### Fichier `routes/products.js` :
```js
const express = require('express');
const router = express.Router();

// Route pour obtenir la liste des produits
router.get('/', (req, res) => {
  res.send('Liste des produits');
});

// Route pour obtenir un produit par ID
router.get('/:id', (req, res) => {
  res.send(`Produit avec ID: ${req.params.id}`);
});

module.exports = router;
```

#### Fichier principal `app.js` :
```js
const express = require('express');
const app = express();

// Importer les fichiers de routes
const userRoutes = require('./routes/users');
const productRoutes = require('./routes/products');

// Utiliser les routes dans l'application
app.use('/users', userRoutes);
app.use('/products', productRoutes);

app.listen(3000, () => {
  console.log('Serveur en cours d\'exécution sur le port 3000');
});
```

**Explication** : 
- Les routes pour les utilisateurs et les produits sont séparées dans des fichiers distincts.
- `app.use('/users', userRoutes)` permet de lier le fichier `users.js` aux routes qui commencent par `/users`, et de même pour `products.js`.

## 4. Routes avec des Méthodes HTTP Différentes

Une même route peut répondre à différentes méthodes HTTP, permettant ainsi de gérer les actions sur une même ressource selon l'action souhaitée (lecture, création, mise à jour, suppression).

### Exemple : Routes avec Différentes Méthodes HTTP
```js
const express = require('express');
const app = express();

app.use(express.json()); // Pour parser les requêtes JSON

// Route GET pour obtenir un produit
app.get('/product/:id', (req, res) => {
  res.send(`Produit avec ID: ${req.params.id}`);
});

// Route POST pour créer un produit
app.post('/product', (req, res) => {
  const newProduct = req.body;
  res.status(201).send(`Produit créé: ${newProduct.name}`);
});

// Route PUT pour mettre à jour un produit
app.put('/product/:id', (req, res) => {
  const updatedProduct = req.body;
  res.send(`Produit avec ID: ${req.params.id} mis à jour`);
});

// Route DELETE pour supprimer un produit
app.delete('/product/:id', (req, res) => {
  res.send(`Produit avec ID: ${req.params.id} supprimé`);
});

app.listen(3000, () => {
  console.log('Serveur en cours d\'exécution sur le port 3000');
});
```

**Explication** : 
- Nous utilisons les méthodes HTTP `GET`, `POST`, `PUT` et `DELETE` pour effectuer des actions différentes sur la ressource `product`.

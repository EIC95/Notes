# **Implémentation de l'Enregistrement et de la Connexion des Utilisateurs avec MongoDB**

### **Enregistrement d'un Utilisateur**
L'enregistrement d'un utilisateur implique la création d'un nouveau document dans une collection d'utilisateurs dans MongoDB. Ce processus nécessite généralement la collecte des informations suivantes :
- Nom d'utilisateur (ou adresse e-mail)
- Mot de passe (qui doit être sécurisé avant d'être stocké)

#### Exemple d'enregistrement d'un utilisateur :

1. **Installation des dépendances** :
   - `express` pour gérer les requêtes HTTP.
   - `bcrypt` pour le hachage du mot de passe.
   - `mongodb` pour interagir avec MongoDB.

   ```bash
   npm install express bcrypt mongodb
   ```

2. **Code pour l'enregistrement de l'utilisateur** :

   ```javascript
   const express = require('express');
   const bcrypt = require('bcrypt');
   const MongoClient = require('mongodb').MongoClient;

   const app = express();
   const url = 'mongodb://localhost:27017';
   const dbName = 'maBaseDeDonnees';
   const client = new MongoClient(url);

   app.use(express.json());

   app.post('/register', async (req, res) => {
     const { username, password } = req.body;

     if (!username || !password) {
       return res.status(400).send('Nom d\'utilisateur et mot de passe requis');
     }

     // Hachage du mot de passe
     const hashedPassword = await bcrypt.hash(password, 10);

     try {
       await client.connect();
       const db = client.db(dbName);
       const collection = db.collection('utilisateurs');

       const user = { username, password: hashedPassword };
       const result = await collection.insertOne(user);

       res.status(201).send('Utilisateur enregistré');
     } catch (err) {
       res.status(500).send('Erreur lors de l\'enregistrement');
     } finally {
       client.close();
     }
   });

   app.listen(3000, () => {
     console.log('Serveur démarré sur le port 3000');
   });
   ```

- Dans cet exemple, le mot de passe de l'utilisateur est haché avant d'être stocké dans MongoDB. Cela garantit que même si la base de données est compromise, les mots de passe ne seront pas visibles en clair.

### **Connexion de l'Utilisateur**
Lors de la connexion, l'utilisateur fournit son nom d'utilisateur et son mot de passe. Le mot de passe est comparé au mot de passe haché stocké dans la base de données.

#### Exemple de connexion d'un utilisateur :

1. **Code pour la connexion de l'utilisateur** :

   ```javascript
   app.post('/login', async (req, res) => {
     const { username, password } = req.body;

     if (!username || !password) {
       return res.status(400).send('Nom d\'utilisateur et mot de passe requis');
     }

     try {
       await client.connect();
       const db = client.db(dbName);
       const collection = db.collection('utilisateurs');

       const user = await collection.findOne({ username });

       if (!user) {
         return res.status(404).send('Utilisateur non trouvé');
       }

       // Vérification du mot de passe
       const match = await bcrypt.compare(password, user.password);

       if (match) {
         res.status(200).send('Connexion réussie');
       } else {
         res.status(400).send('Mot de passe incorrect');
       }
     } catch (err) {
       res.status(500).send('Erreur lors de la connexion');
     } finally {
       client.close();
     }
   });
   ```

- Dans cet exemple, après la vérification du mot de passe, un message est envoyé pour informer l'utilisateur si la connexion a réussi ou échoué. Si l'utilisateur n'existe pas ou si le mot de passe est incorrect, une erreur est retournée.

---

### **Sécurisation des Mots de Passe**
- **Hachage avec bcrypt** : Le mot de passe de l'utilisateur ne doit jamais être stocké en clair dans la base de données. L'utilisation de `bcrypt` permet de hacher le mot de passe avant de l'enregistrer, offrant ainsi une couche de sécurité supplémentaire.
- **Salage** : `bcrypt` applique un "sel" (salt) au mot de passe, ce qui rend chaque hachage unique, même si deux utilisateurs ont le même mot de passe.

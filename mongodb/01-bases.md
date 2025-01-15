# Introduction à MongoDB

MongoDB est une base de données NoSQL qui stocke des données sous forme de documents BSON (Binary JSON). Il est utilisé pour des applications nécessitant une grande évolutivité et des données non structurées.

## Connexion à MongoDB

### 1. Se connecter à MongoDB localement
Par défaut, MongoDB fonctionne sur le port `27017` de votre machine locale. Si vous êtes sur la même machine que le serveur MongoDB, vous pouvez vous connecter en tapant simplement :
```bash
mongosh
```

Si vous vous connectez à un serveur distant ou à un autre port, utilisez l'URL de connexion suivante :
```bash
mongosh "mongodb://adresse_ip:port"
```

### 2. Afficher les bases de données existantes
Une fois connecté, vous pouvez lister toutes les bases de données existantes sur le serveur avec la commande suivante :
```bash
show dbs
```

### 3. Créer une nouvelle base de données
Pour créer une nouvelle base de données, utilisez la commande `use` suivie du nom de la base de données. Si la base de données n'existe pas, MongoDB la créera automatiquement lorsque vous ajouterez des données :
```bash
use ma_nouvelle_db
```

### 4. Afficher la base de données actuelle
Pour voir quelle base de données vous utilisez actuellement, tapez :
```bash
db
```

### 5. Afficher les collections d'une base de données
Les **collections** dans MongoDB sont l'équivalent des tables dans une base de données relationnelle. Pour lister les collections de la base de données actuelle :
```bash
show collections
```

## Utiliser MongoDB Atlas

**MongoDB Atlas** est la version cloud de MongoDB, qui permet de déployer, gérer et faire évoluer des bases de données MongoDB sur le cloud (AWS, Google Cloud, ou Azure). Voici comment l'utiliser :

### 1. Créer un compte MongoDB Atlas
1. Rendez-vous sur [MongoDB Atlas](https://www.mongodb.com/cloud/atlas) et créez un compte si vous n'en avez pas déjà un.
2. Une fois votre compte créé, vous pouvez créer un nouveau cluster en choisissant l'option gratuite (M0), qui est suffisante pour des tests et des petits projets.

### 2. Créer un cluster MongoDB
1. Après avoir créé un compte et vous être connecté à Atlas, cliquez sur "Build a Cluster".
2. Choisissez le fournisseur de cloud, la région, et sélectionnez un plan (choisissez "M0" pour le plan gratuit).
3. Une fois le cluster créé, cela peut prendre quelques minutes.

### 3. Configurer les utilisateurs et les permissions
1. Dans le tableau de bord d'Atlas, allez dans l'onglet **Database Access** pour créer un utilisateur de base de données.
2. Cliquez sur **Add New Database User**, attribuez un nom d'utilisateur, un mot de passe et définissez les permissions.

### 4. Se connecter à MongoDB Atlas avec `mongosh`
1. Allez dans l'onglet **Connect** dans votre cluster Atlas.
2. Choisissez **Connect with MongoDB Shell**.
3. Copiez l'URL de connexion fournie par Atlas et utilisez-la pour vous connecter à votre cluster :
   ```bash
   mongosh "mongodb+srv://<username>:<password>@<cluster-name>.mongodb.net/test"
   ```
   Remplacez `<username>`, `<password>` et `<cluster-name>` par les informations spécifiques à votre cluster.

### 5. Afficher les bases de données dans Atlas
Une fois connecté à MongoDB Atlas via **mongosh**, vous pouvez afficher les bases de données existantes de la même manière que sur une instance locale :
```bash
show dbs
```
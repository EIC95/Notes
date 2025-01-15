# Création de Collections dans MongoDB

Dans MongoDB, une **collection** est une structure qui contient des documents. Contrairement aux bases de données relationnelles, les collections n'ont pas de schéma fixe, ce qui permet de stocker des documents avec des structures de données variées.

## Créer une Collection

### 1. Création automatique d'une collection
Les collections dans MongoDB sont créées automatiquement lorsque vous insérez un premier document dans la base de données. Par exemple, si vous insérez un document dans une collection qui n'existe pas encore, MongoDB créera la collection automatiquement :

```bash
db.ma_collection.insertOne({ "nom": "Alice", "age": 25 })
```

Cela crée la collection `ma_collection` et insère un document avec les champs `"nom"` et `"age"`.

### 2. Créer une collection manuellement
Vous pouvez également créer une collection explicitement à l'aide de la commande `createCollection`. Par exemple :

```bash
db.createCollection("ma_nouvelle_collection")
```

Cette commande crée une nouvelle collection vide appelée `ma_nouvelle_collection`.

### 3. Options de création de collection
Lors de la création d'une collection manuellement, vous pouvez spécifier des options, comme la définition de la taille maximale de la collection ou la gestion des index. Par exemple :

```bash
db.createCollection("ma_collection_avec_options", {
    capped: true,
    size: 1000000,
    max: 5000
})
```

- **capped** : Définit si la collection est de type "capped", c'est-à-dire avec une taille fixe et un comportement circulaire.
- **size** : La taille maximale de la collection en octets.
- **max** : Le nombre maximum de documents que la collection peut contenir.

### 4. Vérifier l'existence d'une collection
Pour vérifier si une collection existe déjà dans la base de données, vous pouvez utiliser la méthode suivante :

```bash
db.getCollectionNames()
```

Cela retourne une liste de toutes les collections présentes dans la base de données actuelle.

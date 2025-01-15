# Insertion de Documents dans une Collection MongoDB

Dans MongoDB, l'insertion de documents dans une collection est une opération courante. Les documents sont des objets au format BSON (Binary JSON) et peuvent contenir des données sous diverses formes, comme des chaînes de caractères, des nombres, des tableaux ou des objets imbriqués.

## Insertion d'un Document

### 1. Insérer un seul document
Pour insérer un seul document dans une collection, vous pouvez utiliser la méthode `insertOne()`. Par exemple :

```bash
db.ma_collection.insertOne({ "nom": "Alice", "age": 25 })
```

Cette commande insère un document avec les champs `"nom"` et `"age"` dans la collection `ma_collection`.

### 2. Insérer plusieurs documents
Si vous souhaitez insérer plusieurs documents à la fois, vous pouvez utiliser la méthode `insertMany()`. Par exemple :

```bash
db.ma_collection.insertMany([
    { "nom": "Bob", "age": 30 },
    { "nom": "Charlie", "age": 35 }
])
```

Cette commande insère deux documents dans la collection `ma_collection`.

### 3. Structure des documents
Les documents peuvent avoir des structures variées. Voici quelques exemples de documents insérés :

```bash
db.ma_collection.insertOne({
    "nom": "David",
    "age": 40,
    "adresse": { "rue": "123 Rue Principale", "ville": "Paris" },
    "interests": ["sport", "lecture"]
})
```

Les documents peuvent inclure des objets imbriqués (`"adresse"`) et des tableaux (`"interests"`).

## Validation des Données lors de l'Insertion

MongoDB ne nécessite pas un schéma fixe, mais il est possible de définir des **règles de validation** pour garantir que les documents insérés respectent un certain format. Par exemple, vous pouvez utiliser des règles de validation pour vérifier que les documents contiennent un champ spécifique.

### 1. Exemple de validation d'un champ
Vous pouvez définir une validation lors de la création d'une collection :

```bash
db.createCollection("ma_collection_avec_validation", {
    validator: {
        $jsonSchema: {
            bsonType: "object",
            required: ["nom", "age"],
            properties: {
                nom: { bsonType: "string" },
                age: { bsonType: "int" }
            }
        }
    }
})
```

Cette validation garantit que chaque document inséré dans la collection doit avoir les champs `"nom"` (de type chaîne de caractères) et `"age"` (de type entier).

## Résultats de l'Insertion

### 1. Confirmation d'insertion
Lorsque vous insérez un document, MongoDB renvoie un objet qui contient des informations sur l'opération. Par exemple, pour `insertOne()`, vous pouvez obtenir un objet comme celui-ci :

```bash
{
    "acknowledged" : true,
    "insertedId" : ObjectId("5f50c31b8a4f4c3b1fcbdd35")
}
```

- **acknowledged** : Indique si l'insertion a été confirmée par le serveur MongoDB.
- **insertedId** : L'ID unique généré pour le document inséré.

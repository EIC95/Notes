# Utilisation de la méthode `update()` dans MongoDB

La méthode `update()` est utilisée pour modifier un ou plusieurs documents dans une collection MongoDB. Elle permet de spécifier des critères de recherche pour identifier les documents à mettre à jour et de définir les nouvelles valeurs pour les champs spécifiés.

## Syntaxe de base de `update()`

La syntaxe de la méthode `update()` est la suivante :

```bash
db.ma_collection.update(<critères_de_recherche>, <modification>, <options>)
```

- **`<critères_de_recherche>`** : Ce paramètre définit les conditions pour trouver les documents à mettre à jour.
- **`<modification>`** : Ce paramètre définit les modifications à appliquer aux documents trouvés.
- **`<options>`** : Ce paramètre optionnel permet de spécifier des options comme l'option `upsert` ou `multi`.

## Exemple de mise à jour d'un document

### 1. Mettre à jour un seul document
La méthode `update()` permet de mettre à jour un seul document correspondant aux critères de recherche. Par exemple, pour mettre à jour l'âge d'un utilisateur nommé "Alice" dans la collection `ma_collection` :

```bash
db.ma_collection.update({ "nom": "Alice" }, { $set: { "age": 26 } })
```

Ici :
- `{ "nom": "Alice" }` est le critère de recherche pour trouver le document.
- `{ $set: { "age": 26 } }` est la modification à appliquer. L'opérateur `$set` définit le champ `"age"` à `26`.

### 2. Mettre à jour plusieurs documents
Par défaut, la méthode `update()` met à jour un seul document. Si vous souhaitez mettre à jour plusieurs documents correspondant aux critères de recherche, vous devez ajouter l'option `multi: true` :

```bash
db.ma_collection.update({ "age": { $lt: 30 } }, { $set: { "status": "Jeune" } }, { multi: true })
```

Cela met à jour tous les documents où l'âge est inférieur à 30, en ajoutant ou modifiant le champ `"status"` avec la valeur `"Jeune"`.

### 3. Utiliser l'option `upsert`
L'option `upsert` permet de créer un nouveau document si aucun document correspondant aux critères de recherche n'est trouvé. Par exemple :

```bash
db.ma_collection.update({ "nom": "David" }, { $set: { "age": 45 } }, { upsert: true })
```

Si aucun document avec `"nom": "David"` n'existe, MongoDB crée un nouveau document avec les champs `"nom": "David"` et `"age": 45`.

## Opérateurs de mise à jour

MongoDB prend en charge plusieurs opérateurs de mise à jour qui permettent de modifier les documents de manière plus avancée.

### 1. `$set`
L'opérateur `$set` permet de définir la valeur d'un champ spécifié. Si le champ n'existe pas, il est ajouté au document.

```bash
db.ma_collection.update({ "nom": "Alice" }, { $set: { "age": 26 } })
```

### 2. `$inc`
L'opérateur `$inc` permet d'incrémenter ou de décrémenter une valeur numérique. Par exemple, pour augmenter l'âge de "Alice" de 1 an :

```bash
db.ma_collection.update({ "nom": "Alice" }, { $inc: { "age": 1 } })
```

### 3. `$unset`
L'opérateur `$unset` permet de supprimer un champ d'un document. Par exemple, pour supprimer le champ `"adresse"` d'un document :

```bash
db.ma_collection.update({ "nom": "Alice" }, { $unset: { "adresse": "" } })
```

### 4. `$push` et `$addToSet`
L'opérateur `$push` permet d'ajouter un élément à un tableau, tandis que `$addToSet` ajoute un élément seulement s'il n'est pas déjà présent dans le tableau. Par exemple, pour ajouter un intérêt à la liste des intérêts de "Alice" :

```bash
db.ma_collection.update({ "nom": "Alice" }, { $push: { "interests": "cuisine" } })
```

### 5. `$pull`
L'opérateur `$pull` permet de retirer un élément d'un tableau. Par exemple, pour retirer un intérêt de la liste des intérêts de "Alice" :

```bash
db.ma_collection.update({ "nom": "Alice" }, { $pull: { "interests": "cuisine" } })
```

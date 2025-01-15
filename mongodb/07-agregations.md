# Agrégations dans MongoDB

Les agrégations dans MongoDB permettent d'effectuer des opérations complexes sur les données d'une collection. Elles permettent de filtrer, trier, grouper, transformer et calculer des résultats à partir de documents dans une collection.

## Introduction à l'agrégation

L'agrégation est réalisée avec la méthode **`aggregate()`**, qui prend un tableau de **pipes** (étapes d'agrégation) comme argument. Chaque étape dans le pipeline transforme les données de la collection de manière spécifique.

```bash
db.ma_collection.aggregate([<étapes_agrégation>])
```

Chaque **étape d'agrégation** est un document qui représente une opération à appliquer sur les documents de la collection.

## Étapes courantes d'agrégation

### 1. `$match`
L'étape `$match` filtre les documents en fonction de conditions spécifiées, similaire à une requête `find()`. Par exemple, pour sélectionner les documents où l'âge est supérieur à 30 :

```bash
db.ma_collection.aggregate([
  { $match: { "age": { $gt: 30 } } }
])
```

Cela ne retournera que les documents où l'âge est supérieur à 30.

### 2. `$group`
L'étape `$group` permet de regrouper les documents en fonction d'un ou plusieurs champs. Elle est souvent utilisée pour effectuer des calculs sur des groupes de documents, comme des moyennes ou des sommes. Par exemple, pour calculer la moyenne de l'âge des utilisateurs :

```bash
db.ma_collection.aggregate([
  { $group: { _id: null, moyenne_age: { $avg: "$age" } } }
])
```

Ici :
- **`_id: null`** signifie que tous les documents sont regroupés ensemble.
- **`$avg: "$age"`** calcule la moyenne du champ `"age"`.

### 3. `$sort`
L'étape `$sort` trie les documents selon les critères spécifiés. Par exemple, pour trier les documents par âge de manière décroissante :

```bash
db.ma_collection.aggregate([
  { $sort: { "age": -1 } }
])
```

- **`-1`** signifie un tri décroissant.
- **`1`** serait pour un tri croissant.

### 4. `$project`
L'étape `$project` permet de sélectionner les champs à inclure ou à exclure dans le résultat. Par exemple, pour ne retourner que le nom et l'âge des utilisateurs :

```bash
db.ma_collection.aggregate([
  { $project: { "nom": 1, "age": 1 } }
])
```

Cela retournera uniquement les champs `"nom"` et `"age"` de chaque document.

### 5. `$limit`
L'étape `$limit` permet de limiter le nombre de documents dans le résultat. Par exemple, pour obtenir seulement les 5 premiers documents :

```bash
db.ma_collection.aggregate([
  { $limit: 5 }
])
```

### 6. `$skip`
L'étape `$skip` permet de sauter un certain nombre de documents. Par exemple, pour ignorer les 5 premiers documents et retourner les suivants :

```bash
db.ma_collection.aggregate([
  { $skip: 5 }
])
```

### 7. `$unwind`
L'étape `$unwind` décompose un tableau dans un document en plusieurs documents, un pour chaque élément du tableau. Par exemple, si un utilisateur a plusieurs intérêts dans un tableau `"interests"`, vous pouvez les séparer en plusieurs documents :

```bash
db.ma_collection.aggregate([
  { $unwind: "$interests" }
])
```

Cela générera un document par intérêt, dupliquant les autres champs pour chaque valeur du tableau `"interests"`.

### 8. `$addFields`
L'étape `$addFields` permet d'ajouter de nouveaux champs à chaque document, ou de modifier les champs existants. Par exemple, pour ajouter un champ `"status"` basé sur l'âge de l'utilisateur :

```bash
db.ma_collection.aggregate([
  { $addFields: { "status": { $cond: { if: { $gt: ["$age", 30] }, then: "Mature", else: "Jeune" } } } }
])
```

Ici, l'opérateur `$cond` crée une condition qui attribue le statut "Mature" si l'âge est supérieur à 30, sinon "Jeune".

## Exemple complet de pipeline d'agrégation

Voici un exemple complet de pipeline d'agrégation combinant plusieurs étapes :

```bash
db.ma_collection.aggregate([
  { $match: { "age": { $gt: 20 } } },
  { $group: { _id: "$status", moyenne_age: { $avg: "$age" } } },
  { $sort: { "moyenne_age": -1 } },
  { $project: { "status": 1, "moyenne_age": 1 } }
])
```

Cet exemple effectue les étapes suivantes :
1. Filtre les utilisateurs de plus de 20 ans.
2. Regroupe les utilisateurs par statut et calcule la moyenne d'âge par groupe.
3. Trie les groupes par la moyenne d'âge de manière décroissante.
4. Projette les champs `"status"` et `"moyenne_age"` dans le résultat final.

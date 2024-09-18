# JSON (JavaScript Object Notation)

**JSON** (JavaScript Object Notation) est un format léger et textuel d'échange de données. Il est conçu pour être facilement lisible et modifiable par les humains, et simple à analyser et générer par les machines. JSON est souvent utilisé pour transmettre des données entre un client web et un serveur, notamment dans les API web, en raison de sa simplicité et de sa compatibilité avec de nombreux langages de programmation.

## Structure de JSON

La structure de JSON repose principalement sur deux éléments : les objets et les tableaux.

### Objets

- **Délimitation** : `{ }`
- **Contenu** : Paires clé-valeur
- **Exemple** :
  ```json
  {
    "nom": "John",
    "âge": 30,
    "ville": "New York"
  }
  ```

### Tableaux

- **Délimitation** : `[ ]`
- **Contenu** : Liste ordonnée de valeurs
- **Exemple** :
  ```json
  [
    "pomme",
    "banane",
    "cerise"
  ]
  ```

## Types de Données

- **Chaînes de caractères** : Entre guillemets doubles.
  - **Exemple** : `"exemple"`
- **Nombres** : Entiers ou à virgule flottante.
  - **Exemple** : `42`, `3.14`
- **Objets** : Paires clé-valeur imbriquées.
- **Tableaux** : Listes de valeurs ordonnées.
- **Booléens** : `true` ou `false`.
- **Valeur Null** : `null`.

## Utilisation en JavaScript

JSON est couramment utilisé pour manipuler les données récupérées des serveurs ou des API.

### Méthodes JavaScript

- **`JSON.parse()`** : Convertit une chaîne JSON en objet JavaScript.
  - **Exemple** :
    ```javascript
    let jsonString = '{"nom": "John", "âge": 30}';
    let obj = JSON.parse(jsonString);
    ```
- **`JSON.stringify()`** : Convertit un objet JavaScript en chaîne JSON.
  - **Exemple** :
    ```javascript
    let obj = { nom: "John", âge: 30 };
    let jsonString = JSON.stringify(obj);
    ```

## Utilisation en PHP

En PHP, les fonctions suivantes facilitent la manipulation des données JSON côté serveur.

### Fonctions PHP

- **`json_decode()`** : Convertit une chaîne JSON en tableau ou objet PHP.
  - **Exemple** :
    ```php
    $jsonString = '{"nom": "John", "âge": 30}';
    $obj = json_decode($jsonString);
    ```
- **`json_encode()`** : Convertit un tableau ou objet PHP en chaîne JSON.
  - **Exemple** :
    ```php
    $obj = array("nom" => "John", "âge" => 30);
    $jsonString = json_encode($obj);
    ```
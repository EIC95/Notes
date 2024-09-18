# Chaînes de caractères en JavaScript

Les chaînes peuvent être déclarées de différentes manières :

- **Guillemets simples (`'`)** : `'Bonjour'`
- **Guillemets doubles (`"`)** : `"Bonjour"`
- **Backticks (`` ` ``)** : `` `Bonjour, ${nom}` `` (permet d'inclure des variables et des expressions)

Les caractères spéciaux peuvent être inclus dans une chaîne avec le caractère d'échappement (`\`).

### Méthodes des chaînes

- **`.length`**
  - **Description** : Retourne la longueur de la chaîne.
  - **Exemple** :
    ```javascript
    let str = "Bonjour";
    console.log(str.length); // 7
    ```

- **`.charAt(index)`**
  - **Description** : Retourne le caractère à l'index spécifié.
  - **Exemple** :
    ```javascript
    let str = "Bonjour";
    console.log(str.charAt(1)); // 'o'
    ```

- **`.includes(substring)`**
  - **Description** : Vérifie si la chaîne contient la sous-chaîne spécifiée.
  - **Exemple** :
    ```javascript
    let str = "Bonjour";
    console.log(str.includes("jour")); // true
    ```

- **`.indexOf(substring)`**
  - **Description** : Retourne l'index de la première occurrence de la sous-chaîne, ou -1 si elle n'est pas trouvée.
  - **Exemple** :
    ```javascript
    let str = "Bonjour";
    console.log(str.indexOf("jour")); // 4
    ```

- **`.slice(start, end)`**
  - **Description** : Extrait une partie de la chaîne de `start` à `end` (non inclus).
  - **Exemple** :
    ```javascript
    let str = "Bonjour";
    console.log(str.slice(1, 4)); // 'onj'
    ```

- **`.substring(start, end)`**
  - **Description** : Extrait les caractères entre `start` et `end` (non inclus).
  - **Exemple** :
    ```javascript
    let str = "Bonjour";
    console.log(str.substring(1, 4)); // 'onj'
    ```

- **`.toUpperCase()`**
  - **Description** : Convertit la chaîne en majuscules.
  - **Exemple** :
    ```javascript
    let str = "Bonjour";
    console.log(str.toUpperCase()); // 'BONJOUR'
    ```

- **`.toLowerCase()`**
  - **Description** : Convertit la chaîne en minuscules.
  - **Exemple** :
    ```javascript
    let str = "Bonjour";
    console.log(str.toLowerCase()); // 'bonjour'
    ```

- **`.trim()`**
  - **Description** : Supprime les espaces blancs au début et à la fin de la chaîne.
  - **Exemple** :
    ```javascript
    let str = "  Bonjour  ";
    console.log(str.trim()); // 'Bonjour'
    ```

- **`.replace(oldValue, newValue)`**
  - **Description** : Remplace la première occurrence de `oldValue` par `newValue`.
  - **Exemple** :
    ```javascript
    let str = "Bonjour tout le monde";
    console.log(str.replace("monde", "amis")); // 'Bonjour tout les amis'
    ```

- **`.split(separator)`**
  - **Description** : Divise la chaîne en un tableau de sous-chaînes en utilisant le séparateur spécifié.
  - **Exemple** :
    ```javascript
    let str = "Bonjour,comment,ça va";
    console.log(str.split(",")); // ['Bonjour', 'comment', 'ça va']
    ```
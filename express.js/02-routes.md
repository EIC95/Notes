# Routes dans Express.js

## 1. Qu'est-ce qu'une Route ?
Une **route** dans Express.js est un point de terminaison où une application web peut répondre à une requête HTTP. Chaque route est associée à une **méthode HTTP** (comme `GET`, `POST`, `PUT`, `DELETE`, etc.) et à un **chemin** spécifique (URL). Les routes sont utilisées pour définir ce que le serveur doit faire lorsqu'il reçoit une requête à un certain chemin.

Les routes peuvent également être associées à des **handlers** (gestionnaires) qui définissent ce qui se passe lorsqu'une requête correspond à la route spécifiée.

## 2. Structure d'une Route
La structure d'une route Express se compose généralement de la manière suivante :

```js
app.[method]('[path]', [callback]);
```

- **[method]** : La méthode HTTP à utiliser pour cette route (`get`, `post`, `put`, `delete`, etc.).
- **[path]** : Le chemin de la route (par exemple, `/`, `/user/:id`).
- **[callback]** : Une fonction ou un tableau de fonctions qui traitent la requête et renvoient une réponse.

## 3. Exemple de Route

### Route `GET /` :
```js
app.get('/', (req, res) => {
  res.send('Bienvenue sur notre site !');
});
```
Dans cet exemple, lorsque l'utilisateur accède à la racine du site (par exemple, `http://localhost:3000/`), la réponse sera "Bienvenue sur notre site !".

### Route `GET /user/:id` :
```js
app.get('/user/:id', (req, res) => {
  const userId = req.params.id;  // Récupère l'ID de l'utilisateur dans l'URL
  res.send(`Utilisateur avec ID : ${userId}`);
});
```
Ici, la route prend un paramètre dynamique `:id` dans l'URL. Par exemple, `http://localhost:3000/user/123` affichera "Utilisateur avec ID : 123".

### Route `POST /login` :
```js
app.post('/login', (req, res) => {
  const username = req.body.username;
  const password = req.body.password;
  // Vérification des identifiants...
  res.send(`Connexion réussie pour ${username}`);
});
```
Cette route accepte des données envoyées dans le corps de la requête (`req.body`), comme un nom d'utilisateur et un mot de passe. Elle peut être utilisée pour implémenter une fonctionnalité de connexion.

## 4. Méthodes HTTP courantes pour les Routes

- **GET** : Récupère des informations.
- **POST** : Envoie des informations au serveur (souvent utilisé pour les formulaires).
- **PUT** : Met à jour des informations existantes.
- **DELETE** : Supprime des informations.

## 5. Routes avec Paramètres

Les routes peuvent contenir des **paramètres dynamiques** qui permettent de capturer des valeurs spécifiques dans l'URL.

### Exemple de Route avec Paramètres Dynamiques :
```js
app.get('/product/:productId', (req, res) => {
  const productId = req.params.productId;
  res.send(`Détails du produit avec l'ID : ${productId}`);
});
```
Dans cet exemple, l'ID du produit est capturé dans l'URL et peut être utilisé dans la fonction de callback pour afficher des détails spécifiques.

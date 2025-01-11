# Middleware dans Express.js

## 1. Qu'est-ce qu'un Middleware ?
Un **middleware** est une fonction qui s'exécute pendant le cycle de vie d'une requête HTTP, **avant** que la requête n'atteigne la route finale. Il peut être utilisé pour effectuer des actions comme la validation des données, la gestion de l'authentification, la gestion des erreurs, ou encore l'enregistrement des requêtes.

Les middlewares peuvent être définis de manière globale pour toutes les routes ou de manière spécifique pour certaines routes.

## 2. Structure d'un Middleware
Un middleware dans Express.js prend généralement trois arguments :

```js
(req, res, next) => { ... }
```

- **req** : L'objet représentant la requête HTTP.
- **res** : L'objet représentant la réponse HTTP.
- **next** : Une fonction qui, lorsqu'elle est appelée, permet de passer à la prochaine fonction middleware ou à la route suivante.

## 3. Exemple de Middleware de Journalisation (Logging)

Un middleware de journalisation permet de suivre les requêtes qui arrivent sur le serveur. Il peut être utilisé pour afficher des informations sur la requête dans la console.

### Code :
```js
const logRequest = (req, res, next) => {
  console.log(`${req.method} ${req.url}`);
  next();  // Passe à la route suivante
};

app.use(logRequest);
```

Ici, à chaque fois qu'une requête est reçue, la méthode HTTP et l'URL sont affichées dans la console.

## 4. Middleware de Vérification d'Authentification

Les middlewares sont souvent utilisés pour vérifier si un utilisateur est authentifié avant de lui permettre d'accéder à certaines routes. 

### Code d'exemple :
```js
const authenticate = (req, res, next) => {
  const token = req.headers['authorization'];
  if (token && token === 'Bearer mysecrettoken') {
    next();  // L'utilisateur est authentifié, on passe à la route suivante
  } else {
    res.status(403).send('Accès refusé');
  }
};

app.get('/admin', authenticate, (req, res) => {
  res.send('Accès administrateur');
});
```

Ici, le middleware `authenticate` vérifie si un token d'authentification est présent dans les en-têtes de la requête. Si le token est valide, l'utilisateur peut accéder à la route `/admin`, sinon l'accès est refusé.

## 5. Middleware Global vs Middleware de Route

### Middleware Global
Un middleware global est appliqué à toutes les routes de l'application.

```js
app.use(logRequest);  // S'applique à toutes les routes
```

### Middleware de Route
Un middleware de route est appliqué uniquement à des routes spécifiques.

```js
app.get('/admin', authenticate, (req, res) => {
  res.send('Accès administrateur');
});
```

## 6. Middleware Asynchrone

Les middlewares peuvent aussi être asynchrones. Si un middleware effectue une opération asynchrone, il peut utiliser `async/await` et `next()` pour gérer le passage à la prochaine fonction une fois l'opération terminée.

### Exemple :
```js
const asyncMiddleware = async (req, res, next) => {
  try {
    // Simuler une opération asynchrone (ex. récupération de données)
    await someAsyncOperation();
    next();  // Passe à la route suivante
  } catch (error) {
    res.status(500).send('Erreur interne');
  }
};

app.use(asyncMiddleware);
```
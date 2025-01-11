# Sécurisation d'une application Express

## Authentification avec JWT (JSON Web Token)

### Génération d'un token JWT

L'authentification avec JWT consiste à générer un token signé contenant des informations sur l'utilisateur. Ce token est ensuite utilisé pour valider l'identité de l'utilisateur dans les requêtes suivantes.

#### Code pour générer un token JWT :
```js
const jwt = require('jsonwebtoken');

// Fonction pour générer un token JWT
function generateToken(user) {
  return jwt.sign(
    { id: user.id, username: user.username },  // Informations de l'utilisateur
    'secret_key',  // Secret pour signer le token
    { expiresIn: '1h' }  // Expiration du token dans 1 heure
  );
}
```

**Explication :**
- `jwt.sign` est utilisé pour générer un token signé.
- Le `user` contient les informations que nous voulons stocker dans le token, comme l'ID et le nom d'utilisateur.
- `'secret_key'` est une clé secrète utilisée pour signer le token, garantissant qu'il n'a pas été modifié.
- `{ expiresIn: '1h' }` définit une expiration de 1 heure pour le token.

---

### Middleware d'authentification

Ce middleware vérifie si le token JWT est présent dans les en-têtes de la requête et s'il est valide. Si le token est valide, il permet à l'utilisateur de continuer à accéder à la route.

#### Code pour créer un middleware d'authentification : 
```js
function authenticate(req, res, next) {
  const token = req.header('Authorization')?.replace('Bearer ', '');
  if (!token) {
    return res.status(401).send('Accès refusé. Aucun token fourni.');
  }

  try {
    const decoded = jwt.verify(token, 'secret_key');
    req.user = decoded;  // Ajouter les informations de l'utilisateur à la requête
    next();  // Passer à la route suivante
  } catch (err) {
    res.status(400).send('Token invalide.');
  }
}
```

**Explication :**
- `req.header('Authorization')` récupère l'en-tête d'autorisation dans la requête.
- `.replace('Bearer ', '')` supprime le préfixe `Bearer` du token.
- `jwt.verify` vérifie la validité du token en le comparant à la clé secrète.
- Si le token est valide, les informations de l'utilisateur (`decoded`) sont ajoutées à la requête avec `req.user`.

---

### Route protégée avec JWT

La route `/profile` est protégée par le middleware `authenticate`. Si l'utilisateur a un token valide, il peut accéder à cette route et voir ses informations.

#### Code pour une route protégée :
```js
app.get('/profile', authenticate, (req, res) => {
  res.send(`Bienvenue, ${req.user.username}`);
});
```

**Explication :**
- Le middleware `authenticate` est utilisé avant d'exécuter la logique de la route.
- Si le token est valide, `req.user.username` est accessible et renvoyé dans la réponse.

---

## Autorisation : Contrôler l'accès en fonction des rôles

L'autorisation vérifie que l'utilisateur a les droits nécessaires pour accéder à une ressource particulière, par exemple, en fonction de son rôle.

### Middleware d'autorisation

Ce middleware vérifie si l'utilisateur a le rôle approprié pour accéder à la route.

#### Code pour un middleware d'autorisation :
```js
function authorize(role) {
  return (req, res, next) => {
    if (req.user.role !== role) {
      return res.status(403).send('Accès interdit.');
    }
    next();  // Si l'utilisateur a le bon rôle, on passe à la route suivante
  };
}
```

**Explication :**
- `authorize(role)` est une fonction qui prend un rôle en paramètre (par exemple, `'admin'`).
- Le middleware vérifie si le rôle de l'utilisateur (`req.user.role`) correspond à celui requis.
- Si le rôle ne correspond pas, une erreur 403 est renvoyée, sinon la requête passe à la route suivante.

---

### Route protégée par rôle

Dans cet exemple, la route `/admin` est protégée et accessible uniquement aux utilisateurs ayant le rôle `'admin'`.

#### Code pour une route protégée par rôle :
```js
app.get('/admin', authenticate, authorize('admin'), (req, res) => {
  res.send('Accès administrateur');
});
```

**Explication :**
- La route `/admin` utilise d'abord le middleware `authenticate` pour vérifier l'authentification.
- Ensuite, le middleware `authorize('admin')` s'assure que l'utilisateur a le rôle `'admin'`.
- Si les deux vérifications réussissent, l'utilisateur accède à la route et voit le message `'Accès administrateur'`.

---

## Sécurisation des routes avec des middlewares

Les middlewares peuvent être utilisés pour effectuer des vérifications supplémentaires avant d'atteindre les routes.

### Middleware de vérification de compte

Ce middleware vérifie que l'utilisateur a bien vérifié son compte avant d'accéder à certaines routes.

#### Code pour un middleware de vérification de compte :
```js
function secureRoute(req, res, next) {
  if (req.user && req.user.isVerified) {
    next();  // L'utilisateur est vérifié, on passe à la route suivante
  } else {
    res.status(403).send('Accès interdit. Vous devez vérifier votre compte.');
  }
}
```

**Explication :**
- Le middleware `secureRoute` vérifie si l'utilisateur est authentifié (`req.user`) et si son compte est vérifié (`req.user.isVerified`).
- Si l'utilisateur est vérifié, il peut accéder à la route suivante, sinon une erreur 403 est renvoyée.

---

### Route sécurisée

La route `/secure-data` est protégée par les middlewares `authenticate` et `secureRoute`.

#### Code pour une route sécurisée :
```js
app.get('/secure-data', authenticate, secureRoute, (req, res) => {
  res.send('Données sécurisées');
});
```

**Explication :**
- La route `/secure-data` est protégée par les middlewares `authenticate` et `secureRoute`.
- L'utilisateur doit être authentifié et avoir vérifié son compte pour accéder aux données sécurisées.

---

## Mesures de sécurité supplémentaires

Il existe plusieurs autres pratiques pour sécuriser une application Express, comme la protection contre les attaques CSRF et XSS, la limitation des tentatives de connexion, et l'utilisation de HTTPS.

### Protection contre les attaques CSRF (Cross-Site Request Forgery)

Les attaques CSRF exploitent la confiance d'un site envers le navigateur de l'utilisateur. Pour protéger l'application, on utilise des tokens CSRF.

#### Code pour activer la protection CSRF :
```js
const csrf = require('csurf');
const csrfProtection = csrf({ cookie: true });

app.use(csrfProtection);
```

**Explication :**
- `csrfProtection` génère et vérifie des tokens CSRF pour chaque requête afin de protéger l'application contre ce type d'attaque.

---

### Protection contre les attaques XSS (Cross-Site Scripting)

Les attaques XSS permettent d'injecter des scripts malveillants dans une page web. Pour éviter cela, il est important de toujours échapper les données utilisateur.

#### Code pour ajouter des en-têtes de sécurité XSS :
```js
const helmet = require('helmet');
app.use(helmet());
```

**Explication :**
- `helmet` ajoute des en-têtes HTTP qui protègent l'application contre diverses attaques, y compris les attaques XSS et le clickjacking.

---

### Limitation des tentatives de connexion avec `express-rate-limit`

La limitation des tentatives de connexion permet de se protéger contre les attaques par force brute.

#### Code pour limiter les tentatives de connexion :
```js
const rateLimit = require('express-rate-limit');

const loginLimiter = rateLimit({
  windowMs: 15 * 60 * 1000,  // 15 minutes
  max: 5,  // Limiter à 5 tentatives par adresse IP
  message: 'Trop de tentatives de connexion. Essayez plus tard.'
});

app.post('/login', loginLimiter, (req, res) => {
  // Traitement de la connexion
});
```

**Explication :**
- `express-rate-limit` permet de limiter le nombre de requêtes à une route spécifique.
- Ici, on limite les tentatives de connexion à 5 par adresse IP toutes les 15 minutes.

---

### Utilisation de HTTPS

L'utilisation de HTTPS permet de sécuriser les échanges de données entre le client et le serveur.

#### Code pour configurer HTTPS :
```js
const https = require('https');
const fs = require('fs');

const options = {
  key: fs.readFileSync('path/to/your/private-key.pem'),
  cert: fs.readFileSync('path/to/your/certificate.pem')
};

https.createServer(options, app).listen(3000, () => {
  console.log('Serveur HTTPS démarré sur https://localhost:3000');
});
```

**Explication :**
- Le serveur HTTPS est créé avec les certificats SSL (clé privée et certificat) pour chiffrer les communications.

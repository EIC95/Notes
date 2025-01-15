# **Gestion des Sessions et des Cookies**

Les sessions et les cookies permettent de maintenir l'état de l'utilisateur entre les requêtes. Après que l'utilisateur se soit authentifié, vous devez stocker une information qui lui permettra de rester connecté pendant ses interactions avec votre application. Voici comment procéder.

## **1. Installation des Dépendances**

Pour gérer les sessions et les cookies, nous allons utiliser les modules suivants :
- `express-session` pour gérer les sessions.
- `cookie-parser` pour analyser les cookies dans les requêtes.

Installez ces modules via npm :

```bash
npm install express-session cookie-parser
```

## **2. Configuration de `express-session`**

`express-session` vous permet de créer des sessions pour chaque utilisateur et de les lier à un identifiant de session unique. Cet identifiant est stocké dans un cookie sur le client.

Voici un exemple de configuration basique :

```javascript
const express = require('express');
const session = require('express-session');
const cookieParser = require('cookie-parser');

const app = express();

// Utilisation de cookie-parser pour analyser les cookies
app.use(cookieParser());

// Configuration des sessions
app.use(session({
  secret: 'votre_clé_secrète',  // Clé secrète pour signer le cookie de session
  resave: false,  // Ne pas resauvegarder la session si elle n'a pas été modifiée
  saveUninitialized: false,  // Ne pas sauvegarder les sessions non initialisées
  cookie: { secure: false }  // Utilisez `true` pour forcer HTTPS
}));

// Middleware pour vérifier si l'utilisateur est authentifié
function isAuthenticated(req, res, next) {
  if (req.session.user) {
    return next();  // L'utilisateur est authentifié, continuez avec la requête
  } else {
    res.status(401).send('Non authentifié');
  }
}

// Route de connexion
app.post('/login', (req, res) => {
  // Supposons que l'utilisateur a été authentifié avec succès
  req.session.user = { id: 1, username: 'utilisateurExemple' };
  res.send('Utilisateur connecté');
});

// Route protégée nécessitant une authentification
app.get('/protected', isAuthenticated, (req, res) => {
  res.send(`Bienvenue, ${req.session.user.username}`);
});

// Route de déconnexion
app.get('/logout', (req, res) => {
  req.session.destroy((err) => {
    if (err) {
      return res.status(500).send('Erreur lors de la déconnexion');
    }
    res.send('Utilisateur déconnecté');
  });
});

app.listen(3000, () => {
  console.log('Serveur démarré sur http://localhost:3000');
});
```

### Explication des éléments :
- **`secret`** : Une clé secrète utilisée pour signer le cookie de session. Elle permet de sécuriser les données de session.
- **`resave`** : Si cette option est définie sur `false`, la session n'est pas enregistrée si elle n'a pas été modifiée.
- **`saveUninitialized`** : Si définie sur `false`, la session ne sera pas enregistrée si elle n'est pas modifiée.
- **`cookie`** : Vous pouvez configurer des options pour le cookie de session, comme `secure: true` pour utiliser HTTPS.

---

## **3. Gestion des Cookies**

Les cookies permettent de stocker des informations sur le côté client, comme l'identifiant de session. Express utilise des cookies pour stocker l'identifiant de session. Lorsque l'utilisateur se connecte, un cookie est créé et envoyé au client, et lors des requêtes suivantes, ce cookie est envoyé avec chaque demande.

Voici comment configurer des cookies avec `cookie-parser` et `express-session` :

```javascript
// Exemple de cookie personnalisé
app.get('/set-cookie', (req, res) => {
  res.cookie('user', 'utilisateurExemple', { maxAge: 900000, httpOnly: true });
  res.send('Cookie défini');
});

// Exemple de lecture d'un cookie
app.get('/get-cookie', (req, res) => {
  const userCookie = req.cookies.user;
  res.send(`Cookie utilisateur: ${userCookie}`);
});
```

### Explication des éléments :
- **`maxAge`** : La durée de vie du cookie en millisecondes.
- **`httpOnly`** : Cela empêche l'accès au cookie via JavaScript côté client, ce qui améliore la sécurité.
- **`secure`** : Lorsque vous déployez en production avec HTTPS, vous pouvez définir `secure: true` pour vous assurer que le cookie n'est envoyé que via HTTPS.

---

## **4. Expiration de Session et Déconnexion**

Les sessions ont une durée de vie, et vous pouvez définir cette durée via l'option `cookie.maxAge` dans la configuration de `express-session`. Une fois cette durée expirée, la session sera automatiquement supprimée.

Voici un exemple de gestion de l'expiration de la session :

```javascript
app.use(session({
  secret: 'votre_clé_secrète',
  resave: false,
  saveUninitialized: false,
  cookie: { maxAge: 60000 }  // La session expire après 1 minute
}));
```

Lorsque l'utilisateur se déconnecte, vous pouvez supprimer la session à l'aide de `req.session.destroy()`.

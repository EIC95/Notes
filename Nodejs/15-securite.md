# **Sécurisation du Stockage des Mots de Passe**

Il est essentiel de ne jamais stocker un mot de passe en clair dans la base de données. Pour assurer la sécurité des mots de passe, vous devez utiliser un mécanisme de hachage sécurisé. Voici les étapes pour sécuriser les mots de passe avec **bcrypt** :

## **1. Installation de bcrypt**

Tout d'abord, vous devez installer la bibliothèque `bcrypt` qui permet de hacher les mots de passe de manière sécurisée.

```bash
npm install bcrypt
```

## **2. Hachage du Mot de Passe**

Lorsque l'utilisateur crée un compte ou modifie son mot de passe, vous devez hacher le mot de passe avant de le stocker dans la base de données. Le processus de hachage doit inclure l'ajout d'un "sel" (salt), un élément aléatoire qui garantit que même les mots de passe identiques seront hachés de manière différente.

Voici comment vous pouvez hacher un mot de passe avec `bcrypt` :

```javascript
const bcrypt = require('bcrypt');

// Hachage du mot de passe
const password = 'monMotDePasse';
const saltRounds = 10;  // Nombre de rounds pour le sel
const hashedPassword = await bcrypt.hash(password, saltRounds);

console.log(hashedPassword);  // Le mot de passe haché sera stocké dans la base de données
```

## **3. Vérification du Mot de Passe**

Lorsque l'utilisateur se connecte, vous devez comparer le mot de passe qu'il fournit avec le mot de passe haché stocké dans la base de données. Cela se fait à l'aide de la fonction `bcrypt.compare()`.

Voici comment vérifier si le mot de passe fourni correspond à celui stocké :

```javascript
const isMatch = await bcrypt.compare(providedPassword, storedHashedPassword);

if (isMatch) {
  console.log('Mot de passe correct');
} else {
  console.log('Mot de passe incorrect');
}
```

Cela vous permet de valider l'authentification de l'utilisateur sans jamais exposer son mot de passe réel.

## **4. Sécurisation du Mot de Passe dans la Base de Données**

Une fois que le mot de passe est haché, vous pouvez le stocker dans la base de données. Assurez-vous de ne jamais stocker le mot de passe en clair. Par exemple, avec MongoDB, vous pouvez enregistrer le mot de passe haché dans un champ `password` :

```javascript
const user = {
  username: 'exempleUtilisateur',
  password: hashedPassword  // Stockage du mot de passe haché
};
```

---

# **Sécurisation avec HTTPS**

Il est essentiel d'utiliser HTTPS pour chiffrer les données transmises entre le client et le serveur, y compris les mots de passe, pour éviter les attaques de type "man-in-the-middle".

1. **Obtenez un certificat SSL** pour sécuriser votre site.
2. **Forcer l'utilisation de HTTPS** dans votre application.

Voici un exemple de configuration avec Express.js pour forcer l'utilisation de HTTPS :

```javascript
if (process.env.NODE_ENV === 'production') {
  app.use((req, res, next) => {
    if (req.headers['x-forwarded-proto'] !== 'https') {
      return res.redirect('https://' + req.headers.host + req.url);
    }
    next();
  });
}
```

Cela redirige automatiquement les requêtes HTTP vers HTTPS.
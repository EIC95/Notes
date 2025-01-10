# Axios

## Introduction

**Axios** est une bibliothèque JavaScript populaire utilisée pour faire des requêtes HTTP (GET, POST, PUT, DELETE, etc.). Elle est basée sur des promesses, ce qui la rend très compatible avec les techniques modernes comme **`async` / `await`**. Axios peut être utilisé dans les applications front-end (navigateur) ou back-end (Node.js).

---

## Installation

Pour utiliser Axios, vous devez d'abord l'installer. Si vous utilisez Node.js, vous pouvez installer Axios via **npm**.

### Commande d'installation :

```bash
npm install axios
```

Dans le navigateur, vous pouvez inclure Axios via un CDN.

```html
<script src="https://cdn.jsdelivr.net/npm/axios/dist/axios.min.js"></script>
```

---

## Faire une requête GET avec Axios

Axios est principalement utilisé pour envoyer des requêtes HTTP. Voici un exemple de requête **GET** pour récupérer des données d'une API.

### Exemple de requête GET :

```javascript
const axios = require('axios');

axios.get('https://jsonplaceholder.typicode.com/posts')
  .then(response => {
    console.log(response.data);  // Affiche les données reçues
  })
  .catch(error => {
    console.log('Erreur:', error);
  });
```

Dans cet exemple, nous récupérons des données depuis l'API **jsonplaceholder** et les affichons dans la console. Si une erreur survient, elle sera capturée et affichée.

---

## Faire une requête POST avec Axios

Vous pouvez aussi envoyer des données au serveur en utilisant une requête **POST**. Voici comment envoyer des données avec Axios.

### Exemple de requête POST :

```javascript
const axios = require('axios');

const data = {
  title: 'Titre de l\'article',
  body: 'Contenu de l\'article',
  userId: 1
};

axios.post('https://jsonplaceholder.typicode.com/posts', data)
  .then(response => {
    console.log(response.data);  // Affiche la réponse du serveur
  })
  .catch(error => {
    console.log('Erreur:', error);
  });
```

Ici, nous envoyons un objet **`data`** contenant un titre, un corps et un identifiant utilisateur à l'API.

---

## Utilisation avec `async` / `await`

Axios fonctionne parfaitement avec **`async`** et **`await`**, ce qui permet d'écrire du code plus propre et plus lisible.

### Exemple avec `async` / `await` :

```javascript
const axios = require('axios');

async function getData() {
  try {
    const response = await axios.get('https://jsonplaceholder.typicode.com/posts');
    console.log(response.data);  // Affiche les données reçues
  } catch (error) {
    console.log('Erreur:', error);
  }
}

getData();
```

Dans cet exemple, la requête **GET** est effectuée de manière asynchrone, et les données sont affichées une fois la requête terminée.

---

## Gestion des erreurs avec Axios

Lorsque vous utilisez Axios, vous pouvez facilement gérer les erreurs via le **`.catch()`** ou avec **`try/catch`** dans le cas de **`async` / `await`**.

### Exemple de gestion des erreurs avec `.catch()` :

```javascript
axios.get('https://jsonplaceholder.typicode.com/posts')
  .then(response => {
    console.log(response.data);
  })
  .catch(error => {
    if (error.response) {
      // La requête a été faite et le serveur a répondu avec un code d'état
      console.log('Erreur de réponse:', error.response.data);
    } else if (error.request) {
      // La requête a été faite mais aucune réponse n'a été reçue
      console.log('Aucune réponse reçue:', error.request);
    } else {
      // Une erreur est survenue lors de la configuration de la requête
      console.log('Erreur lors de la configuration:', error.message);
    }
  });
```

---

## Annuler une requête avec Axios

Axios permet également d'annuler une requête en cours en utilisant un **cancel token**.

### Exemple d'annulation de requête :

```javascript
const axios = require('axios');
const CancelToken = axios.CancelToken;
let cancel;

axios.get('https://jsonplaceholder.typicode.com/posts', {
  cancelToken: new CancelToken(function executor(c) {
    cancel = c;
  })
}).then(response => {
  console.log(response.data);
}).catch(error => {
  if (axios.isCancel(error)) {
    console.log('Requête annulée', error.message);
  } else {
    console.log('Erreur:', error);
  }
});

// Annuler la requête après 2 secondes
setTimeout(() => {
  cancel('Requête annulée après 2 secondes');
}, 2000);
```

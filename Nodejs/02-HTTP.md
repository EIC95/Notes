# Module HTTP 

Node.js inclut un module intégré appelé **HTTP**, qui permet de transférer des données via le protocole HTTP (Hyper Text Transfer Protocol). Ce module est essentiel pour créer des serveurs Web et gérer des requêtes et des réponses HTTP.

---

## Inclure le module HTTP

Pour inclure le module HTTP, utilisez la méthode `require()` :  

```javascript
let http = require('http');
```

---

## Node.js comme serveur Web

Le module HTTP peut créer un serveur HTTP capable d'écouter des ports et de répondre aux clients.  

### Créer un serveur HTTP

Utilisez la méthode `createServer()` pour créer un serveur HTTP :  

```javascript
let http = require('http');

// Créer un serveur :
http.createServer(function (req, res) {
  res.write('Hello World!'); // Écrire une réponse pour le client
  res.end(); // Terminer la réponse
}).listen(8080); // Le serveur écoute sur le port 8080
```

- La fonction passée en argument à `http.createServer()` est exécutée lorsqu'un client accède au serveur via le port spécifié (ici, **8080**).  
- Sauvegardez ce code dans un fichier nommé **`demo_http.js`**.  

---

## Ajouter un en-tête HTTP

Si vous souhaitez afficher une réponse au format HTML, il est nécessaire d'ajouter un en-tête HTTP avec le type de contenu approprié.  

### Exemple avec un en-tête HTTP

```javascript
let http = require('http');

http.createServer(function (req, res) {
  res.writeHead(200, {'Content-Type': 'text/html'}); // Ajouter un en-tête HTTP
  res.write('Hello World!'); // Écrire une réponse pour le client
  res.end(); // Terminer la réponse
}).listen(8080);
```

- Le **premier argument** de la méthode `res.writeHead()` est le **code de statut** (200 signifie "OK").  
- Le **deuxième argument** est un objet contenant les **en-têtes de la réponse**.  

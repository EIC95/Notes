# Node.js URL Module

Le module intégré **URL** permet de découper une adresse web en parties lisibles.

---

## Inclure le module URL

Pour inclure le module URL, utilisez la méthode `require()` :  
```javascript
let url = require('url');
```

---

## **Analyser une adresse avec `url.parse()`**

La méthode `url.parse()` retourne un objet URL avec chaque partie de l'adresse comme propriété.

### Exemple : Découper une adresse web
```javascript
let url = require('url');
let adr = 'http://localhost:8080/default.htm?year=2017&month=february';
let q = url.parse(adr, true);

console.log(q.host);       // retourne 'localhost:8080'
console.log(q.pathname);   // retourne '/default.htm'
console.log(q.search);     // retourne '?year=2017&month=february'

let qdata = q.query;       // retourne un objet : { year: 2017, month: 'february' }
console.log(qdata.month);  // retourne 'february'
```

---

## **Serveur de fichiers avec Node.js**

En combinant le module **URL** et le serveur de fichiers, nous pouvons servir les fichiers demandés par le client.

### exemple :
1. Créez deux fichiers HTML dans le même dossier que vos fichiers Node.js :
   - **summer.html**  
     ```html
     <!DOCTYPE html>
     <html>
     <body>
     <h1>Summer</h1>
     <p>I love the sun!</p>
     </body>
     </html>
     ```

   - **winter.html**  
     ```html
     <!DOCTYPE html>
     <html>
     <body>
     <h1>Winter</h1>
     <p>I love the snow!</p>
     </body>
     </html>
     ```

2. Créez un fichier Node.js pour ouvrir les fichiers demandés.

```javascript
let http = require('http');
let url = require('url');
let fs = require('fs');

http.createServer(function (req, res) {
  let q = url.parse(req.url, true);
  let filename = "." + q.pathname;

  fs.readFile(filename, function (err, data) {
    if (err) {
      res.writeHead(404, { 'Content-Type': 'text/html' });
      return res.end("404 Not Found");
    }
    res.writeHead(200, { 'Content-Type': 'text/html' });
    res.write(data);
    return res.end();
  });
}).listen(8080);
```

- [http://localhost:8080/summer.html](http://localhost:8080/summer.html)  
  **Résultat attendu** :  
  ```
  Summer
  I love the sun!
  ```

- [http://localhost:8080/winter.html](http://localhost:8080/winter.html)  
  **Résultat attendu** :  
  ```
  Winter
  I love the snow!
  ```

# Modules dans Node.js

Les **modules** en Node.js sont similaires aux bibliothèques en JavaScript : ce sont des ensembles de fonctions que vous pouvez inclure dans vos applications pour réutiliser du code.

---

## Modules intégrés

Node.js propose un ensemble de modules intégrés que vous pouvez utiliser sans installation supplémentaire. Ces modules offrent diverses fonctionnalités comme le système de fichiers, le réseau, ou encore la gestion des flux.  

### Exemple d'utilisation d'un module intégré

Pour inclure un module, utilisez la fonction `require()` avec le nom du module :  

```javascript
let http = require('http');
```

Ensuite, vous pouvez utiliser ce module dans votre application. Par exemple, pour créer un serveur HTTP :  

```javascript
let http = require('http');

http.createServer(function (req, res) {
  res.writeHead(200, {'Content-Type': 'text/html'});
  res.end('Hello World!');
}).listen(8080);
```

---

## Créer vos propres modules

Vous pouvez également créer vos propres modules pour organiser et réutiliser votre code.

### Exemple de création d'un module

Créez un module qui retourne la date et l'heure actuelles :  

```javascript
exports.myDateTime = function () {
  return Date();
};
```

- Utilisez le mot-clé `exports` pour rendre des propriétés et méthodes accessibles à l'extérieur du fichier module.  
- Sauvegardez ce code dans un fichier nommé **`myfirstmodule.js`**.

### Inclure votre propre module

Pour utiliser le module que vous venez de créer, incluez-le dans un autre fichier Node.js :  

```javascript
let http = require('http');
let dt = require('./myfirstmodule');

http.createServer(function (req, res) {
  res.writeHead(200, {'Content-Type': 'text/html'});
  res.write("The date and time are currently: " + dt.myDateTime());
  res.end();
}).listen(8080);
```

- Remarquez l'utilisation de `./` pour indiquer que le module est situé dans le même dossier que le fichier Node.js.  
- Sauvegardez ce code dans un fichier nommé **`demo_module.js`**.  

---

## Exécuter les fichiers Node.js

Pour exécuter votre fichier Node.js :  

```bash
node demo_module.js
```

Ouvrez votre navigateur à l'adresse suivante : **`http://localhost:8080`**. Vous devriez voir la date et l'heure actuelles affichées.  


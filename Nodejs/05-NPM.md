# Node.js NPM

## Qu'est-ce que NPM ?

NPM est un gestionnaire de packages pour les modules Node.js.  

- Le site [www.npmjs.com](https://www.npmjs.com) héberge des milliers de packages gratuits.  
- NPM est installé automatiquement avec Node.js et est prêt à l'emploi.  

---

## Qu'est-ce qu'un Package ?

Un **package** dans Node.js contient tous les fichiers nécessaires pour un module.  

Les **modules** sont des bibliothèques JavaScript que vous pouvez inclure dans vos projets.

---

## Télécharger un Package

Le téléchargement d'un package avec NPM est simple.  

### Exemple : Télécharger le package **upper-case**
1. Ouvrez l'interface de ligne de commande.
2. Tapez la commande suivante :
   ```bash
   npm install upper-case
   ```
3. NPM crée un dossier `node_modules` où les packages téléchargés sont stockés.

Structure du projet après installation :  
```
C:\Users\My Name\node_modules\upper-case
```

---

## Utiliser un Package

Une fois le package installé, vous pouvez l'utiliser dans votre projet comme suit :

### Exemple : Convertir un texte en majuscules
1. Incluez le module avec `require` :
   ```javascript
   let uc = require('upper-case');
   ```
2. Créez un serveur Node.js qui renvoie un texte en majuscules :  
   ```javascript
   let http = require('http');
   let uc = require('upper-case');

   http.createServer(function (req, res) {
       res.writeHead(200, {'Content-Type': 'text/html'});
       res.write(uc.upperCase("Hello World!"));
       res.end();
   }).listen(8080);
   ```
3. Enregistrez ce code dans un fichier appelé **demo_uppercase.js**.
4. Exécutez le fichier avec la commande :  
   ```bash
   node demo_uppercase.js
   ```

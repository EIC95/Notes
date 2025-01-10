# Node.js Téléchargement de Fichiers

## Le module Formidable

Formidable est un module pour gérer les téléchargements de fichiers dans Node.js.  
Tu peux l'installer avec NPM :

```bash
C:\Users\Ton Nom>npm install formidable
```

Une fois installé, tu peux l'inclure dans ton application :

```javascript
let formidable = require('formidable');
```

---

## Téléchargement de Fichiers

### Étape 1 : Créer un formulaire de téléchargement

Commence par créer un formulaire HTML simple qui permet à l'utilisateur de télécharger un fichier.

Voici un code Node.js qui génère ce formulaire :

```javascript
let http = require('http');

http.createServer(function (req, res) {
  res.writeHead(200, {'Content-Type': 'text/html'});
  res.write('<form action="fileupload" method="post" enctype="multipart/form-data">');
  res.write('<input type="file" name="filetoupload"><br>');
  res.write('<input type="submit">');
  res.write('</form>');
  return res.end();
}).listen(8080);
```

---

### Étape 2 : Analyser le fichier téléchargé

Une fois le fichier téléchargé, il faut l'analyser. Le module Formidable s'en charge et place le fichier dans un dossier temporaire sur ton ordinateur.

```javascript
let http = require('http');
let formidable = require('formidable');

http.createServer(function (req, res) {
  if (req.url == '/fileupload') {
    let form = new formidable.IncomingForm();
    form.parse(req, function (err, fields, files) {
      res.write('Fichier téléchargé');
      res.end();
    });
  } else {
    res.writeHead(200, {'Content-Type': 'text/html'});
    res.write('<form action="fileupload" method="post" enctype="multipart/form-data">');
    res.write('<input type="file" name="filetoupload"><br>');
    res.write('<input type="submit">');
    res.write('</form>');
    return res.end();
  }
}).listen(8080);
```

---

### Étape 3 : Sauvegarder le fichier

Le fichier téléchargé est temporairement stocké sur ton ordinateur. Pour le déplacer vers un autre dossier, tu peux utiliser le module **fs** (File System) pour le renommer et le déplacer.

Voici comment faire :

```javascript
let http = require('http');
let formidable = require('formidable');
let fs = require('fs');

http.createServer(function (req, res) {
  if (req.url == '/fileupload') {
    let form = new formidable.IncomingForm();
    form.parse(req, function (err, fields, files) {
      let oldpath = files.filetoupload.filepath;
      let newpath = 'C:/Users/Ton Nom/' + files.filetoupload.originalFilename;
      fs.rename(oldpath, newpath, function (err) {
        if (err) throw err;
        res.write('Fichier téléchargé et déplacé !');
        res.end();
      });
    });
  } else {
    res.writeHead(200, {'Content-Type': 'text/html'});
    res.write('<form action="fileupload" method="post" enctype="multipart/form-data">');
    res.write('<input type="file" name="filetoupload"><br>');
    res.write('<input type="submit">');
    res.write('</form>');
    return res.end();
  }
}).listen(8080);
```

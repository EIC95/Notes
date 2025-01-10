# Module File System de Node.js

Le module **File System (fs)** de Node.js permet de travailler avec le système de fichiers de votre ordinateur. Il offre des méthodes pour lire, créer, mettre à jour, supprimer et renommer des fichiers.

---

## **Inclure le module File System**
Pour inclure le module File System, utilisez la méthode `require()` :  
```javascript
let fs = require('fs');
```

---

## **Lecture de fichiers**

La méthode `fs.readFile()` permet de lire le contenu d'un fichier.

Exemple : Lire un fichier HTML et retourner son contenu via un serveur HTTP.

```javascript
let http = require('http');
let fs = require('fs');

http.createServer(function (req, res) {
  fs.readFile('demofile1.html', function (err, data) {
    if (err) throw err;
    res.writeHead(200, { 'Content-Type': 'text/html' });
    res.write(data);
    res.end();
  });
}).listen(8080);
```
- Le fichier **`demofile1.html`** est lu, et son contenu est envoyé comme réponse HTTP.
- Accédez au serveur à l'adresse [http://localhost:8080](http://localhost:8080).

---

## **Création de fichiers**

### 1. **`fs.appendFile()`**
Ajoute du contenu à un fichier existant ou crée un nouveau fichier s'il n'existe pas.  
```javascript
fs.appendFile('mynewfile1.txt', 'Hello content!', function (err) {
  if (err) throw err;
  console.log('Saved!');
});
```

### 2. **`fs.open()`**
Crée un fichier vide ou l'ouvre en mode écriture.  
```javascript
fs.open('mynewfile2.txt', 'w', function (err, file) {
  if (err) throw err;
  console.log('Saved!');
});
```

### 3. **`fs.writeFile()`**
Crée un fichier ou remplace son contenu existant.  
```javascript
fs.writeFile('mynewfile3.txt', 'Hello content!', function (err) {
  if (err) throw err;
  console.log('Saved!');
});
```

---

## **Mise à jour des fichiers**

### 1. **Ajouter du contenu à un fichier avec `fs.appendFile()`**
Ajoute du texte à la fin d'un fichier.  
```javascript
fs.appendFile('mynewfile1.txt', ' This is my text.', function (err) {
  if (err) throw err;
  console.log('Updated!');
});
```

### 2. **Remplacer le contenu avec `fs.writeFile()`**
Remplace complètement le contenu d'un fichier.  
```javascript
fs.writeFile('mynewfile3.txt', 'This is my text', function (err) {
  if (err) throw err;
  console.log('Replaced!');
});
```

---

## **Suppression de fichiers**

Utilisez la méthode `fs.unlink()` pour supprimer un fichier.  
```javascript
fs.unlink('mynewfile2.txt', function (err) {
  if (err) throw err;
  console.log('File deleted!');
});
```

---

## **Renommage de fichiers**

Utilisez la méthode `fs.rename()` pour renommer un fichier.  
```javascript
fs.rename('mynewfile1.txt', 'myrenamedfile.txt', function (err) {
  if (err) throw err;
  console.log('File Renamed!');
});
```

---

## **Résumé des méthodes importantes**

| Méthode          | Description                                           |
|-------------------|-------------------------------------------------------|
| `fs.readFile()`   | Lit le contenu d'un fichier.                         |
| `fs.appendFile()` | Ajoute du contenu à un fichier ou le crée.           |
| `fs.open()`       | Crée un fichier vide ou l'ouvre en mode écriture.    |
| `fs.writeFile()`  | Crée ou remplace le contenu d'un fichier.            |
| `fs.unlink()`     | Supprime un fichier.                                 |
| `fs.rename()`     | Renomme un fichier.                                  |

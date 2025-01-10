# Node.js Callbacks

## Introduction

Les callbacks sont des fonctions passées en argument à d'autres fonctions, et qui sont exécutées après que l'opération en cours soit terminée. Dans Node.js, les callbacks sont largement utilisés, notamment pour gérer des opérations asynchrones comme la lecture de fichiers, les requêtes HTTP, ou l'accès à une base de données.

---

## Qu'est-ce qu'un Callback ?

Un **callback** est une fonction qui est appelée une fois qu'une autre fonction a terminé son exécution. En Node.js, cela permet de gérer des tâches asynchrones, ce qui signifie que le programme peut continuer à s'exécuter pendant qu'une tâche prend du temps (comme la lecture d'un fichier ou une requête réseau).

---

## Exemple Simple de Callback

Dans cet exemple, une fonction est passée à une autre fonction pour être exécutée une fois que celle-ci a terminé son travail.

### Exemple :

```javascript
function sayHello(name, callback) {
  console.log('Hello ' + name);
  callback();  // Appelle la fonction callback une fois le message affiché
}

function callbackFunction() {
  console.log('Callback executed!');
}

sayHello('Alice', callbackFunction);
```

**Sortie :**
```
Hello Alice
Callback executed!
```

---

## Utilisation des Callbacks dans Node.js

Les fonctions de Node.js qui effectuent des opérations asynchrones (comme la lecture de fichiers) utilisent souvent des callbacks pour signaler que l'opération est terminée.

### Exemple avec la Lecture d'un Fichier

Node.js offre le module `fs` (système de fichiers) qui utilise des callbacks pour gérer la lecture de fichiers.

```javascript
var fs = require('fs');

fs.readFile('example.txt', 'utf8', function (err, data) {
  if (err) {
    console.log('Erreur de lecture du fichier', err);
  } else {
    console.log('Contenu du fichier :', data);
  }
});
```

Dans cet exemple :
- La fonction `readFile` lit un fichier de manière asynchrone.
- Une fois la lecture terminée, le callback est appelé avec les paramètres `err` (pour les erreurs) et `data` (le contenu du fichier).

---

## Gestion des Erreurs avec des Callbacks

Il est courant de gérer les erreurs dans un callback en vérifiant si le premier argument (`err`) est présent. Si une erreur se produit, cet argument contient l'erreur. Si tout se passe bien, il est `null`.

### Exemple avec une Gestion d'Erreur :

```javascript
fs.readFile('example.txt', 'utf8', function (err, data) {
  if (err) {
    console.log('Erreur :', err);
    return;  // Sort de la fonction si une erreur se produit
  }
  console.log('Contenu du fichier :', data);
});
```

---

## Callback Hell (L'Enfer des Callbacks)

Lorsque plusieurs callbacks sont imbriqués les uns dans les autres, le code peut devenir difficile à lire et à maintenir. Ce phénomène est souvent appelé "callback hell" ou "pyramid of doom".

### Exemple de Callback Hell :

```javascript
fs.readFile('file1.txt', 'utf8', function (err, data1) {
  if (err) throw err;
  fs.readFile('file2.txt', 'utf8', function (err, data2) {
    if (err) throw err;
    fs.readFile('file3.txt', 'utf8', function (err, data3) {
      if (err) throw err;
      console.log('Fichiers lus :', data1, data2, data3);
    });
  });
});
```

Dans cet exemple, chaque lecture de fichier est imbriquée dans le callback précédent, ce qui rend le code difficile à lire et à maintenir.


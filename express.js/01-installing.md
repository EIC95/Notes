# Installation et configuration de base d'Express.js

## 1. Installation de Node.js et Express.js

Avant de commencer à utiliser Express.js, il faut installer **Node.js**. Si ce n'est pas déjà fait, voici comment procéder :

### Installer Node.js
1. Va sur le site officiel de [Node.js](https://nodejs.org) et télécharge la version stable.
2. Suis les instructions d'installation en fonction de ton système d'exploitation.

### Vérifier l'installation
Après l'installation, ouvre ton terminal ou invite de commandes et tape les commandes suivantes pour vérifier que Node.js et npm (le gestionnaire de paquets) sont installés correctement :

```bash
node -v
npm -v
```
Cela devrait te renvoyer les versions de Node.js et npm installées sur ton système.

## 2. Créer un projet Node.js et installer Express

### Créer un dossier pour ton projet
Dans ton terminal, crée un dossier pour ton projet et rends-toi dedans :

```bash
mkdir mon-projet-express
cd mon-projet-express
```

### Initialiser le projet Node.js
Ensuite, initialise un projet Node.js dans ce dossier en exécutant la commande suivante :

```bash
npm init -y
```
Cela génère un fichier `package.json` avec les paramètres par défaut.

### Installer Express.js
Installe maintenant Express en utilisant npm :

```bash
npm install express
```
Cela va installer Express et ajouter la dépendance dans ton fichier `package.json`.

## 3. Créer un serveur Express de base

Maintenant, tu peux créer un fichier `app.js` dans ton dossier de projet et y mettre le code suivant pour démarrer un serveur Express :

```js
// Importer Express
const express = require('express');

// Créer une instance d'application Express
const app = express();

// Définir une route de base qui répond avec "Hello World"
app.get('/', (req, res) => {
  res.send('Hello World');
});

// Démarrer le serveur sur le port 3000
app.listen(3000, () => {
  console.log('Le serveur fonctionne sur le port 3000');
});
```

## 4. Exécuter le serveur

Dans ton terminal, lance ton serveur en exécutant la commande suivante :

```bash
node app.js
```
Le serveur démarre sur le port 3000, et tu devrais voir le message suivant dans ton terminal :

```
Le serveur fonctionne sur le port 3000
```

## 5. Vérifier ton serveur

Ouvre ton navigateur et tape l'URL suivante pour voir si ton serveur fonctionne :

```
http://localhost:3000
```

Tu devrais voir afficher **"Hello World"** dans ton navigateur.

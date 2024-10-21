# React Components

### Qu’est-ce qu’un composant React ?  
Les **composants** sont des morceaux de code indépendants et réutilisables, similaires à des fonctions JavaScript. Ils renvoient du **HTML** et fonctionnent de manière isolée. React propose deux types de composants :  

1. **Composants de classe** (peu utilisés aujourd’hui)  
2. **Composants fonctionnels** (recommandés, surtout avec les Hooks à partir de React 16.8)  

### Création d’un composant fonctionnel  
Un **composant fonctionnel** est une fonction qui renvoie du HTML. Par convention, le nom du composant doit commencer par une **majuscule**.

**Exemple de composant fonctionnel**  
```javascript
function Car() {
  return <h2>Hi, I am a Car!</h2>;
}
```

### Rendu d’un composant  
Pour afficher un composant dans le DOM, on utilise la méthode **`render()`** sur un élément racine.

**Exemple**  
```javascript
const root = ReactDOM.createRoot(document.getElementById('root'));
root.render(<Car />);
```

### Utilisation de props  
Les **props** sont des attributs passés aux composants, similaires aux arguments d’une fonction. Elles permettent de personnaliser les composants.

**Exemple avec props**  
```javascript
function Car(props) {
  return <h2>I am a {props.color} Car!</h2>;
}

const root = ReactDOM.createRoot(document.getElementById('root'));
root.render(<Car color="red" />);
```

### Composants imbriqués  
Un composant peut être utilisé dans un autre composant.

**Exemple de composant imbriqué**  
```javascript
function Car() {
  return <h2>I am a Car!</h2>;
}

function Garage() {
  return (
    <>
      <h1>Who lives in my Garage?</h1>
      <Car />
    </>
  );
}

const root = ReactDOM.createRoot(document.getElementById('root'));
root.render(<Garage />);
```

### Organisation des composants dans des fichiers  
Il est recommandé de **séparer les composants** dans des fichiers individuels pour faciliter la réutilisation. Chaque fichier de composant doit être exporté et importé dans l’application.  

**Exemple : Fichier Car.js**  
```javascript
function Car() {
  return <h2>Hi, I am a Car!</h2>;
}

export default Car;
```

**Import du composant Car dans l’application principale**  
```javascript
import React from 'react';
import ReactDOM from 'react-dom/client';
import Car from './Car.js';

const root = ReactDOM.createRoot(document.getElementById('root'));
root.render(<Car />);
```  
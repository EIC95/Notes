# Styling React avec CSS

Il existe plusieurs façons de **styler un composant React** avec CSS. Voici trois méthodes courantes :  

- **Inline Styling**  
- **CSS Stylesheets**  
- **CSS Modules**

---

## Inline Styling

Avec le **style inline**, on passe un **objet JavaScript** contenant les informations de style.

### Exemple simple

```javascript
const Header = () => {
  return (
    <>
      <h1 style={{ color: "red" }}>Hello Style!</h1>
      <p>Add a little style!</p>
    </>
  );
};
```

> **Note :** En JSX, les expressions JavaScript sont **placées entre accolades** `{}`. Pour définir le style inline, on doit donc utiliser **deux paires d'accolades** : `{{}}`.  

### Syntaxe camelCase

Les propriétés CSS avec des tirets comme `background-color` doivent être écrites en **camelCase** dans React.

```javascript
const Header = () => {
  return (
    <>
      <h1 style={{ backgroundColor: "lightblue" }}>Hello Style!</h1>
      <p>Add a little style!</p>
    </>
  );
};
```

---

### Utilisation d'un objet JavaScript

On peut définir un **objet de styles** et l’utiliser dans l’attribut `style`.

```javascript
const Header = () => {
  const myStyle = {
    color: "white",
    backgroundColor: "DodgerBlue",
    padding: "10px",
    fontFamily: "Sans-Serif"
  };

  return (
    <>
      <h1 style={myStyle}>Hello Style!</h1>
      <p>Add a little style!</p>
    </>
  );
};
```

---

## CSS Stylesheets

On peut aussi **écrire le CSS dans un fichier séparé** avec l'extension **`.css`** et l'importer dans notre composant.

### App.css

```css
/* App.css */
body {
  background-color: #282c34;
  color: white;
  padding: 40px;
  font-family: Sans-Serif;
  text-align: center;
}
```

### Importer le CSS dans React

```javascript
// index.js
import React from 'react';
import ReactDOM from 'react-dom/client';
import './App.css';

const Header = () => {
  return (
    <>
      <h1>Hello Style!</h1>
      <p>Add a little style!</p>
    </>
  );
};

const root = ReactDOM.createRoot(document.getElementById('root'));
root.render(<Header />);
```

---

## CSS Modules

Les **CSS Modules** sont utiles pour **isoler le style au niveau du composant**, évitant ainsi les conflits de noms.

### Créer un CSS Module

Créez un fichier **`my-style.module.css`** avec ce contenu :

```css
/* my-style.module.css */
.bigblue {
  color: DodgerBlue;
  padding: 40px;
  font-family: Sans-Serif;
  text-align: center;
}
```

### Utiliser un CSS Module

```javascript
// Car.js
import styles from './my-style.module.css';

const Car = () => {
  return <h1 className={styles.bigblue}>Hello Car!</h1>;
};

export default Car;
```

### Importer le composant dans l’application

```javascript
// index.js
import ReactDOM from 'react-dom/client';
import Car from './Car.js';

const root = ReactDOM.createRoot(document.getElementById('root'));
root.render(<Car />);
```

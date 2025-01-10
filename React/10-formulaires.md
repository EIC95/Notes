# Les formulaires en React

Comme en HTML, React utilise des **formulaires** pour permettre aux utilisateurs d’interagir avec la page web. Cependant, React contrôle les formulaires différemment : il **gère l'état** des données dans les composants.

---

## Ajouter un formulaire en React

Créer un formulaire en React se fait de manière similaire à HTML.

### Exemple : Formulaire de base

```javascript
function MyForm() {
  return (
    <form>
      <label>Enter your name:
        <input type="text" />
      </label>
    </form>
  );
}

const root = ReactDOM.createRoot(document.getElementById('root'));
root.render(<MyForm />);
```

Par défaut, le **formulaire se soumet et recharge la page** lorsqu’on appuie sur "Entrée". Mais en React, nous souhaitons **contrôler ce comportement** pour gérer l'état avec des Hooks.

---

## Gestion des formulaires en React

Pour que React contrôle un formulaire, nous utilisons :
1. **`useState`** pour garder la trace des valeurs d'entrée.
2. **`onChange`** pour détecter les modifications des champs.
3. **`onSubmit`** pour gérer la soumission du formulaire.

---

## Exemple : Contrôler un champ avec `useState`

```javascript
import { useState } from 'react';
import ReactDOM from 'react-dom/client';

function MyForm() {
  const [name, setName] = useState("");

  return (
    <form>
      <label>Enter your name:
        <input 
          type="text" 
          value={name} 
          onChange={(e) => setName(e.target.value)} 
        />
      </label>
    </form>
  );
}

const root = ReactDOM.createRoot(document.getElementById('root'));
root.render(<MyForm />);
```

- **`useState`** garde l'état du champ d’entrée.
- **`onChange`** met à jour l’état à chaque saisie de l’utilisateur.

---

## Soumettre un formulaire avec React

Nous utilisons **`onSubmit`** pour empêcher le rechargement de la page.

### Exemple : Formulaire avec soumission

```javascript
import { useState } from 'react';
import ReactDOM from 'react-dom/client';

function MyForm() {
  const [name, setName] = useState("");

  const handleSubmit = (event) => {
    event.preventDefault(); // Empêche le rechargement de la page
    alert(`The name you entered was: ${name}`);
  };

  return (
    <form onSubmit={handleSubmit}>
      <label>Enter your name:
        <input 
          type="text" 
          value={name} 
          onChange={(e) => setName(e.target.value)} 
        />
      </label>
      <input type="submit" />
    </form>
  );
}

const root = ReactDOM.createRoot(document.getElementById('root'));
root.render(<MyForm />);
```

---

## Formulaire avec plusieurs champs

Nous utilisons un **objet d'état** pour suivre plusieurs champs d'entrée.

### Exemple : Formulaire avec plusieurs champs

```javascript
import { useState } from 'react';
import ReactDOM from 'react-dom/client';

function MyForm() {
  const [inputs, setInputs] = useState({});

  const handleChange = (event) => {
    const { name, value } = event.target;
    setInputs((values) => ({ ...values, [name]: value }));
  };

  const handleSubmit = (event) => {
    event.preventDefault();
    alert(JSON.stringify(inputs)); // Affiche les valeurs sous forme de chaîne JSON
  };

  return (
    <form onSubmit={handleSubmit}>
      <label>Enter your name:
        <input 
          type="text" 
          name="username" 
          value={inputs.username || ""} 
          onChange={handleChange} 
        />
      </label>
      <label>Enter your age:
        <input 
          type="number" 
          name="age" 
          value={inputs.age || ""} 
          onChange={handleChange} 
        />
      </label>
      <input type="submit" />
    </form>
  );
}

const root = ReactDOM.createRoot(document.getElementById('root'));
root.render(<MyForm />);
```

- **`handleChange`** est utilisé pour tous les champs en exploitant leur **nom** et **valeur**.
- Les **crochets** autour du nom du champ permettent d’ajouter dynamiquement des propriétés.

---

## Textarea en React

Contrairement à HTML, la valeur du **textarea** est gérée par l’attribut `value` et non entre les balises.

### Exemple : Textarea contrôlé

```javascript
import { useState } from 'react';

function MyForm() {
  const [textarea, setTextarea] = useState(
    "The content of a textarea goes in the value attribute"
  );

  const handleChange = (event) => {
    setTextarea(event.target.value);
  };

  return (
    <form>
      <textarea value={textarea} onChange={handleChange} />
    </form>
  );
}

const root = ReactDOM.createRoot(document.getElementById('root'));
root.render(<MyForm />);
```

---

## Sélectionner une option dans un `select`

Comme pour `textarea`, la valeur sélectionnée dans une liste déroulante est définie avec l’attribut **`value`**.

### Exemple : Liste déroulante contrôlée

```javascript
import { useState } from 'react';

function MyForm() {
  const [myCar, setMyCar] = useState("Volvo");

  const handleChange = (event) => {
    setMyCar(event.target.value);
  };

  return (
    <form>
      <select value={myCar} onChange={handleChange}>
        <option value="Ford">Ford</option>
        <option value="Volvo">Volvo</option>
        <option value="Fiat">Fiat</option>
      </select>
    </form>
  );
}

const root = ReactDOM.createRoot(document.getElementById('root'));
root.render(<MyForm />);
```

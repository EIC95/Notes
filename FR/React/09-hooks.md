# Les Hooks en React

Les **Hooks** ont été introduits dans React avec la version **16.8**. Ils permettent d'utiliser l'état et d'autres fonctionnalités de React dans des **composants fonctionnels**, rendant ainsi les classes moins nécessaires. Bien que les Hooks remplacent généralement les composants de classe, ceux-ci restent disponibles.

---

## Qu’est-ce qu’un Hook ?

Un **Hook** est une fonction spéciale qui permet de "brancher" des fonctionnalités React (comme l'état ou les effets de cycle de vie) dans les **composants fonctionnels**. Cela simplifie la gestion des composants et évite d’utiliser des classes.

---

## Règles des Hooks

1. **Uniquement dans des composants fonctionnels** : Les Hooks ne fonctionnent pas dans les composants de classe.
2. **Toujours au niveau supérieur** : Les Hooks doivent être appelés directement dans le corps d’un composant (pas dans des boucles ou conditions).
3. **Non conditionnels** : Vous ne pouvez pas appeler un Hook à l’intérieur d’un `if` ou d’une boucle `for`.

---

## Liste des principaux Hooks

### 1. **useState** – Gérer l’état d’un composant

Ce Hook permet de définir un **état local** dans un composant fonctionnel.

#### Exemple :

```javascript
import { useState } from 'react';
import ReactDOM from 'react-dom/client';

function FavoriteColor() {
  const [color, setColor] = useState("red");

  return (
    <>
      <h1>My favorite color is {color}!</h1>
      <button onClick={() => setColor("blue")}>Blue</button>
      <button onClick={() => setColor("red")}>Red</button>
      <button onClick={() => setColor("pink")}>Pink</button>
      <button onClick={() => setColor("green")}>Green</button>
    </>
  );
}

const root = ReactDOM.createRoot(document.getElementById('root'));
root.render(<FavoriteColor />);
```

- **`useState`** renvoie un **tableau** avec deux éléments :  
  1. La **valeur de l'état**  
  2. Une **fonction pour mettre à jour l’état**  

---

### 2. **useEffect** – Gestion des effets secondaires

Utilisé pour exécuter du code après le rendu du composant (comme des **requêtes API** ou la gestion du **DOM**).

#### Exemple :

```javascript
import { useState, useEffect } from 'react';

function Timer() {
  const [count, setCount] = useState(0);

  useEffect(() => {
    const interval = setInterval(() => {
      setCount((prevCount) => prevCount + 1);
    }, 1000);

    return () => clearInterval(interval); // Nettoyage de l'intervalle
  }, []);

  return <h1>Time: {count}s</h1>;
}
```

- **`useEffect`** s’exécute après chaque rendu.
- Le **retour de `useEffect`** (la fonction `return`) est appelé pour **nettoyer** l'effet.

---

### 3. **useContext** – Partager des états globaux

Le **contexte** permet de partager des données entre plusieurs composants sans les passer en **props** à chaque niveau.

#### Exemple :

```javascript
import { useState, createContext, useContext } from 'react';

const UserContext = createContext();

function DisplayUser() {
  const user = useContext(UserContext);
  return <h1>Hello, {user}!</h1>;
}

function App() {
  const [user, setUser] = useState("Alice");

  return (
    <UserContext.Provider value={user}>
      <DisplayUser />
    </UserContext.Provider>
  );
}

const root = ReactDOM.createRoot(document.getElementById('root'));
root.render(<App />);
```

- **`useContext`** permet d’accéder à une **valeur de contexte** sans utiliser de props.

---

### 4. **useRef** – Références directes à des éléments

Permet d’obtenir une **référence directe** à un élément du DOM ou de conserver une valeur entre les rendus sans déclencher de re-rendu.

#### Exemple :

```javascript
import { useRef } from 'react';

function TextInput() {
  const inputRef = useRef(null);

  const focusInput = () => {
    inputRef.current.focus();
  };

  return (
    <>
      <input ref={inputRef} type="text" />
      <button onClick={focusInput}>Focus Input</button>
    </>
  );
}

const root = ReactDOM.createRoot(document.getElementById('root'));
root.render(<TextInput />);
```

- **`useRef`** renvoie un **objet mutable** (`current`) qui persiste entre les rendus.

---

### 5. **useReducer** – Gestion complexe de l’état

Similaire à `useState`, mais permet de mieux gérer des **états complexes**.

#### Exemple :

```javascript
import { useReducer } from 'react';

function reducer(state, action) {
  switch (action.type) {
    case 'increment':
      return { count: state.count + 1 };
    case 'decrement':
      return { count: state.count - 1 };
    default:
      throw new Error();
  }
}

function Counter() {
  const [state, dispatch] = useReducer(reducer, { count: 0 });

  return (
    <>
      <h1>Count: {state.count}</h1>
      <button onClick={() => dispatch({ type: 'increment' })}>+</button>
      <button onClick={() => dispatch({ type: 'decrement' })}>-</button>
    </>
  );
}

const root = ReactDOM.createRoot(document.getElementById('root'));
root.render(<Counter />);
```

- **`useReducer`** prend une fonction réductrice (`reducer`) et un état initial.

---

### 6. **useMemo** – Optimisation des calculs

Utilisé pour **mémoriser** un résultat de calcul et **éviter des recalculs inutiles**.

#### Exemple :

```javascript
import { useState, useMemo } from 'react';

function ExpensiveCalculation(num) {
  console.log('Calculating...');
  return num * 2;
}

function App() {
  const [count, setCount] = useState(0);
  const double = useMemo(() => ExpensiveCalculation(count), [count]);

  return (
    <>
      <h1>Double: {double}</h1>
      <button onClick={() => setCount(count + 1)}>Increment</button>
    </>
  );
}

const root = ReactDOM.createRoot(document.getElementById('root'));
root.render(<App />);
```

- **`useMemo`** ne recalculera la valeur que si la **dépendance** (ici `count`) change.

---

### 7. **useCallback** – Mémorisation de fonctions

Utilisé pour **mémoriser une fonction**, utile lors du passage de fonctions en **props**.

#### Exemple :

```javascript
import { useState, useCallback } from 'react';

function Button({ onClick }) {
  console.log('Button rendered');
  return <button onClick={onClick}>Click me</button>;
}

function App() {
  const [count, setCount] = useState(0);

  const increment = useCallback(() => setCount((c) => c + 1), []);

  return (
    <>
      <h1>Count: {count}</h1>
      <Button onClick={increment} />
    </>
  );
}

const root = ReactDOM.createRoot(document.getElementById('root'));
root.render(<App />);
```

---

## Hooks personnalisés

Vous pouvez créer vos **propres Hooks** pour réutiliser de la logique entre plusieurs composants.

#### Exemple : Hook personnalisé

```javascript
import { useState, useEffect } from 'react';

function useWindowWidth() {
  const [width, setWidth] = useState(window.innerWidth);

  useEffect(() => {
    const handleResize = () => setWidth(window.innerWidth);
    window.addEventListener('resize', handleResize);

    return () => window.removeEventListener('resize', handleResize);
  }, []);

  return width;
}

function App() {
  const width = useWindowWidth();

  return <h1>Window width: {width}px</h1>;
}

const root = ReactDOM.createRoot(document.getElementById('root'));
root.render(<App />);
```

---

## Conclusion

Les **Hooks** simplifient le développement en React en permettant d’utiliser l’état, les effets et d’autres fonctionnalités dans les **composants fonctionnels**. Ils favorisent aussi la **réutilisation** de logique avec les Hooks personnalisés.
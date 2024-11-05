# Les Hooks en React

Les **Hooks** ont été introduits dans React avec la version **16.8**. Ils permettent d'utiliser l'état et d'autres fonctionnalités de React dans des **composants fonctionnels**, rendant ainsi les classes moins nécessaires. Bien que les Hooks remplacent généralement les composants de classe, ceux-ci restent disponibles pour ceux qui préfèrent cette approche.

---

## Qu’est-ce qu’un Hook ?

Un **Hook** est une fonction spéciale qui permet de "brancher" des fonctionnalités React (comme l'état ou les effets de cycle de vie) dans les **composants fonctionnels**. Cela simplifie la gestion des composants et évite d’utiliser des classes. Les Hooks permettent également de mieux structurer et réutiliser la logique dans les applications.

---

## Règles des Hooks

Pour utiliser les Hooks de manière appropriée, il est important de respecter certaines règles :

1. **Uniquement dans des composants fonctionnels** : Les Hooks ne fonctionnent pas dans les composants de classe. Ils sont conçus pour être utilisés uniquement dans des fonctions.
  
2. **Toujours au niveau supérieur** : Les Hooks doivent être appelés directement dans le corps d’un composant. Ne les appelez pas à l'intérieur de boucles, conditions, ou fonctions imbriquées.
  
3. **Non conditionnels** : Vous ne pouvez pas appeler un Hook à l’intérieur d’un `if` ou d’une boucle `for`. Cela garantit que les Hooks sont appelés dans le même ordre à chaque rendu.

---

## Liste des principaux Hooks

### 1. **useState** – Gérer l’état d’un composant

Le Hook `useState` permet de définir un **état local** dans un composant fonctionnel. Il renvoie un tableau contenant la valeur de l'état et une fonction pour mettre à jour cet état.

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

- **Détails** :
  - `useState` initialise l'état avec la valeur fournie et renvoie un tableau où :
    - Le premier élément est la **valeur de l'état**.
    - Le deuxième élément est la **fonction pour mettre à jour l’état**.

---

### 2. **useEffect** – Gestion des effets secondaires

Le Hook `useEffect` est utilisé pour exécuter du code après le rendu du composant, comme des **requêtes API** ou la gestion du **DOM**. Il peut également être utilisé pour gérer des effets secondaires comme des abonnements ou des minuteries.

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
  }, []); // Dépendance vide, donc s'exécute uniquement au premier rendu

  return <h1>Time: {count}s</h1>;
}
```

- **Détails** :
  - `useEffect` s’exécute après chaque rendu par défaut.
  - Le **retour de `useEffect`** (la fonction `return`) est appelé pour **nettoyer** l'effet, permettant d'éviter des fuites de mémoire.

---

### 3. **useContext** – Partager des états globaux

Le **contexte** permet de partager des données entre plusieurs composants sans avoir à les passer en **props** à chaque niveau. Cela simplifie la gestion des états globaux, comme l'utilisateur authentifié ou les thèmes.

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

- **Détails** :
  - `useContext` permet d’accéder à une **valeur de contexte** sans avoir besoin de passer cette valeur via des props, ce qui peut simplifier la structure de vos composants.

---

### 4. **useRef** – Références directes à des éléments

Le Hook `useRef` permet d’obtenir une **référence directe** à un élément du DOM ou de conserver une valeur entre les rendus sans déclencher de re-rendu. Il est souvent utilisé pour interagir directement avec le DOM.

#### Exemple :

```javascript
import { useRef } from 'react';

function TextInput() {
  const inputRef = useRef(null);

  const focusInput = () => {
    inputRef.current.focus(); // Focalise l'input
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

- **Détails** :
  - `useRef` renvoie un **objet mutable** (`current`) qui persiste entre les rendus, ce qui le rend utile pour accéder à des éléments DOM ou conserver des valeurs qui ne déclenchent pas de re-rendu.

---

### 5. **useReducer** – Gestion complexe de l’état

Le Hook `useReducer` est similaire à `useState`, mais il est plus adapté à la gestion d'états complexes ou à des états qui dépendent des actions.

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

- **Détails** :
  - `useReducer` prend une fonction réductrice (`reducer`) et un état initial, ce qui facilite la gestion des mises à jour d'état en fonction d'actions spécifiques.

---

### 6. **useMemo** – Optimisation des calculs

Le Hook `useMemo` est utilisé pour **mémoriser** un résultat de calcul, évitant ainsi des recalculs inutiles lors des rendus.

#### Exemple :

```javascript
import { useState, useMemo } from 'react';

function ExpensiveCalculation(num) {
  console.log('Calculating...');
  return num * 2; // Simulation d'un calcul coûteux
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

- **Détails** :
  - `useMemo` ne recalculera la valeur que si la **dépendance** (ici `count`) change, optimisant ainsi les performances.

---

### 7. **useCallback** – Mémorisation de fonctions

Le Hook `useCallback` est utilisé pour **mémoriser une fonction**, ce qui est particulièrement utile lors du passage de fonctions en **props** pour éviter des re-rendus inutiles des composants enfants.

#### Exemple :

```javascript
import { useState, useCallback } from 'react';

function Button({ onClick }) {
  console.log('Button rendered');
  return <button onClick={onClick}>Click me</button>;
}

function App() {
  const [count, setCount] = useState(0);

  const increment = useCallback(() => setCount((c) => c + 1), []); // Mémorisation de la fonction

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

- **Détails** :
  - `useCallback` renvoie une version mémorisée de la fonction fournie, qui ne change que si une de ses dépendances change.

---

## Hooks personnalisés

Vous pouvez créer vos **propres Hooks** pour réutiliser de la logique entre plusieurs composants. Cela vous permet de partager facilement des comportements entre différents composants sans répéter le code.

#### Exemple : Hook personnalisé

```javascript
import { useState, useEffect } from 'react';

function useWindowWidth() {
  const [width, setWidth] = useState(window.innerWidth);

  useEffect(() => {
    const handleResize = () => setWidth(window.innerWidth); // Met à jour la largeur lors du redimensionnement
    window.addEventListener('resize', handleResize);

    return () => window.removeEventListener('resize', handleResize); // Nettoyage de l'écouteur d'événements
  }, []);

  return width; // Renvoie la largeur de la fenêtre
}

function App() {
  const width = useWindowWidth();

  return <h1>Window width: {width}px</h1>;
}

const root = ReactDOM.createRoot(document.getElementById('root'));
root.render(<App />);
```

- **Détails** :
  - Les Hooks personnalisés permettent de regrouper et d'encapsuler la logique réutilisable, ce qui rend le code plus propre et plus facile à maintenir.

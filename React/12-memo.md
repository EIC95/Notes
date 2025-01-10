# React Memo

**`React.memo`** permet à React d'**éviter de re-render** un composant si ses **props n'ont pas changé**, améliorant ainsi les **performances** de l’application.

---

## Problème

Dans l'exemple suivant, le composant **`Todos`** se re-render à chaque fois qu'on clique sur le bouton d'incrémentation, **même si les todos ne changent pas**.

### index.js

```javascript
import { useState } from "react";
import ReactDOM from "react-dom/client";
import Todos from "./Todos";

const App = () => {
  const [count, setCount] = useState(0);
  const [todos, setTodos] = useState(["todo 1", "todo 2"]);

  const increment = () => {
    setCount((c) => c + 1);
  };

  return (
    <>
      <Todos todos={todos} />
      <hr />
      <div>
        Count: {count}
        <button onClick={increment}>+</button>
      </div>
    </>
  );
};

const root = ReactDOM.createRoot(document.getElementById('root'));
root.render(<App />);
```

---

### Todos.js

```javascript
const Todos = ({ todos }) => {
  console.log("child render"); // Indique chaque re-render du composant

  return (
    <>
      <h2>My Todos</h2>
      {todos.map((todo, index) => (
        <p key={index}>{todo}</p>
      ))}
    </>
  );
};

export default Todos;
```

Dans ce cas, **le composant Todos se re-render** même si les `todos` ne changent pas, car React **re-render tous les composants enfants** lorsque l'état du parent change (ici avec `count`).

---

## Solution : Utiliser React.memo

Pour **éviter les re-renders inutiles**, nous allons utiliser **`React.memo`**. Cela permet à React de **mémoriser** le composant `Todos` et de **ne le re-render que lorsque ses props changent**.

---

### Mise à jour de Todos.js

```javascript
import { memo } from "react";

const Todos = ({ todos }) => {
  console.log("child render"); // S'affiche uniquement si les todos changent

  return (
    <>
      <h2>My Todos</h2>
      {todos.map((todo, index) => (
        <p key={index}>{todo}</p>
      ))}
    </>
  );
};

export default memo(Todos);
```

---

### Explication

- **`memo`** empêche le composant `Todos` de se re-render **à moins que les `todos` ne changent**.
- Si la prop `todos` reste identique (comme dans cet exemple), **le composant ne sera pas re-rendu**.

---

### Test du Comportement

- Cliquez sur le bouton d'incrémentation (**Count**) :  
  - Avant d’ajouter **`memo`**, le message **"child render"** apparaissait à chaque clic.
  - Après avoir ajouté **`memo`**, le message ne s'affiche plus à chaque clic sur **Count**, car `todos` n’a pas changé.


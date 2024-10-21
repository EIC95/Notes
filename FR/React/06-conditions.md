# Rendu conditionnel en React  

En **React**, il est possible d’afficher des composants de manière conditionnelle en fonction d’une situation donnée. Voici plusieurs façons de le faire.

---

### Utiliser l'instruction `if`  
L’instruction JavaScript `if` permet de choisir quel composant afficher selon une condition.  

**Exemple avec `if` :**  
```javascript
function MissedGoal() {
  return <h1>MISSED!</h1>;
}

function MadeGoal() {
  return <h1>Goal!</h1>;
}

function Goal(props) {
  const isGoal = props.isGoal;
  if (isGoal) {
    return <MadeGoal />;
  }
  return <MissedGoal />;
}

const root = ReactDOM.createRoot(document.getElementById('root'));
root.render(<Goal isGoal={false} />);
```
- Si `isGoal` est **`true`**, le composant `MadeGoal` s'affiche.  
- Sinon, le composant `MissedGoal` est rendu.  

---

### Opérateur logique `&&`  
L'opérateur logique **`&&`** permet d’afficher un composant **seulement si une condition est vraie**.  

**Exemple avec `&&` :**  
```javascript
function Garage(props) {
  const cars = props.cars;
  return (
    <>
      <h1>Garage</h1>
      {cars.length > 0 && (
        <h2>You have {cars.length} cars in your garage.</h2>
      )}
    </>
  );
}

const cars = ['Ford', 'BMW', 'Audi'];
const root = ReactDOM.createRoot(document.getElementById('root'));
root.render(<Garage cars={cars} />);
```
Si le tableau `cars` contient des éléments, le message `"You have X cars in your garage."` est affiché.  

**Testez avec un tableau vide :**  
```javascript
const cars = [];
root.render(<Garage cars={cars} />);
```
Dans ce cas, **aucun message ne sera affiché**, car la condition `cars.length > 0` est fausse.

---

### Utiliser l'opérateur ternaire  
L’opérateur ternaire permet de **retourner un composant ou un autre** en fonction d’une condition.

**Syntaxe :**  
```javascript
condition ? valeur_si_vrai : valeur_si_faux
```

**Exemple avec opérateur ternaire :**  
```javascript
function Goal(props) {
  const isGoal = props.isGoal;
  return (
    <>
      {isGoal ? <MadeGoal /> : <MissedGoal />}
    </>
  );
}

const root = ReactDOM.createRoot(document.getElementById('root'));
root.render(<Goal isGoal={false} />);
```
- Si `isGoal` est **`true`**, le composant `MadeGoal` est affiché.  
- Sinon, c’est `MissedGoal` qui est rendu.

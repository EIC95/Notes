# React JSX

### Qu'est-ce que JSX ?  
JSX signifie **JavaScript XML**. Il permet d’écrire du HTML directement dans du code JavaScript, simplifiant ainsi la création d’interfaces. Avec JSX, il n’est plus nécessaire d’utiliser les méthodes `createElement()` ou `appendChild()` pour manipuler le DOM, car les balises HTML sont automatiquement converties en **éléments React**.

**Exemple avec JSX**  
```javascript
const myElement = <h1>I Love JSX!</h1>;
const root = ReactDOM.createRoot(document.getElementById('root'));
root.render(myElement);
```

**Exemple sans JSX**  
```javascript
const myElement = React.createElement('h1', {}, 'I do not use JSX!');
const root = ReactDOM.createRoot(document.getElementById('root'));
root.render(myElement);
```

JSX est basé sur **ES6** et est converti en JavaScript classique à l’exécution.

### Expressions dans JSX  
Les expressions JavaScript peuvent être insérées directement dans du JSX entre **{ }**. Elles peuvent inclure des variables, des calculs ou des propriétés.

**Exemple**  
```javascript
const myElement = <h1>React is {5 + 5} times better with JSX</h1>;
```

### Insertion de blocs HTML  
Pour écrire du HTML sur plusieurs lignes, il faut l’**envelopper entre parenthèses**.

**Exemple**  
```javascript
const myElement = (
  <ul>
    <li>Apples</li>
    <li>Bananas</li>
    <li>Cherries</li>
  </ul>
);
```

### Utilisation d’un seul élément parent  
Tout code HTML dans JSX doit être **enveloppé dans un seul élément parent**. Cela peut être une balise `<div>` ou un **fragment** pour éviter d’ajouter des balises inutiles dans le DOM.

**Exemple avec une div**  
```javascript
const myElement = (
  <div>
    <p>I am a paragraph.</p>
    <p>I am a paragraph too.</p>
  </div>
);
```

**Exemple avec un fragment**  
```javascript
const myElement = (
  <>
    <p>I am a paragraph.</p>
    <p>I am a paragraph too.</p>
  </>
);
```

### Fermeture des éléments  
Les balises HTML doivent être correctement **fermées** pour respecter les règles JSX.

**Exemple**  
```javascript
const myElement = <input type="text" />;
```

### Attribut `className` au lieu de `class`  
Comme `class` est un mot-clé réservé en JavaScript, JSX utilise **`className`** à la place. Ce dernier sera converti en `class` lors de l'affichage.

**Exemple**  
```javascript
const myElement = <h1 className="myclass">Hello World</h1>;
```

### Conditions dans JSX  
Les **if statements** ne peuvent pas être utilisés directement dans du JSX. Pour ajouter des conditions, on peut les placer **en dehors du JSX** ou utiliser une **expression ternaire**.

**Option 1 : if à l’extérieur du JSX**  
```javascript
const x = 5;
let text = "Goodbye";
if (x < 10) {
  text = "Hello";
}
const myElement = <h1>{text}</h1>;
```

**Option 2 : Expression ternaire**  
```javascript
const x = 5;
const myElement = <h1>{x < 10 ? "Hello" : "Goodbye"}</h1>;
```
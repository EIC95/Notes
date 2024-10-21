# React Props

### Qu’est-ce que les props ?  
Les **props** (propriétés) sont des **arguments passés aux composants React** via des **attributs HTML**. Elles permettent de transmettre des **données dynamiques** aux composants et de les réutiliser efficacement. Les props sont similaires aux **paramètres** d’une fonction en JavaScript.

### Utilisation des props  
Pour envoyer une prop à un composant, on l'ajoute sous forme d'attribut HTML.

**Exemple d'attribut props**  
```javascript
const myElement = <Car brand="Ford" />;
```

Le composant **reçoit cet attribut** dans un **objet `props`** et l'utilise.

**Exemple d'utilisation de props**  
```javascript
function Car(props) {
  return <h2>I am a {props.brand}!</h2>;
}

const root = ReactDOM.createRoot(document.getElementById('root'));
root.render(<Car brand="Ford" />);
```

### Passer des données d’un composant à un autre  
Les props sont un moyen de **transmettre des données** d’un composant parent à un composant enfant.

**Exemple avec composant parent/enfant**  
```javascript
function Car(props) {
  return <h2>I am a {props.brand}!</h2>;
}

function Garage() {
  return (
    <>
      <h1>Who lives in my garage?</h1>
      <Car brand="Ford" />
    </>
  );
}

const root = ReactDOM.createRoot(document.getElementById('root'));
root.render(<Garage />);
```

### Passer une variable comme props 
Si vous avez une **variable** à transmettre, utilisez des **accolades** autour de la variable dans l’attribut.

**Exemple avec une variable**  
```javascript
function Car(props) {
  return <h2>I am a {props.brand}!</h2>;
}

function Garage() {
  const carName = "Ford";
  return (
    <>
      <h1>Who lives in my garage?</h1>
      <Car brand={carName} />
    </>
  );
}

const root = ReactDOM.createRoot(document.getElementById('root'));
root.render(<Garage />);
```

### Passer un objet comme prop  
Les props peuvent également être des **objets**.

**Exemple avec un objet prop**  
```javascript
function Car(props) {
  return <h2>I am a {props.brand.model}!</h2>;
}

function Garage() {
  const carInfo = { name: "Ford", model: "Mustang" };
  return (
    <>
      <h1>Who lives in my garage?</h1>
      <Car brand={carInfo} />
    </>
  );
}

const root = ReactDOM.createRoot(document.getElementById('root'));
root.render(<Garage />);
```

### Note importante  
Les **props sont en lecture seule**. Une fois passées à un composant, elles **ne peuvent pas être modifiées**. Toute tentative de modification d'une prop entraînera une erreur.
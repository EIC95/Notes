# Listes en React

En **React**, on utilise souvent des boucles pour **afficher des listes** d’éléments. La méthode **`map()`** de JavaScript est généralement privilégiée pour parcourir les tableaux et générer les éléments correspondants.

---

### Exemple de rendu de liste avec `map()`

Dans cet exemple, nous allons afficher une liste de voitures.

```javascript
function Car(props) {
  return <li>I am a {props.brand}</li>;
}

function Garage() {
  const cars = ['Ford', 'BMW', 'Audi'];
  return (
    <>
      <h1>Who lives in my garage?</h1>
      <ul>
        {cars.map((car) => <Car brand={car} />)}
      </ul>
    </>
  );
}

const root = ReactDOM.createRoot(document.getElementById('root'));
root.render(<Garage />);
```

- **Explication** :  
  - La méthode **`map()`** parcourt le tableau `cars` et renvoie un élément `<Car>` pour chaque voiture.
  - Chaque composant **`Car`** reçoit une propriété `brand` correspondant à une marque.

**Problème** : Vous recevrez une **alerte** indiquant qu’un "key" est manquant pour chaque élément de la liste.

---

### Clés en React

Les **clés** permettent à React d'identifier chaque élément de la liste de manière unique. Elles sont **essentielles** pour optimiser le rendu : React met à jour uniquement les éléments modifiés ou supprimés, au lieu de rendre la liste complète.

#### Règles pour les clés :
- La **clé** doit être **unique parmi les éléments frères**.
- Vous pouvez utiliser :
  - Un **identifiant unique**.
  - En dernier recours, l'**index** du tableau (mais ce n’est pas recommandé si les données sont susceptibles de changer).

---

### Ajout de clés à la liste

Nous allons améliorer l’exemple précédent en incluant des clés uniques pour chaque voiture :

```javascript
function Car(props) {
  return <li>I am a {props.brand}</li>;
}

function Garage() {
  const cars = [
    { id: 1, brand: 'Ford' },
    { id: 2, brand: 'BMW' },
    { id: 3, brand: 'Audi' }
  ];
  
  return (
    <>
      <h1>Who lives in my garage?</h1>
      <ul>
        {cars.map((car) => (
          <Car key={car.id} brand={car.brand} />
        ))}
      </ul>
    </>
  );
}

const root = ReactDOM.createRoot(document.getElementById('root'));
root.render(<Garage />);
```

- **Explication** :
  - Chaque voiture est maintenant un **objet** avec un `id` unique et une `brand`.
  - Nous utilisons la **propriété `key`** pour assigner une clé unique à chaque composant `Car`.
  - Cela permet à React de savoir quel élément mettre à jour en cas de modification ou suppression.


# React Events  

### Qu’est-ce qu’un événement en React ?  
Tout comme dans le **DOM HTML**, React peut exécuter des **actions basées sur des événements utilisateurs** (ex. clic, survol). La gestion d'événements en React suit une syntaxe légèrement différente.  

### Ajouter un événement en React  
1. Les noms des événements sont écrits en **camelCase** (ex. `onClick` au lieu de `onclick`).
2. Les **fonctions de gestion d'événements** (event handlers) sont placées entre **accolades** `{}`.

**Exemple d'ajout d'un événement `onClick` :**  
```javascript
function Football() {
  const shoot = () => {
    alert("Great Shot!");
  };

  return (
    <button onClick={shoot}>Take the shot!</button>
  );
}

const root = ReactDOM.createRoot(document.getElementById('root'));
root.render(<Football />);
```
Ici, **l'alerte** est déclenchée lorsque l’utilisateur clique sur le bouton. L'événement est écrit avec `onClick` en camelCase.


### Passer des arguments aux gestionnaires d’événements  
Pour **transmettre un argument** à une fonction événementielle, on utilise une **fonction fléchée** dans le gestionnaire d'événements.

**Exemple avec paramètre :**  
```javascript
function Football() {
  const shoot = (message) => {
    alert(message);
  };

  return (
    <button onClick={() => shoot("Goal!")}>Take the shot!</button>
  );
}

const root = ReactDOM.createRoot(document.getElementById('root'));
root.render(<Football />);
```
Ici, en cliquant sur le bouton, **l’alerte affiche "Goal!"** grâce à la fonction fléchée dans l'attribut `onClick`.

---

### Objet événement React  
Les gestionnaires d'événements ont accès à un **objet événement React**, similaire à l'objet événement du DOM. Cet objet contient des informations comme le **type d’événement** (ex. `click`).

**Exemple avec objet événement :**  
```javascript
function Football() {
  const shoot = (message, event) => {
    alert(event.type);  // Affiche "click"
  };

  return (
    <button onClick={(event) => shoot("Goal!", event)}>Take the shot!</button>
  );
}

const root = ReactDOM.createRoot(document.getElementById('root'));
root.render(<Football />);
```
Dans cet exemple :  
- Le gestionnaire d’événement **reçoit "Goal!" et l'objet événement**.  
- L'alerte affiche le **type de l'événement** (ici "click").   
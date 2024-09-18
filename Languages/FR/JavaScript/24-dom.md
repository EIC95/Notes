# Document Object Model (DOM)

Le **Document Object Model (DOM)** est une interface de programmation qui permet aux scripts d'accéder et de manipuler le contenu, la structure et le style des documents HTML et XML. Le DOM représente le document sous la forme d'une arborescence hiérarchique où chaque nœud est un objet représentant une partie du document (éléments, attributs, texte, etc.). Cette structure permet aux développeurs de naviguer dans le document et de modifier son contenu dynamiquement en utilisant des langages de programmation comme JavaScript.

## Sélection des Éléments

### Méthodes de Sélection

- **`getElementById(id)`** : Sélectionne un élément par son ID.
- **`getElementsByClassName(className)`** : Sélectionne tous les éléments avec une certaine classe.
- **`getElementsByTagName(tagName)`** : Sélectionne les éléments par leur nom de balise.
- **`querySelector(selector)`** : Sélectionne le premier élément correspondant au sélecteur CSS.
- **`querySelectorAll(selector)`** : Sélectionne tous les éléments correspondant au sélecteur CSS.

## Manipulation des Éléments

### Modification du Contenu

- **`innerHTML`** : Change le contenu HTML intérieur d'un élément.
- **`textContent`** : Modifie le texte à l'intérieur d'un élément.

### Manipulation des Attributs

- **`setAttribute(name, value)`** : Définit une valeur pour un attribut.
- **`getAttribute(name)`** : Obtient la valeur d'un attribut.

### Modification du Style

- **`element.style.propertyName`** : Définit des propriétés CSS directement sur les éléments.

## Gestion des Événements

Les événements sont des actions que l'utilisateur ou le navigateur peut déclencher, comme des clics de souris ou des entrées de texte. Vous pouvez ajouter des écouteurs d'événements aux éléments avec **`addEventListener(type, listener)`**, qui exécute une fonction spécifique lorsque l'événement se produit.

### Événements Courants

- **`click`**
  - **Déclenché** : Lorsqu'un utilisateur clique sur un élément.
  - **Exemple** :
    ```javascript
    document.getElementById("monBouton").addEventListener("click", function() {
      alert("Le bouton a été cliqué !");
    });
    ```

- **`input`**
  - **Déclenché** : Lorsqu'une entrée est effectuée dans un élément de formulaire (champ de texte, zone de saisie, etc.).
  - **Exemple** :
    ```javascript
    document.getElementById("monChampTexte").addEventListener("input", function() {
      console.log("Texte saisi : " + this.value);
    });
    ```

- **`change`**
  - **Déclenché** : Lorsqu'une valeur d'un élément de formulaire (comme une case à cocher, un menu déroulant, etc.) est modifiée.
  - **Exemple** :
    ```javascript
    document.getElementById("monSelect").addEventListener("change", function() {
      console.log("Option sélectionnée : " + this.value);
    });
    ```

- **`submit`**
  - **Déclenché** : Lorsqu'un formulaire est soumis.
  - **Exemple** :
    ```javascript
    document.getElementById("monFormulaire").addEventListener("submit", function(event) {
      event.preventDefault(); // Empêche la soumission réelle du formulaire
      console.log("Formulaire soumis !");
    });
    ```

- **`keydown`**
  - **Déclenché** : Lorsqu'une touche du clavier est enfoncée.
  - **Exemple** :
    ```javascript
    document.addEventListener("keydown", function(event) {
      console.log("Touche enfoncée : " + event.key);
    });
    ```

- **`keyup`**
  - **Déclenché** : Lorsqu'une touche du clavier est relâchée.
  - **Exemple** :
    ```javascript
    document.addEventListener("keyup", function(event) {
      console.log("Touche relâchée : " + event.key);
    });
    ```

- **`mouseover`**
  - **Déclenché** : Lorsqu'un utilisateur passe la souris au-dessus d'un élément.
  - **Exemple** :
    ```javascript
    document.getElementById("monElement").addEventListener("mouseover", function() {
      this.style.backgroundColor = "yellow";
    });
    ```

- **`mouseout`**
  - **Déclenché** : Lorsqu'un utilisateur déplace la souris hors d'un élément.
  - **Exemple** :
    ```javascript
    document.getElementById("monElement").addEventListener("mouseout", function() {
      this.style.backgroundColor = "";
    });
    ```

- **`focus`**
  - **Déclenché** : Lorsqu'un élément (comme un champ de texte) reçoit le focus.
  - **Exemple** :
    ```javascript
    document.getElementById("monChampTexte").addEventListener("focus", function() {
      this.style.borderColor = "blue";
    });
    ```

- **`blur`**
  - **Déclenché** : Lorsqu'un élément (comme un champ de texte) perd le focus.
  - **Exemple** :
    ```javascript
    document.getElementById("monChampTexte").addEventListener("blur", function() {
      this.style.borderColor = "";
    });
    ```

- **`load`**
  - **Déclenché** : Lorsque la page ou un élément (comme une image) a fini de se charger.
  - **Exemple** :
    ```javascript
    window.addEventListener("load", function() {
      console.log("La page est complètement chargée !");
    });
    ```

- **`resize`**
  - **Déclenché** : Lorsqu'une fenêtre de navigateur est redimensionnée.
  - **Exemple** :
    ```javascript
    window.addEventListener("resize", function() {
      console.log("La fenêtre a été redimensionnée !");
    });
    ```

- **`scroll`**
  - **Déclenché** : Lorsqu'un utilisateur fait défiler une page ou un élément.
  - **Exemple** :
    ```javascript
    window.addEventListener("scroll", function() {
      console.log("Défilement détecté !");
    });
    ```

- **`contextmenu`**
  - **Déclenché** : Lorsqu'un utilisateur fait un clic droit pour ouvrir le menu contextuel.
  - **Exemple** :
    ```javascript
    document.getElementById("monElement").addEventListener("contextmenu", function(event) {
      event.preventDefault(); // Empêche le menu contextuel par défaut
      console.log("Menu contextuel ouvert !");
    });
    ```
## Création et Suppression d'Éléments

### Création d'Éléments

- **`createElement(tagName)`** : Crée un nouvel élément HTML.
- **`createTextNode(text)`** : Crée un nœud de texte.

### Ajout au Document

- **`appendChild(node)`** : Ajoute un nœud comme enfant du nœud actuel.
- **`insertBefore(newNode, existingNode)`** : Insère un nouveau nœud avant un nœud existant.

### Suppression d'Éléments

- **`removeChild(node)`** : Supprime un nœud enfant d'un élément.
- **`remove()`** : Supprime l'élément actuel dans les navigateurs les plus récents.

## Navigation dans le DOM

Dans le DOM, tout est un nœud. La racine de cette structure est le nœud `document`. Les nœuds d'éléments correspondent aux balises HTML, les nœuds d'attributs contiennent les propriétés des éléments, et les nœuds de texte représentent le texte à l'intérieur des éléments.

### Accès aux Nœuds

- **`parentNode`** : Accède au parent d'un nœud.
- **`childNodes`** : Obtient tous les enfants d'un nœud.
- **`firstChild`** : Accède au premier enfant d'un nœud.
- **`lastChild`** : Accède au dernier enfant d'un nœud.
- **`nextSibling`** : Accède au nœud frère suivant.
- **`previousSibling`** : Accède au nœud frère précédent.

# Affichage de Données en JavaScript

- **Accéder et modifier le contenu HTML**  
  Utilisez `document.getElementById("id")` pour accéder à un élément HTML par son identifiant.  
  Exemple :
  ```javascript
  document.getElementById("monElement").innerHTML = "Nouveau contenu";
  ```

- **Écrire dans le document HTML**  
  `document.write()` peut être utilisé pour écrire directement dans le document HTML.  
  Exemple :
  ```javascript
  document.write("Texte affiché sur la page");
  ```
  *Remarque : à éviter dans les documents HTML chargés, car cela efface le HTML existant.*

- **Afficher une boîte de pop-up**  
  Utilisez `window.alert()` pour afficher une boîte de dialogue. Le mot-clé `window` est optionnel.  
  Exemple :
  ```javascript
  alert("Message de pop-up");
  ```

- **Déboguer dans la console**  
  `console.log()` affiche des messages dans la console du navigateur pour le débogage.  
  Exemple :
  ```javascript
  console.log("Message de débogage");
  ```

- **Imprimer le contenu de la fenêtre**  
  Utilisez `window.print()` pour ouvrir la boîte de dialogue d'impression du navigateur.  
  Exemple :
  ```javascript
  window.print();
  ```
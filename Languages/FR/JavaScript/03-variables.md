# Déclaration des Variables en JavaScript

Il existe plusieurs façons de déclarer des variables en JavaScript, chacune ayant des caractéristiques distinctes :

- **`var`**  
  Les variables déclarées avec `var` ont une portée globale ou de fonction, ce qui signifie qu'elles sont accessibles depuis n'importe où dans le programme ou la fonction où elles sont définies. Elles peuvent être redéclarées et n'ont pas besoin d'être initialisées avant utilisation.  
  *Remarque :* Utilisez `var` uniquement pour les navigateurs plus anciens.

  Exemple :
  ```javascript
  var x = 10;
  var x = 20; // Réassignable
  ```

- **`let`**  
  `let` fournit une portée de bloc, ce qui signifie que les variables sont accessibles uniquement dans le bloc de code où elles sont déclarées. Elles ne peuvent pas être redéclarées dans le même bloc et doivent être déclarées avant d'être utilisées.

  Exemple :
  ```javascript
  let y = 30;
  // let y = 40; // Erreur : Variable déjà déclarée
  ```

- **`const`**  
  `const` est utilisé pour déclarer des variables dont la valeur ne doit pas changer. Les variables déclarées avec `const` ont une portée de bloc, ne peuvent pas être redéclarées dans le même bloc et ne peuvent pas être réassignées après leur déclaration.

  Exemple :
  ```javascript
  const z = 50;
  // z = 60; // Erreur : Assignment to constant variable
  ```

- **Déclaration Implicite**  
  Il est possible de déclarer une variable sans utiliser `var`, `let`, ou `const`. Cependant, cela crée une variable globale, ce qui est généralement une mauvaise pratique. Il est recommandé de toujours déclarer les variables explicitement.

  Exemple :
  ```javascript
  x = 70; // Déclaration implicite (variable globale)
  ```
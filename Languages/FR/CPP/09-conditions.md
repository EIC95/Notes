# Structures de Contrôle en C++

## Instructions Conditionnelles

- **`if`**  
  Exécute un bloc de code si une condition est vraie.
  ```cpp
  int x = 10;
  if (x > 5) {
      std::cout << "x est supérieur à 5";
  }
  ```

- **`if...else`**  
  Exécute un bloc de code si une condition est vraie, sinon exécute un autre bloc de code.
  ```cpp
  int x = 4;
  if (x > 5) {
      std::cout << "x est supérieur à 5";
  } else {
      std::cout << "x est inférieur ou égal à 5";
  }
  ```

- **`else if`**  
  Permet de tester plusieurs conditions en chaîne, après un `if` initial.
  ```cpp
  int x = 7;
  if (x > 10) {
      std::cout << "x est supérieur à 10";
  } else if (x > 5) {
      std::cout << "x est supérieur à 5 mais inférieur ou égal à 10";
  } else {
      std::cout << "x est inférieur ou égal à 5";
  }
  ```

- **Opérateur Ternaire**  
  `condition ? expr1 : expr2;`  
  Évalue `expr1` si la condition est vraie, sinon évalue `expr2`.
  ```cpp
  int x = 8;
  std::string result = (x > 5) ? "x est supérieur à 5" : "x est inférieur ou égal à 5";
  std::cout << result;
  ```

- **`switch case`**  
  Permet de sélectionner parmi plusieurs blocs de code en fonction de la valeur d'une expression.
  ```cpp
  int day = 3;
  switch (day) {
      case 1:
          std::cout << "Lundi";
          break;
      case 2:
          std::cout << "Mardi";
          break;
      case 3:
          std::cout << "Mercredi";
          break;
      default:
          std::cout << "Jour inconnu";
  }
  ```
```
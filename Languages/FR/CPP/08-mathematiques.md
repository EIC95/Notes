# Fonctions Mathématiques en C++

C++ possède de nombreuses fonctions qui vous permettent d'effectuer des tâches mathématiques sur des nombres avec la bibliothèque `cmath`.

- **`cos(x)`**  
  Retourne le cosinus de `x` (en radians).
  ```cpp
  #include <cmath>
  #include <iostream>

  int main() {
      double result = cos(3.14);
      std::cout << result;
      return 0;
  }
  ```

- **`tan(x)`**  
  Retourne la tangente de `x` (en radians).
  ```cpp
  #include <cmath>
  #include <iostream>

  int main() {
      double result = tan(3.14);
      std::cout << result;
      return 0;
  }
  ```

- **`log(x)`**  
  Retourne le logarithme naturel (base e) de `x`.
  ```cpp
  #include <cmath>
  #include <iostream>

  int main() {
      double result = log(10);
      std::cout << result;
      return 0;
  }
  ```

- **`exp(x)`**  
  Retourne `e` élevé à la puissance `x`.
  ```cpp
  #include <cmath>
  #include <iostream>

  int main() {
      double result = exp(2);
      std::cout << result;
      return 0;
  }
  ```

- **`ceil(x)`**  
  Retourne le plus petit entier supérieur ou égal à `x`.
  ```cpp
  #include <cmath>
  #include <iostream>

  int main() {
      double result = ceil(4.3);
      std::cout << result;
      return 0;
  }
  ```

- **`floor(x)`**  
  Retourne le plus grand entier inférieur ou égal à `x`.
  ```cpp
  #include <cmath>
  #include <iostream>

  int main() {
      double result = floor(4.7);
      std::cout << result;
      return 0;
  }
  ```
```
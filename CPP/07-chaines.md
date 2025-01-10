# Manipulation des Chaînes de Caractères en C++

Les chaînes de caractères en C++ peuvent être manipulées de manière simple et sécurisée en utilisant la classe `std::string` de la bibliothèque standard. Voici quelques méthodes et opérateurs courants pour manipuler les chaînes.

## Méthodes de `std::string`

- **`size()` ou `length()`**  
  Retourne la longueur de la chaîne.
  ```cpp
  std::string str = "Hello";
  std::cout << str.size(); // Affiche 5
  ```

- **`empty()`**  
  Vérifie si la chaîne est vide.
  ```cpp
  std::string str = "";
  if (str.empty()) {
      std::cout << "La chaîne est vide.";
  }
  ```

- **`clear()`**  
  Efface le contenu de la chaîne.
  ```cpp
  std::string str = "Hello";
  str.clear();
  std::cout << str; // Affiche une chaîne vide
  ```

- **`operator[]`**  
  Accède à un caractère à une position spécifiée.
  ```cpp
  std::string str = "Hello";
  std::cout << str[1]; // Affiche 'e'
  ```

- **`find(sub)`**  
  Retourne la position de la première occurrence de `sub`.
  ```cpp
  std::string str = "Hello World";
  size_t pos = str.find("World");
  std::cout << pos; // Affiche 6
  ```

- **`replace(pos, len, str)`**  
  Remplace une portion de la chaîne par `str`.
  ```cpp
  std::string str = "Hello World";
  str.replace(6, 5, "C++");
  std::cout << str; // Affiche "Hello C++"
  ```

- **`append(str)`**  
  Ajoute `str` à la fin de la chaîne.
  ```cpp
  std::string str = "Hello";
  str.append(" World");
  std::cout << str; // Affiche "Hello World"
  ```

## Caractères Spéciaux

- **`\n`** : Nouvelle ligne
- **`\t`** : Tabulation horizontale
- **`\\`** : Barre oblique inverse
- **`\"`** : Guillemets doubles
- **`\'`** : Apostrophe ou guillemets simples
- **`\r`** : Retour chariot
- **`\b`** : Retour arrière
- **`\f`** : Saut de page
```





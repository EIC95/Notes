# JSON en PHP

JSON (JavaScript Object Notation) est un format léger de stockage et d'échange de données. Basé sur du texte, JSON est facilement transmissible entre le client et le serveur et est supporté par de nombreux langages de programmation.

## Fonctions JSON en PHP

- **json_encode()** : Encode une valeur PHP au format JSON.
  ```php
  <?php
  $data = array("nom" => "Alice", "age" => 25);
  $json = json_encode($data);
  echo $json; // {"nom":"Alice","age":25}
  ?>
  ```

- **json_decode()** : Décode une chaîne JSON en un objet PHP ou un tableau associatif.
  ```php
  <?php
  $json = '{"nom":"Alice","age":25}';
  $data = json_decode($json, true); // true pour obtenir un tableau associatif
  echo $data["nom"]; // Alice
  ?>
  ```
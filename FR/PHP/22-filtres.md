# Filtres PHP

Les filtres PHP sont utilisés pour valider et nettoyer les entrées externes telles que les saisies utilisateur, les cookies, et les données des services web. Cette validation est cruciale pour la sécurité et l'intégrité de votre application. La fonction `filter_var()` permet de valider, nettoyer, et filtrer une variable en utilisant un filtre spécifié.

## Fonctionnalités des filtres

- **FILTER_VALIDATE_INT** : Valide si la valeur est un entier.
  ```php
  $value = "123";
  if (filter_var($value, FILTER_VALIDATE_INT) !== false) {
      echo "Valide.";
  } else {
      echo "Invalide.";
  }
  ```

- **FILTER_VALIDATE_EMAIL** : Valide si la valeur est une adresse email.
  ```php
  $email = "example@example.com";
  if (filter_var($email, FILTER_VALIDATE_EMAIL) !== false) {
      echo "Email valide.";
  } else {
      echo "Email invalide.";
  }
  ```

- **FILTER_VALIDATE_URL** : Valide si la valeur est une URL.
  ```php
  $url = "https://www.example.com";
  if (filter_var($url, FILTER_VALIDATE_URL) !== false) {
      echo "URL valide.";
  } else {
      echo "URL invalide.";
  }
  ```

- **FILTER_VALIDATE_IP** : Valide si la valeur est une adresse IP.
  ```php
  $ip = "192.168.1.1";
  if (filter_var($ip, FILTER_VALIDATE_IP) !== false) {
      echo "IP valide.";
  } else {
      echo "IP invalide.";
  }
  ```

## Nettoyage des données

- **FILTER_SANITIZE_STRING** : Nettoie une chaîne de caractères en supprimant les balises HTML et les caractères spéciaux.
  ```php
  $string = "<script>alert('Hello');</script>";
  $cleaned = filter_var($string, FILTER_SANITIZE_STRING);
  echo $cleaned;
  ```

- **FILTER_SANITIZE_EMAIL** : Nettoie une adresse email en supprimant les caractères illégaux.
  ```php
  $email = "user@@example.com";
  $cleaned = filter_var($email, FILTER_SANITIZE_EMAIL);
  echo $cleaned;
  ```

- **FILTER_SANITIZE_URL** : Nettoie une URL en supprimant les caractères illégaux.
  ```php
  $url = "http://example.com/?query=<script>alert('XSS');</script>";
  $cleaned = filter_var($url, FILTER_SANITIZE_URL);
  echo $cleaned;
  ```

- **FILTER_SANITIZE_NUMBER_INT** : Nettoie pour obtenir un entier en supprimant les caractères non numériques.
  ```php
  $number = "123abc456";
  $cleaned = filter_var($number, FILTER_SANITIZE_NUMBER_INT);
  echo $cleaned;
  ```

- **FILTER_SANITIZE_NUMBER_FLOAT** : Nettoie pour obtenir un nombre à virgule flottante en supprimant les caractères non numériques.
  ```php
  $float = "123.45abc";
  $cleaned = filter_var($float, FILTER_SANITIZE_NUMBER_FLOAT, FILTER_FLAG_ALLOW_FRACTION);
  echo $cleaned;
  ```

- **FILTER_SANITIZE_SPECIAL_CHARS** : Échappe les caractères spéciaux pour éviter les injections HTML et XSS.
  ```php
  $string = "<div>Hello</div>";
  $cleaned = filter_var($string, FILTER_SANITIZE_SPECIAL_CHARS);
  echo $cleaned;
  ```
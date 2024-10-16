# Gestion des Fichiers en Java

Java offre plusieurs méthodes pour créer, lire, mettre à jour et supprimer des fichiers. La classe `File` du package `java.io` fournit des outils pour interagir avec les fichiers et les répertoires. Voici un aperçu des principales méthodes et classes utilisées pour la gestion des fichiers :

## Création de Fichiers et Répertoires

- **Créer un Nouveau Fichier :**
  ```java
  File file = new File("nom_fichier.txt");
  boolean success = file.createNewFile();
  ```
  - **`createNewFile()`** : Crée un nouveau fichier vide. Retourne `true` si le fichier a été créé avec succès, `false` sinon.

- **Créer un Nouveau Répertoire :**
  ```java
  File directory = new File("nom_repertoire");
  boolean success = directory.mkdir();
  ```
  - **`mkdir()`** : Crée un nouveau répertoire. Retourne `true` si le répertoire a été créé avec succès, `false` sinon.

## Lecture d'un Fichier

- **Utiliser `FileReader` pour lire un fichier :**
  ```java
  File file = new File("nom_fichier.txt");
  FileReader fileReader = new FileReader(file);
  ```

- **Utiliser `BufferedReader` pour une lecture plus efficace :**
  ```java
  BufferedReader reader = new BufferedReader(new FileReader(file));
  String line = reader.readLine();  // Lit une ligne de texte
  reader.close();  // Ferme le fichier et libère les ressources
  ```

## Écriture dans un Fichier

- **Utiliser `FileWriter` pour écrire dans un fichier :**
  ```java
  FileWriter fileWriter = new FileWriter("nom_fichier.txt");
  ```

- **Utiliser `BufferedWriter` pour une écriture plus efficace :**
  ```java
  BufferedWriter writer = new BufferedWriter(new FileWriter("nom_fichier.txt"));
  writer.write("Contenu à écrire dans le fichier");
  writer.close();  // Ferme le fichier et libère les ressources
  ```

## Suppression d'un Fichier

- **Supprimer un Fichier :**
  ```java
  File file = new File("nom_fichier.txt");
  boolean success = file.delete();
  ```
  - **`delete()`** : Supprime le fichier spécifié. Retourne `true` si le fichier a été supprimé avec succès, `false` sinon.

## Résumé des Méthodes

- **Création de Fichier :**
  - `createNewFile()`
  - `mkdir()`

- **Lecture d'un Fichier :**
  - `new FileReader(fichier)`
  - `BufferedReader(new FileReader(fichier))`
  - `reader.readLine()`
  - `reader.close()`

- **Écriture dans un Fichier :**
  - `new FileWriter(fichier)`
  - `BufferedWriter(new FileWriter(fichier))`
  - `writer.write(contenu)`
  - `writer.close()`

- **Suppression d'un Fichier :**
  - `delete()`

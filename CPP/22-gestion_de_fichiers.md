# Gestion des Fichiers en C++

La bibliothèque `<fstream>` de C++ permet de créer, lire et écrire des fichiers. Elle fournit trois classes principales pour travailler avec des fichiers : `ofstream`, `ifstream`, et `fstream`.

## Classes de la Bibliothèque `<fstream>`

- **`ofstream`** : Utilisée pour créer et écrire dans des fichiers.
- **`ifstream`** : Utilisée pour lire à partir de fichiers.
- **`fstream`** : Une combinaison de `ofstream` et `ifstream`, permettant de créer, lire et écrire dans des fichiers.

## Création et Écriture dans un Fichier

Pour créer un fichier et y écrire des données, vous pouvez utiliser `ofstream` ou `fstream`. Voici un exemple de création d'un fichier et d'écriture dans celui-ci :

### Exemple d'Écriture

```cpp
#include <iostream>
#include <fstream> // Inclusion de la bibliothèque fstream
using namespace std;

int main() {
    ofstream outFile("example.txt"); // Création d'un fichier nommé example.txt

    if (outFile.is_open()) { // Vérification si le fichier est ouvert avec succès
        outFile << "Hello, World!" << endl; // Écriture dans le fichier
        outFile.close(); // Fermeture du fichier
        cout << "Écriture terminée et fichier fermé." << endl;
    } else {
        cout << "Impossible d'ouvrir le fichier." << endl;
    }

    return 0;
}
```

## Lecture d'un Fichier

Pour lire le contenu d'un fichier, utilisez `ifstream` ou `fstream`. Vous pouvez lire le fichier ligne par ligne en utilisant la fonction `getline()`.

### Exemple de Lecture

```cpp
#include <iostream>
#include <fstream> // Inclusion de la bibliothèque fstream
#include <string>  // Inclusion de la bibliothèque string pour getline
using namespace std;

int main() {
    ifstream inFile("example.txt"); // Ouverture du fichier example.txt pour la lecture
    string line;

    if (inFile.is_open()) { // Vérification si le fichier est ouvert avec succès
        while (getline(inFile, line)) { // Lecture ligne par ligne
            cout << line << endl; // Affichage de la ligne lue
        }
        inFile.close(); // Fermeture du fichier
    } else {
        cout << "Impossible d'ouvrir le fichier." << endl;
    }

    return 0;
}
```
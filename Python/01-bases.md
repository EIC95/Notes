# Les Bases de Python

## Les Commentaires

Les commentaires en Python sont utilisés pour ajouter des explications ou des annotations dans le code. Ils ne sont pas exécutés par l'interpréteur Python. Ils sont utiles pour documenter le code et le rendre plus lisible.

- **Commentaire sur une seule ligne** : On utilise le symbole `#` pour écrire un commentaire sur une seule ligne.

    ```python
    # Ceci est un commentaire sur une seule ligne
    print("Hello, World!")  # Un commentaire à côté de l'instruction
    ```

- **Commentaire sur plusieurs lignes** : Python ne dispose pas d'une syntaxe spécifique pour les commentaires sur plusieurs lignes, mais on peut utiliser des guillemets triples (`"""`) pour simuler des blocs de commentaires. Bien que ces guillemets créent techniquement une chaîne de caractères, ils sont souvent utilisés pour documenter du code.

    ```python
    """
    Ceci est un commentaire
    sur plusieurs lignes
    """
    print("Bonjour tout le monde!")
    ```

## L'Indentation

L'indentation est très importante en Python. Contrairement à d'autres langages qui utilisent des accolades `{}` pour délimiter les blocs de code, Python utilise l'indentation pour structurer le code. Une mauvaise indentation entraînera une erreur de syntaxe.

- **Indentation correcte** : En général, on utilise 4 espaces pour l'indentation, mais il est aussi possible d'utiliser des tabulations. Toutefois, il est fortement recommandé d'utiliser les espaces pour garantir la cohérence du code.

    ```python
    if True:
        print("Condition est vraie")
        print("Toujours dans le bloc conditionnel")
    ```

- **Indentation incorrecte** : Un mauvais alignement ou mélange des tabulations et des espaces entraînera une erreur.

    ```python
     if True:
      print("Erreur possible avec l'indentation")
    ```

# Fonctions en C++

## Déclaration

Une fonction en C++ est définie par un type de retour, un nom, une liste de paramètres (facultative), et un corps de fonction. Pour appeler une fonction, on utilise son nom suivi de parenthèses contenant les arguments.

```cpp
int add(int a, int b); // Déclaration
```

## Définition

La définition inclut le corps de la fonction, c'est-à-dire le code à exécuter.

```cpp
int add(int a, int b) {
    return a + b;
}
```

## Appel

On appelle la fonction en utilisant son nom et les arguments appropriés.

```cpp
int result = add(3, 4); // Appel
```

## Retour de Valeur

Une fonction peut retourner une valeur à l'aide de l'instruction `return`.

```cpp
int multiply(int a, int b) {
    return a * b;
}
```

## Fonction `void`

Une fonction qui ne retourne pas de valeur a un type de retour `void`.

```cpp
void printMessage() {
    std::cout << "Hello, World!";
}
```

## Surcharge de Fonction

C++ permet la surcharge de fonctions, c'est-à-dire la définition de plusieurs fonctions ayant le même nom mais des listes de paramètres différentes.

```cpp
int add(int a, int b) {
    return a + b;
}

double add(double a, double b) {
    return a + b;
}
```



# Gestion des Threads en Java

Un thread en Java est une unité d'exécution légère au sein d'un programme, permettant l'exécution simultanée de plusieurs tâches. Chaque thread fonctionne indépendamment et peut exécuter son propre code. Les threads partagent le même espace mémoire, ce qui peut entraîner des problèmes de concurrence si plusieurs threads accèdent aux mêmes variables.

## Création de Threads

Il existe deux principales méthodes pour créer des threads en Java :

### 1. **En héritant de la classe `Thread`**

- **Description** : Créez une classe qui hérite de la classe `Thread` et surchargez la méthode `run()`. La méthode `run()` contient le code que le thread exécutera.
- **Exécution** : Créez une instance de la classe dérivée et appelez la méthode `start()` pour démarrer le thread.

```java
class MyThread extends Thread {
    public void run() {
        // Code à exécuter par le thread
        System.out.println("Thread en cours d'exécution.");
    }
}

public class Main {
    public static void main(String[] args) {
        MyThread thread = new MyThread();
        thread.start(); // Démarre le thread
    }
}
```

### 2. **En utilisant l'interface `Runnable`**

- **Description** : Créez une classe qui implémente l'interface `Runnable`. L'interface `Runnable` définit une seule méthode, `run()`, où le code du thread sera placé.
- **Exécution** : Passez une instance de la classe implémentant `Runnable` au constructeur de la classe `Thread`, puis appelez la méthode `start()` du thread.

```java
class MyRunnable implements Runnable {
    public void run() {
        // Code à exécuter par le thread
        System.out.println("Thread en cours d'exécution.");
    }
}

public class Main {
    public static void main(String[] args) {
        Thread thread = new Thread(new MyRunnable());
        thread.start(); // Démarre le thread
    }
}
```

### Différences Entre Étendre `Thread` et Implémenter `Runnable`

- **Extendre `Thread`** : Vous ne pouvez pas étendre une autre classe en même temps, ce qui limite la flexibilité de l'héritage.
- **Implémenter `Runnable`** : Permet d'étendre une autre classe tout en créant des threads, offrant ainsi plus de flexibilité dans la conception de votre classe.

## Gestion des Problèmes de Concurrence

Les threads peuvent accéder et modifier les mêmes variables de manière concurrente, ce qui peut entraîner des résultats imprévisibles. Pour éviter les problèmes de concurrence :

- **Minimiser le Partage** : Réduisez le partage des attributs entre les threads autant que possible.
- **Utiliser `isAlive()`** : Vérifiez si un thread est encore en cours d'exécution avant d'accéder à des attributs que ce thread pourrait modifier.

```java
if (thread.isAlive()) {
    // Attendre que le thread se termine
}
```

Les problèmes de concurrence peuvent être complexes à résoudre et nécessitent souvent des mécanismes de synchronisation pour garantir que les threads n'interfèrent pas les uns avec les autres de manière incorrecte.
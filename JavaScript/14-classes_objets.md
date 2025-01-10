# Objets et Classes en JavaScript

## Objets

Les objets en JavaScript sont des collections de paires clé-valeur. Ils permettent de stocker diverses données et fonctionnalités.

### Création et accès aux propriétés

Vous pouvez créer un objet en utilisant des accolades `{}` et accéder à ses propriétés via la **notation par points** ou **crochets**.

**Exemple :**

```javascript
let personne = {
    nom: "Alice",
    age: 25,
    saluer: function() {
        return "Bonjour, je m'appelle " + this.nom;
    }
};

// Accès aux propriétés
console.log(personne.nom); // "Alice"
console.log(personne['age']); // 25

// Appel d'une méthode
console.log(personne.saluer()); // "Bonjour, je m'appelle Alice"
```

### Ajout ou modification de propriétés

Les propriétés peuvent être ajoutées ou modifiées après la création de l'objet.

**Exemple :**

```javascript
personne.profession = "Développeuse";
personne.age = 26;
console.log(personne.profession); // "Développeuse"
console.log(personne.age); // 26
```

### Le mot-clé `this`

Le mot-clé `this` fait référence à l'objet courant dans une méthode. Il permet d'accéder aux propriétés et méthodes de l'objet depuis l'intérieur de celui-ci.

**Exemple :**

```javascript
let voiture = {
    marque: "Toyota",
    modele: "Corolla",
    description: function() {
        return this.marque + " " + this.modele;
    }
};

console.log(voiture.description()); // "Toyota Corolla"
```

## Classes

Les **classes** en JavaScript sont des modèles pour créer des objets avec des propriétés et des méthodes définies. Elles facilitent la création de plusieurs instances similaires.

### Définir une classe

Utilisez le mot-clé `class` pour définir une classe, et le mot-clé `constructor` pour initialiser les propriétés.

**Exemple :**

```javascript
class Animal {
    constructor(nom, type) {
        this.nom = nom;
        this.type = type;
    }

    // Méthode
    decrire() {
        return this.nom + " est un " + this.type;
    }
}

// Création d'une instance
let chien = new Animal("Rex", "chien");
console.log(chien.decrire()); // "Rex est un chien"
```

### Héritage avec `extends`

Une classe peut hériter d'une autre classe en utilisant le mot-clé `extends`. La méthode `super()` est utilisée pour appeler le constructeur de la classe parente.

**Exemple :**

```javascript
class Chien extends Animal {
    constructor(nom, race) {
        super(nom, "chien");
        this.race = race;
    }

    aboyer() {
        return this.nom + " aboie !";
    }
}

let berger = new Chien("Max", "Berger Allemand");
console.log(berger.decrire()); // "Max est un chien"
console.log(berger.aboyer()); // "Max aboie !"
```

### Méthodes statiques

Les méthodes statiques sont définies avec le mot-clé `static` et appartiennent à la classe elle-même, et non aux instances de cette classe.

**Exemple :**

```javascript
class Mathematiques {
    static additionner(a, b) {
        return a + b;
    }
}

console.log(Mathematiques.additionner(5, 3)); // 8
```
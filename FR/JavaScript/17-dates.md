# Gestion des dates et heures en JavaScript

En JavaScript, l'objet `Date` permet de manipuler les dates et les heures. Vous pouvez obtenir la date et l'heure actuelles, créer des dates spécifiques et extraire ou modifier les composants d'une date.

## Création d'une date

### Date actuelle
Pour obtenir la date et l'heure actuelles, il suffit de créer un objet `Date` sans paramètre.

```javascript
let dateActuelle = new Date();
console.log(dateActuelle);
```

### Date spécifique
Vous pouvez aussi créer une date spécifique en passant plusieurs paramètres :
- Année
- Mois (commençant à 0, donc 0 = janvier, 1 = février, etc.)
- Jour
- Heure
- Minute
- Seconde
- Milliseconde

```javascript
let dateSpecifique = new Date(2023, 8, 18, 14, 30, 0);
console.log(dateSpecifique);
```

### Méthodes `get` pour extraire des parties d'une date

- `.getFullYear()`: retourne l'année
- `.getMonth()`: retourne le mois (0-11)
- `.getDate()`: retourne le jour du mois (1-31)
- `.getHours()`: retourne l'heure (0-23)
- `.getMinutes()`: retourne les minutes (0-59)
- `.getSeconds()`: retourne les secondes (0-59)

```javascript
let annee = dateActuelle.getFullYear();
let mois = dateActuelle.getMonth();
let jour = dateActuelle.getDate();
console.log(`Année : ${annee}, Mois : ${mois + 1}, Jour : ${jour}`);
```

### Méthodes `set` pour modifier les composants d'une date

Vous pouvez modifier les composants d'une date existante avec les méthodes `set`.

- `.setFullYear(année)`
- `.setMonth(mois)`
- `.setDate(jour)`
- `.setHours(heures)`
- `.setMinutes(minutes)`
- `.setSeconds(secondes)`

```javascript
dateActuelle.setFullYear(2025);
dateActuelle.setMonth(5); // juin
console.log(dateActuelle);
```

Ces méthodes permettent de manipuler facilement les dates en fonction de vos besoins, que ce soit pour afficher l'heure actuelle ou planifier des événements à des dates spécifiques.
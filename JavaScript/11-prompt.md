# Fonction `prompt()` en JavaScript

La fonction `prompt()` affiche une boîte de dialogue modale qui demande à l'utilisateur de saisir une entrée. Elle retourne la valeur saisie par l'utilisateur sous forme de chaîne de caractères. Si l'utilisateur annule la saisie, `prompt()` retourne `null`.

**Syntaxe :**

```javascript
let valeur = prompt(message, valeurParDéfaut);
```

- **`message`** : (Optionnel) Texte affiché dans la boîte de dialogue pour inviter l'utilisateur à entrer une valeur.
- **`valeurParDéfaut`** : (Optionnel) Valeur initiale affichée dans le champ de saisie.

**Exemple :**

```javascript
let nom = prompt("Quel est votre nom ?");
console.log("Bonjour, " + nom + "!");
```

Dans cet exemple, une boîte de dialogue demandera à l'utilisateur d'entrer son nom. Le nom saisi sera ensuite affiché dans la console.

**Remarque :**
- `prompt()` est principalement utilisé dans des environnements de navigation web. Il n'est pas recommandé pour les applications web modernes en raison de son aspect modale intrusif et de son interface utilisateur limitée.
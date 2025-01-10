# Utilisation de l'Opérateur LIKE en SQL

## Introduction

L'opérateur `LIKE` est utilisé dans une clause `WHERE` pour rechercher des motifs spécifiques dans une colonne. Il permet d'effectuer des recherches basées sur des modèles, en utilisant des caractères génériques pour représenter des groupes de caractères.

## Caractères Généraux avec LIKE

### Caractères Généraux

- **`%`** : Représente zéro, un ou plusieurs caractères. Utilisé pour rechercher une séquence de caractères inconnus.
- **`_`** : Représente un seul caractère. Utilisé pour rechercher un caractère spécifique à une position donnée.

### Autres Caractères Généraux

Les caractères génériques peuvent varier selon les systèmes de bases de données :

- **`[]`** : Représente n'importe quel caractère unique parmi ceux spécifiés entre crochets.
- **`^`** : Représente n'importe quel caractère qui ne fait pas partie des caractères spécifiés entre crochets.
- **`-`** : Représente n'importe quel caractère unique dans la plage spécifiée entre crochets.
- **`{}`** : Représente n'importe quel caractère échappé (principalement utilisé dans Oracle).
- **`*`** : Représente zéro ou plusieurs caractères (non pris en charge dans PostgreSQL et MySQL).
- **`?`** : Représente un seul caractère (non pris en charge dans certaines bases de données).
- **`!`** : Représente n'importe quel caractère qui n'est pas parmi ceux spécifiés entre crochets.
- **`#`** : Représente n'importe quel caractère numérique (principalement utilisé dans Microsoft SQL Server).

### Syntaxe

```sql
SELECT colonne
FROM table
WHERE colonne LIKE motif;
```

### Exemples

1. **Rechercher des noms qui commencent par "A"** :

   ```sql
   SELECT nom
   FROM clients
   WHERE nom LIKE 'A%';
   ```

2. **Rechercher des noms qui contiennent "an"** :

   ```sql
   SELECT nom
   FROM clients
   WHERE nom LIKE '%an%';
   ```

3. **Rechercher des noms qui commencent par "A" et ont exactement 5 caractères** :

   ```sql
   SELECT nom
   FROM clients
   WHERE nom LIKE 'A____';
   ```

4. **Rechercher des numéros de téléphone qui commencent par "123" suivis de 4 chiffres** :

   ```sql
   SELECT numero_telephone
   FROM contacts
   WHERE numero_telephone LIKE '123####';
   ```

5. **Rechercher des noms contenant une lettre spécifique parmi plusieurs options (ex. "a", "e" ou "i")** :

   ```sql
   SELECT nom
   FROM clients
   WHERE nom LIKE '%[aei]%';
   ```
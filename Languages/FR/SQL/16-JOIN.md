# Clauses JOIN en SQL

Les clauses `JOIN` sont utilisées pour combiner des lignes de deux ou plusieurs tables basées sur une colonne commune. Voici les principaux types de `JOIN` en SQL :

## Types de JOIN

### INNER JOIN

L'`INNER JOIN` renvoie les enregistrements dont les valeurs correspondent dans les deux tables impliquées. Il ne retourne que les lignes ayant des correspondances dans les deux tables.

#### Syntaxe

```sql
SELECT colonnes
FROM table1
INNER JOIN table2
ON table1.colonne_commune = table2.colonne_commune;
```

#### Exemple

```sql
SELECT clients.nom, commandes.date_commande
FROM clients
INNER JOIN commandes
ON clients.id_client = commandes.id_client;
```

### LEFT JOIN (ou LEFT OUTER JOIN)

Le `LEFT JOIN` renvoie tous les enregistrements de la table de gauche et les enregistrements correspondants de la table de droite. Les enregistrements de la table de gauche qui n'ont pas de correspondance dans la table de droite auront des valeurs NULL pour les colonnes de la table de droite.

#### Syntaxe

```sql
SELECT colonnes
FROM table1
LEFT JOIN table2
ON table1.colonne_commune = table2.colonne_commune;
```

#### Exemple

```sql
SELECT clients.nom, commandes.date_commande
FROM clients
LEFT JOIN commandes
ON clients.id_client = commandes.id_client;
```

### RIGHT JOIN (ou RIGHT OUTER JOIN)

Le `RIGHT JOIN` renvoie tous les enregistrements de la table de droite et les enregistrements correspondants de la table de gauche. Les enregistrements de la table de droite qui n'ont pas de correspondance dans la table de gauche auront des valeurs NULL pour les colonnes de la table de gauche.

#### Syntaxe

```sql
SELECT colonnes
FROM table1
RIGHT JOIN table2
ON table1.colonne_commune = table2.colonne_commune;
```

#### Exemple

```sql
SELECT clients.nom, commandes.date_commande
FROM clients
RIGHT JOIN commandes
ON clients.id_client = commandes.id_client;
```

### FULL JOIN (ou FULL OUTER JOIN)

Le `FULL JOIN` renvoie tous les enregistrements lorsqu'il y a une correspondance dans la table de gauche ou de droite. Si une ligne n'a pas de correspondance dans l'une des tables, les valeurs de cette table seront NULL.

#### Syntaxe

```sql
SELECT colonnes
FROM table1
FULL JOIN table2
ON table1.colonne_commune = table2.colonne_commune;
```

#### Exemple

```sql
SELECT clients.nom, commandes.date_commande
FROM clients
FULL JOIN commandes
ON clients.id_client = commandes.id_client;
```

### Auto-Jointure

Une auto-jointure est une jointure d'une table avec elle-même. Cela peut être utile pour des comparaisons au sein d'une même table.

#### Syntaxe

```sql
SELECT a.colonne1, b.colonne2
FROM table a
INNER JOIN table b
ON a.colonne_commune = b.colonne_commune;
```

#### Exemple

```sql
SELECT a.nom AS Employe, b.nom AS Superviseur
FROM employes a
INNER JOIN employes b
ON a.superviseur_id = b.id;
```

## Points Clés

- **INNER JOIN** : Combine uniquement les lignes avec des correspondances dans les deux tables.
- **LEFT JOIN** : Inclut tous les enregistrements de la table de gauche et les correspondances de la table de droite.
- **RIGHT JOIN** : Inclut tous les enregistrements de la table de droite et les correspondances de la table de gauche.
- **FULL JOIN** : Inclut tous les enregistrements de gauche et de droite, même sans correspondance.
- **Auto-Jointure** : Joint une table avec elle-même pour des comparaisons internes.

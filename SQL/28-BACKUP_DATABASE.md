# Sauvegarder une Base de Données

L'instruction **`BACKUP DATABASE`** est utilisée dans **SQL Server** pour créer une sauvegarde complète d'une base de données existante. Cela permet de préserver l'état actuel de la base de données, qui pourra être restauré en cas de perte de données ou de panne.

## Sauvegarde Complète

Une **sauvegarde complète** copie l'ensemble de la base de données à un instant donné.

### Syntaxe

```sql
BACKUP DATABASE nom_de_la_base
TO DISK = 'chemin_du_fichier_de_sauvegarde';
```

### Exemple

```sql
BACKUP DATABASE myDatabase
TO DISK = 'C:\\Backup\\myDatabase.bak';
```

Cette commande crée une sauvegarde complète de la base de données **`myDatabase`** dans le fichier spécifié.

## Sauvegarde Différentielle

Une **sauvegarde différentielle** sauvegarde uniquement les données modifiées depuis la dernière sauvegarde complète, ce qui permet de réduire la taille des sauvegardes et le temps nécessaire.

### Syntaxe

```sql
BACKUP DATABASE nom_de_la_base
TO DISK = 'chemin_du_fichier_de_sauvegarde'
WITH DIFFERENTIAL;
```

### Exemple

```sql
BACKUP DATABASE myDatabase
TO DISK = 'C:\\Backup\\myDatabase_diff.bak'
WITH DIFFERENTIAL;
```

Cette commande sauvegarde uniquement les parties modifiées de la base de données **`myDatabase`** depuis la dernière sauvegarde complète.


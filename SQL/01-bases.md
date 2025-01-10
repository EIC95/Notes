# Bases de SQL

## Sensibilité à la Casse

Les mots-clés SQL ne sont **pas sensibles à la casse**. Par exemple, `SELECT` est équivalent à `select`.

## Point-virgule

Certains systèmes de bases de données nécessitent un **point-virgule** à la fin de chaque instruction SQL. Le point-virgule est utilisé pour séparer les instructions dans les systèmes qui permettent l'exécution de plusieurs instructions dans un même appel.

## Commentaires

- **Commentaires sur une seule ligne** : Utilisez `--` pour ajouter des commentaires sur une seule ligne.

  ```sql
  -- Ceci est un commentaire sur une seule ligne
  SELECT * FROM utilisateurs;
  ```

- **Commentaires sur plusieurs lignes** : Utilisez `/*` pour commencer un commentaire sur plusieurs lignes et `*/` pour le terminer.

  ```sql
  /*
   * Ceci est un commentaire
   * sur plusieurs lignes
   */
  SELECT * FROM produits;
  ```
# Volumes Docker

## Qu'est-ce qu'un Volume Docker ?

Un **volume Docker** est un mécanisme de stockage persistant qui permet de sauvegarder des données utilisées par les conteneurs. Les volumes ne sont pas affectés par la suppression des conteneurs, ce qui les rend utiles pour :

- **Persister les données** : Les données restent disponibles même après la suppression d'un conteneur.
- **Partager des données** : Permettre à plusieurs conteneurs d'accéder aux mêmes données.
- **Séparer les données** : Séparation des fichiers de données de l'image du conteneur.

---

## Commandes Principales pour les Volumes

### Créer un Volume

```bash
docker volume create mon-volume
```

- Crée un volume nommé `mon-volume`.

### Utiliser un Volume avec un Conteneur

Pour monter un volume dans un conteneur :

```bash
docker run -d -v mon-volume:/chemin/dans/le/conteneur image
```

- **mon-volume** : Nom du volume.
- **/chemin/dans/le/conteneur** : Emplacement où le volume sera monté à l'intérieur du conteneur.
- **image** : Image utilisée pour créer le conteneur.

Exemple avec Nginx :

```bash
docker run -d -v mon-volume:/usr/share/nginx/html nginx
```

### Lister les Volumes

```bash
docker volume ls
```

- Liste tous les volumes disponibles sur le système.

### Supprimer un Volume

```bash
docker volume rm mon-volume
```

- Supprime un volume nommé `mon-volume`.

---

## Exemple : Sauvegarde de Données

1. **Créer un volume** :

   ```bash
   docker volume create data-volume
   ```

2. **Lier le volume à un conteneur** :

   ```bash
   docker run -d -v data-volume:/data ubuntu
   ```

3. **Accéder aux données persistées** :
   - Les données enregistrées dans `/data` à l'intérieur du conteneur seront sauvegardées dans `data-volume`.

---

## Avantages des Volumes Docker

- **Persistants** : Les volumes ne sont pas supprimés quand un conteneur est supprimé.
- **Performants** : Ils offrent des performances élevées comparées aux montages directs de fichiers locaux.
- **Flexibles** : Utilisables par plusieurs conteneurs simultanément.

---

## Résumé des Commandes Utiles

- **Créer un volume** : `docker volume create <nom>`
- **Lister les volumes** : `docker volume ls`
- **Utiliser un volume** : `docker run -v <nom_volume>:<chemin>` 
- **Supprimer un volume** : `docker volume rm <nom>`

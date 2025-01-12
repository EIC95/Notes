# Création d'Images Docker

## Qu'est-ce qu'une Image Docker ?

Une **image Docker** est une version figée et exécutable d'un environnement, contenant tous les fichiers, configurations et dépendances nécessaires pour exécuter une application. C'est à partir de ces images que tu peux créer des conteneurs.

## Dockerfile

Le **Dockerfile** est un fichier texte contenant une série d'instructions permettant de créer une image Docker. Ces instructions définissent l'environnement dans lequel ton application va s'exécuter.

### Exemple de Dockerfile

Voici un exemple de **Dockerfile** pour une application Node.js simple :

```Dockerfile
# Utilise une image officielle Node.js comme base
FROM node:14

# Crée un répertoire dans le conteneur pour l'application
WORKDIR /app

# Copie les fichiers du projet local dans le conteneur
COPY . .

# Installe les dépendances
RUN npm install

# Expose le port 3000
EXPOSE 3000

# Commande à exécuter lorsque le conteneur démarre
CMD ["npm", "start"]
```

### Explication du Dockerfile :

1. **FROM node:14** : Utilise l'image officielle de Node.js version 14 comme base.
2. **WORKDIR /app** : Définit le répertoire de travail à l'intérieur du conteneur.
3. **COPY . .** : Copie tous les fichiers du répertoire courant de la machine locale dans le conteneur.
4. **RUN npm install** : Exécute la commande pour installer les dépendances de l'application.
5. **EXPOSE 3000** : Indique que le conteneur écoutera sur le port 3000.
6. **CMD ["npm", "start"]** : Définit la commande à exécuter quand le conteneur démarre.

## Construire une Image Docker à partir d'un Dockerfile

Pour construire l'image à partir du **Dockerfile**, utilise la commande suivante :

```bash
docker build -t mon-image-node .
```

- **-t mon-image-node** : Nom de l'image.
- **.** : Indique à Docker de chercher le Dockerfile dans le répertoire courant.

## Vérifier les Images Docker Locales

Pour vérifier les images disponibles localement, utilise la commande :

```bash
docker images
```

## Créer une Image Docker sans Dockerfile

Tu peux créer une image Docker à partir d'un conteneur en cours d'exécution avec la commande **docker commit** :

```bash
docker commit <nom_du_conteneur> <nom_de_l_image>
```

## Pousser une Image sur Docker Hub

Pour pousser une image vers Docker Hub, suis ces étapes :

1. **Se connecter à Docker Hub** :

   ```bash
   docker login
   ```

2. **Pousser l'image** :

   ```bash
   docker push <nom_utilisateur>/<nom_de_l_image>
   ```

   Exemple :

   ```bash
   docker push mon-utilisateur/mon-image-node
   ```

Cela permet de partager ou réutiliser l'image sur d'autres machines.

## Résumé des Commandes

- **docker build** : Crée une image à partir d'un Dockerfile.
- **docker images** : Liste les images locales.
- **docker commit** : Crée une image à partir d'un conteneur en cours d'exécution.
- **docker push** : Envoie une image vers Docker Hub.


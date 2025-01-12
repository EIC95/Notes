# Commandes Docker Essentielles

Voici les commandes Docker de base que tu utiliseras fréquemment pour interagir avec Docker.

## 1. Vérifier l'installation de Docker

Pour vérifier que Docker est bien installé et fonctionne, tu peux utiliser la commande suivante :

```bash
docker --version
```
Cela te donnera la version de Docker installée.

## 2. Lancer un conteneur

Pour démarrer un conteneur à partir d’une image :

```bash
docker run <image>
```

Par exemple, pour lancer un conteneur avec l'image **Ubuntu** :

```bash
docker run ubuntu
```

## 3. Lister les conteneurs en cours d'exécution

Pour voir les conteneurs qui sont actuellement en cours d'exécution :

```bash
docker ps
```

Cela te montrera les conteneurs actifs.

## 4. Lister tous les conteneurs (actifs et arrêtés)

Si tu veux voir tous les conteneurs, même ceux qui sont arrêtés :

```bash
docker ps -a
```

## 5. Arrêter un conteneur

Pour arrêter un conteneur qui tourne :

```bash
docker stop <nom_du_conteneur>
```

Par exemple :

```bash
docker stop mon-conteneur
```

## 6. Supprimer un conteneur

Une fois que le conteneur est arrêté, tu peux le supprimer avec :

```bash
docker rm <nom_du_conteneur>
```

## 7. Afficher les logs d'un conteneur

Si tu veux voir les logs de ton conteneur pour comprendre ce qui se passe à l’intérieur :

```bash
docker logs <nom_du_conteneur>
```

## 8. Lancer un conteneur en arrière-plan

Tu peux lancer un conteneur en mode détaché (en arrière-plan) avec l'option `-d` :

```bash
docker run -d <image>
```

Exemple :

```bash
docker run -d nginx
```

## 9. Accéder à un conteneur en cours d'exécution

Pour exécuter une commande à l’intérieur d’un conteneur en cours d'exécution, comme ouvrir un terminal, utilise :

```bash
docker exec -it <nom_du_conteneur> bash
```

Cela te permettra de naviguer dans le conteneur comme si tu étais directement dedans.

## 10. Construire une image à partir d'un Dockerfile

Si tu as un fichier **Dockerfile** et que tu veux construire une image à partir de celui-ci :

```bash
docker build -t <nom_de_l_image> .
```

Cela va créer une image en utilisant le Dockerfile situé dans le répertoire courant (indiqué par le `.`).

## 11. Lister les images locales

Pour voir toutes les images que tu as téléchargées ou créées localement :

```bash
docker images
```

## 12. Supprimer une image

Si tu veux supprimer une image locale qui n'est plus nécessaire :

```bash
docker rmi <nom_de_l_image>
```

## 13. Télécharger une image depuis Docker Hub

Pour télécharger une image depuis Docker Hub :

```bash
docker pull <image>
```

Par exemple, pour télécharger l'image **Ubuntu** :

```bash
docker pull ubuntu
```

## 14. Pousser une image vers Docker Hub

Si tu as une image que tu souhaites partager sur Docker Hub, tu peux la pousser avec :

```bash
docker push <nom_utilisateur>/<nom_de_l_image>
```

# Docker Compose

## Qu'est-ce que Docker Compose ?

**Docker Compose** est un outil permettant de définir et de gérer des applications multi-conteneurs à l'aide d'un fichier YAML. Il simplifie le déploiement et la gestion des applications complexes en automatisant la création, le démarrage et l'arrêt de plusieurs conteneurs.

---

## Avantages de Docker Compose

- **Simplification** : Gestion de plusieurs conteneurs avec un seul fichier YAML.
- **Portabilité** : Facilite le partage de configurations entre environnements (développement, test, production).
- **Automatisation** : Simplifie le démarrage, l'arrêt et la mise à jour des conteneurs.

---

## Installation de Docker Compose

Docker Compose est généralement inclus avec Docker Desktop. Si ce n'est pas le cas, installe-le en suivant les instructions officielles [ici](https://docs.docker.com/compose/install/).

Pour vérifier que Docker Compose est installé :

```bash
docker compose version
```

---

## Fichier YAML pour Docker Compose

Un fichier YAML (généralement nommé `docker-compose.yml`) définit les services, réseaux, volumes, et configurations nécessaires pour l'application.

### Exemple Simple : Application Web avec Nginx et MySQL

```yaml
version: '3.8' # Version de Docker Compose

services:
  web:
    image: nginx
    ports:
      - "8080:80" # Mappe le port 80 du conteneur au port 8080 de l'hôte
    volumes:
      - ./html:/usr/share/nginx/html # Monte un volume pour les fichiers HTML
    networks:
      - mon-reseau

  db:
    image: mysql:5.7
    environment:
      MYSQL_ROOT_PASSWORD: exemple123 # Définit la variable d'environnement pour MySQL
    volumes:
      - db-data:/var/lib/mysql # Stocke les données MySQL dans un volume
    networks:
      - mon-reseau

networks:
  mon-reseau:
    driver: bridge # Type de réseau

volumes:
  db-data:
```

---

## Commandes Principales de Docker Compose

### Lancer les Services

```bash
docker compose up
```

- Crée et démarre les conteneurs définis dans `docker-compose.yml`.
- Ajoute `-d` pour lancer les conteneurs en arrière-plan :

  ```bash
  docker compose up -d
  ```

### Arrêter les Services

```bash
docker compose down
```

- Arrête et supprime les conteneurs, réseaux et volumes créés par Docker Compose.

### Voir les Logs des Conteneurs

```bash
docker compose logs
```

- Ajoute `-f` pour suivre les logs en temps réel.

### Lister les Services Actifs

```bash
docker compose ps
```

- Affiche les conteneurs gérés par Docker Compose.

---

## Exemple : Déploiement d'une Application Python avec Redis

### Fichier `docker-compose.yml`

```yaml
version: '3.8'

services:
  app:
    build: .
    ports:
      - "5000:5000"
    networks:
      - backend

  redis:
    image: redis
    networks:
      - backend

networks:
  backend:
    driver: bridge
```

### Structure du Projet

```
my-app/
│
├── app.py         # Code de l'application Python
├── Dockerfile     # Instructions pour construire l'image
└── docker-compose.yml
```

### Dockerfile pour l'Application

```dockerfile
FROM python:3.9-slim
WORKDIR /app
COPY . .
RUN pip install flask redis
CMD ["python", "app.py"]
```

### Fichier `app.py`

```python
from flask import Flask
import redis

app = Flask(__name__)
cache = redis.Redis(host='redis', port=6379)

@app.route('/')
def home():
    return "Bienvenue dans mon application avec Redis !"

if __name__ == "__main__":
    app.run(host="0.0.0.0", port=5000)
```

### Démarrer l'Application

1. Construire et lancer les conteneurs :

   ```bash
   docker compose up --build
   ```

2. Accéder à l'application sur `http://localhost:5000`.

---

## Résumé des Commandes Docker Compose

- **Lancer les services** : `docker compose up [-d]`
- **Arrêter les services** : `docker compose down`
- **Suivre les logs** : `docker compose logs [-f]`
- **Lister les services actifs** : `docker compose ps`

---


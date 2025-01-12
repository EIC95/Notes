# Réseaux Docker

## Qu'est-ce qu'un Réseau Docker ?

Un **réseau Docker** permet de connecter des conteneurs entre eux ou avec le monde extérieur. Docker utilise des réseaux pour gérer la communication et l'isolation entre conteneurs.

### Types de Réseaux Docker

1. **bridge** (par défaut) :
   - Réseau local privé pour les conteneurs sur une même machine.
   - Les conteneurs peuvent se communiquer entre eux uniquement via ce réseau.

2. **host** :
   - Le conteneur partage directement le réseau de l’hôte.
   - Pas d'isolation réseau.

3. **none** :
   - Le conteneur n'a aucun accès réseau.
   - Utile pour des tâches nécessitant une isolation complète.

4. **overlay** :
   - Réseau utilisé pour connecter des conteneurs sur plusieurs machines (clusters Docker Swarm).

---

## Commandes Principales pour les Réseaux

### Lister les Réseaux Disponibles

```bash
docker network ls
```

- Affiche tous les réseaux disponibles sur le système.

### Créer un Réseau

```bash
docker network create mon-reseau
```

- Crée un réseau nommé `mon-reseau`.

### Connecter un Conteneur à un Réseau

Lors de la création d’un conteneur, tu peux spécifier un réseau avec l’option `--network` :

```bash
docker run -d --network mon-reseau nginx
```

- Connecte le conteneur au réseau `mon-reseau`.

### Ajouter un Conteneur à un Réseau Existant

Pour ajouter un conteneur déjà existant à un réseau :

```bash
docker network connect mon-reseau mon-conteneur
```

- **mon-reseau** : Nom du réseau.
- **mon-conteneur** : Nom ou ID du conteneur.

### Supprimer un Réseau

Pour supprimer un réseau non utilisé :

```bash
docker network rm mon-reseau
```

- Supprime le réseau `mon-reseau`.

---

## Exemple Pratique : Communication entre Conteneurs

1. **Créer un réseau personnalisé** :

   ```bash
   docker network create mon-reseau
   ```

2. **Créer deux conteneurs connectés à ce réseau** :

   ```bash
   docker run -d --name conteneur1 --network mon-reseau nginx
   docker run -d --name conteneur2 --network mon-reseau nginx
   ```

3. **Tester la communication entre les conteneurs** :
   - Accéder au terminal du premier conteneur :

     ```bash
     docker exec -it conteneur1 bash
     ```

   - Tester la connexion au deuxième conteneur par son nom :

     ```bash
     ping conteneur2
     ```

   Si les conteneurs sont sur le même réseau, la commande `ping` devrait fonctionner.

---

## Résumé des Commandes Utiles

- **Lister les réseaux** : `docker network ls`
- **Créer un réseau** : `docker network create <nom>`
- **Connecter un conteneur à un réseau** :
  - Lors de la création : `docker run --network <nom_du_reseau> <image>`
  - Après création : `docker network connect <nom_du_reseau> <nom_du_conteneur>`
- **Supprimer un réseau** : `docker network rm <nom>`

---

## Avantages des Réseaux Docker

- **Isolation** : Permet de séparer les environnements réseau pour plus de sécurité.
- **Communication facilitée** : Les conteneurs d’un même réseau peuvent communiquer par leurs noms.
- **Personnalisation** : Possibilité de configurer des réseaux selon les besoins.

---

Ces notes te donnent un aperçu complet des réseaux Docker. Si tu souhaites des détails supplémentaires ou un autre exemple, fais-moi signe ! 😊
```Voici des notes en Markdown sur les **Réseaux Docker** :

```markdown
# Réseaux Docker

## Qu'est-ce qu'un Réseau Docker ?

Un **réseau Docker** permet de connecter des conteneurs entre eux ou avec le monde extérieur. Docker utilise des réseaux pour gérer la communication et l'isolation entre conteneurs.

### Types de Réseaux Docker

1. **bridge** (par défaut) :
   - Réseau local privé pour les conteneurs sur une même machine.
   - Les conteneurs peuvent se communiquer entre eux uniquement via ce réseau.

2. **host** :
   - Le conteneur partage directement le réseau de l’hôte.
   - Pas d'isolation réseau.

3. **none** :
   - Le conteneur n'a aucun accès réseau.
   - Utile pour des tâches nécessitant une isolation complète.

4. **overlay** :
   - Réseau utilisé pour connecter des conteneurs sur plusieurs machines (clusters Docker Swarm).

---

## Commandes Principales pour les Réseaux

### Lister les Réseaux Disponibles

```bash
docker network ls
```

- Affiche tous les réseaux disponibles sur le système.

### Créer un Réseau

```bash
docker network create mon-reseau
```

- Crée un réseau nommé `mon-reseau`.

### Connecter un Conteneur à un Réseau

Lors de la création d’un conteneur, tu peux spécifier un réseau avec l’option `--network` :

```bash
docker run -d --network mon-reseau nginx
```

- Connecte le conteneur au réseau `mon-reseau`.

### Ajouter un Conteneur à un Réseau Existant

Pour ajouter un conteneur déjà existant à un réseau :

```bash
docker network connect mon-reseau mon-conteneur
```

- **mon-reseau** : Nom du réseau.
- **mon-conteneur** : Nom ou ID du conteneur.

### Supprimer un Réseau

Pour supprimer un réseau non utilisé :

```bash
docker network rm mon-reseau
```

- Supprime le réseau `mon-reseau`.

---

## Exemple Pratique : Communication entre Conteneurs

1. **Créer un réseau personnalisé** :

   ```bash
   docker network create mon-reseau
   ```

2. **Créer deux conteneurs connectés à ce réseau** :

   ```bash
   docker run -d --name conteneur1 --network mon-reseau nginx
   docker run -d --name conteneur2 --network mon-reseau nginx
   ```

3. **Tester la communication entre les conteneurs** :
   - Accéder au terminal du premier conteneur :

     ```bash
     docker exec -it conteneur1 bash
     ```

   - Tester la connexion au deuxième conteneur par son nom :

     ```bash
     ping conteneur2
     ```

   Si les conteneurs sont sur le même réseau, la commande `ping` devrait fonctionner.

---

## Résumé des Commandes Utiles

- **Lister les réseaux** : `docker network ls`
- **Créer un réseau** : `docker network create <nom>`
- **Connecter un conteneur à un réseau** :
  - Lors de la création : `docker run --network <nom_du_reseau> <image>`
  - Après création : `docker network connect <nom_du_reseau> <nom_du_conteneur>`
- **Supprimer un réseau** : `docker network rm <nom>`

---

## Avantages des Réseaux Docker

- **Isolation** : Permet de séparer les environnements réseau pour plus de sécurité.
- **Communication facilitée** : Les conteneurs d’un même réseau peuvent communiquer par leurs noms.
- **Personnalisation** : Possibilité de configurer des réseaux selon les besoins.

---
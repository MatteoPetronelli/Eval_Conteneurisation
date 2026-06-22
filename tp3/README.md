# TaskFlow - Conteneurisation

Ce projet contient l'infrastructure Docker complète pour déployer l'application TaskFlow (Frontend, API Backend et Cache Redis).

## Prérequis

- **Docker** et **Docker Compose** doivent être installés sur votre machine.

## Utilisation

1. **Configuration des variables d'environnement :**
   Copiez le fichier d'exemple pour créer votre propre configuration :
   ```bash
   cp .env.example .env
   ```
   *(Vous pouvez modifier les valeurs de `.env` si nécessaire, bien que les valeurs par défaut soient prévues pour fonctionner directement).*

2. **Lancement de l'application :**
   Construisez et démarrez tous les conteneurs avec la commande suivante :
   ```bash
   docker-compose up --build -d
   ```
   *(Ou `docker compose up --build -d` selon votre version de Docker).*

3. **Accès aux services :**
   - **Frontend** : L'interface utilisateur est accessible sur [http://localhost:8080](http://localhost:8080)
   - **Backend API** : L'API répond sur le port 3001 (ex: [http://localhost:3001](http://localhost:3001))
   - **Redis** : Le cache n'est accessible qu'en interne par le backend.

4. **Arrêt des services :**
   Pour stopper l'application sans supprimer les données du cache :
   ```bash
   docker-compose down
   ```
   Si vous souhaitez également détruire le volume de données Redis, ajoutez l'option `-v` :
   ```bash
   docker-compose down -v
   ```

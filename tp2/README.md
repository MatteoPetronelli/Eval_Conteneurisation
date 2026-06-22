# TP2 - Déploiement avec Docker Compose

Ce dossier contient la configuration Docker Compose pour déployer l'architecture complète : Frontend, API Node.js, Base de données PostgreSQL et Adminer.

## Commandes pour lancer la stack

Pour démarrer tous les services en arrière-plan, placez-vous dans ce dossier (où se trouve le fichier `docker-compose.yml`) et exécutez la commande suivante :

```bash
docker-compose up -d
```
*(ou `docker compose up -d` selon votre version de Docker)*

L'application sera accessible aux adresses suivantes :
- **Frontend** : [http://localhost:8080](http://localhost:8080)
- **API** : [http://localhost:3000](http://localhost:3000)
- **Adminer** : [http://localhost:8081](http://localhost:8081)

## Vérifier la persistance des données

Les données de la base de données PostgreSQL sont sauvegardées de manière persistante grâce à un volume nommé Docker (`db-data`).

Pour vérifier la persistance :
1. Accédez à Adminer ([http://localhost:8081](http://localhost:8081)).
2. Connectez-vous avec les identifiants présents dans le fichier `.env` :
   - Système : PostgreSQL
   - Serveur : `db`
   - Utilisateur : `appuser`
   - Mot de passe : `supersecret`
   - Base de données : `appdb`
3. Créez une table et insérez-y quelques données (ou utilisez l'application pour le faire).
4. Stoppez la stack et supprimez les conteneurs avec la commande :
   ```bash
   docker-compose down
   ```
5. Relancez la stack :
   ```bash
   docker-compose up -d
   ```
6. Retournez sur Adminer ou l'application : vos données créées précédemment seront toujours là.

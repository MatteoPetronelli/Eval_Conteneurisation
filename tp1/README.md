# TP1 - Correction Dockerfile

## Comment builder l'image

Pour construire l'image Docker, exécutez la commande suivante à la racine du dossier (là où se trouve le `Dockerfile`) :

```bash
docker build -t tp1-node-app .
```

## Vérifier la taille de l'image

Une fois l'image construite, vous pouvez vérifier qu'elle fait bien moins de 200 MB avec la commande :

```bash
docker images tp1-node-app
```

## Comment lancer le conteneur

Pour démarrer l'application sur le port 3000 et vérifier qu'elle fonctionne, utilisez la commande suivante :

```bash
docker run -d -p 3000:3000 --name tp1-app tp1-node-app
```

L'application sera alors accessible à l'adresse : [http://localhost:3000](http://localhost:3000).
Vous pouvez vérifier les logs avec `docker logs tp1-app` et constater que l'application tourne bien avec l'utilisateur non-root.

# Utilisation de l'image officielle de Node (version 10-slim)
FROM node:10-slim

# Définition du répertoire d'application dans le conteneur
WORKDIR /app

# Installation de nodemon globalement dans le conteneur
RUN npm install -g nodemon

# Copie des fichiers package*.json du dossier actuel vers le dossier /app dans le conteneur
COPY package*.json /app/

# Exécution des commandes npm ci, npm cache clean, et déplacement des node_modules
RUN npm ci && npm cache clean --force && mv /app/node_modules /node_modules

# Copie du contenu actuel du projet dans le dossier /app du conteneur
COPY . /app

# Définition de la variable d'environnement PORT à 80
ENV PORT=80

# Rendre le port 80 disponible pour les liens et/ou la publication
EXPOSE 80

# Rendre le port 5858 disponible pour les liens et/ou la publication
EXPOSE 5858

# Commande à exécuter lors du lancement du conteneur
CMD ["nodemon", "server.js"]

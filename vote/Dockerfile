# Utilisation de l'image de base officielle de Python
FROM python:latest

# Définition du répertoire d'application dans le conteneur
WORKDIR /app

# Ajout du fichier requirements.txt dans le dossier /app du conteneur
COPY requirements.txt /app/requirements.txt

# Installation des dépendances définies dans requirements.txt
RUN pip install -r requirements.txt

# Copie du code depuis le dossier actuel vers le dossier /app du conteneur
COPY . /app

# Rendre le port 80 disponible pour les liens et/ou la publication
EXPOSE 80

# Commande à exécuter lors du lancement du conteneur
CMD ["python", "app.py"]

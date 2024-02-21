# Utilisation de l'image de Nginx version 1.12 comme image de base
FROM nginx:1.12

# Copie du fichier de configuration par défaut
COPY default.conf /etc/nginx/conf.d/default.conf

# Copie du fichier HTML pour les réponses BACKEND-NOT-FOUND
COPY backend-not-found.html /var/www/html/backend-not-found.html

# Copie de la configuration du proxy
COPY proxy.conf /etc/nginx/includes/

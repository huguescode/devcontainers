# Utiliser une image de base
FROM python:3.8-slim

# Installer des outils nécessaires
RUN apt-get update && apt-get install -y \
    nginx \
    supervisor \
    && apt-get clean

# Configurer le dossier de travail
WORKDIR /app

# Copier les fichiers dans le conteneur
COPY . /app

# Installer les dépendances Python
RUN pip install --no-cache-dir -r requirements.txt

# Ouvrir le port 8000
EXPOSE 8000

# Démarrer Supervisord au lancement
CMD ["supervisord", "-c", "/app/supervisord.conf"]


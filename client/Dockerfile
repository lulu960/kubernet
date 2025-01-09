# Étape 1 : Construire l'application React
FROM node:alpine AS build

# Définir le répertoire de travail
WORKDIR /app

# Copier les fichiers nécessaires
COPY package.json ./

# Installer les dépendances
RUN npm install

# Copier les fichiers source
COPY . .

# Construire l'application React
RUN npm run build

# Étape 2 : Servir l'application avec Node.js
FROM node:alpine

# Définir le répertoire de travail
WORKDIR /app

# Copier les fichiers de build dans le nouveau conteneur
COPY --from=build /app/build ./build

# Installer un simple serveur Node.js pour servir les fichiers statiques
RUN npm install -g serve

# Exposer le port 3000 (ou autre port)
EXPOSE 3000

# Commande par défaut pour démarrer le serveur
CMD ["serve", "-s", "build", "-l", "3000"]

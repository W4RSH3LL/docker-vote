# Utilisation de l'image Maven slim (alpine) comme image de construction
FROM maven:3.5-jdk-8-alpine AS build

# Définition du répertoire d'application dans le conteneur de construction
WORKDIR /code

# Copie du fichier pom.xml depuis le dossier actuel vers /code/pom.xml dans le conteneur de construction
COPY pom.xml /code/pom.xml

# Exécution des commandes mvn pour résoudre les dépendances et vérifier
RUN mvn dependency:resolve && mvn verify

# Copie du dossier src/main vers /code/src/main dans le conteneur de construction
COPY src/main /code/src/main

# Exécution de la commande "mvn package" dans le conteneur de construction
RUN mvn package

# Changement de l'image de base vers OpenJDK 8 (jre alpine)
FROM openjdk:8-jre-alpine

# Copie du jar produit depuis le conteneur de construction vers le répertoire racine de ce conteneur
COPY --from=build /code/target/worker-jar-with-dependencies.jar /

# Définition de la commande à exécuter lors du lancement du conteneur
CMD ["java", "-XX:+UnlockExperimentalVMOptions", "-XX:+UseCGroupMemoryLimitForHeap", "-jar", "/worker-jar-with-dependencies.jar"]

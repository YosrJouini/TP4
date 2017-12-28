# TP4Microservices: Dockernization des MicroServices  

# Architecture

Product Service : Service principal, qui offre une API REST pour lister une liste de produits.

Config Service : Service de configuration, dont le rôle est de centraliser les fichiers de configuration des différents microservices dans un endroit unique.

Proxy Service : Passerelle se chargeant du routage d'une requête vers l'une des instances d'un service, de manière à gérer automatiquement la distribution de charge.

Discovery Service: Service permettant l'enregistrement des instances de services en vue d'être découvertes par d'autres services.

# Etapes

1/ Génération d'un fichier DockerFile: Ce Dockerfile précise les caractéristiques de l'image à créer
Exemple: 

FROM openjdk:8-jdk-alpine
VOLUME /tmp
ARG JAR_FILE
ADD ${JAR_FILE} product-service.jar
ENTRYPOINT ["java", "-Djava.security.egd=file:/dev/./urandom","-jar","product-service.jar"]

2/ Ajout du plugin offert par Spotify au fichier pom.xml

3/ Construction des images et vérification de la création
docker images

4/lancement des conteneurs en utilisant docker-compose.yml

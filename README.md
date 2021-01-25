
Avant toute choses, un grand merci à @samijnih pour m'avoir enseigné Docker et relue/modifié ce Readme.
https://github.com/samijnih

# Docker Base PHP-nginx

L'un des principaux avantages est de mutualiser l'environnement technique (aka stack tech) au sein d'un projet, d'un groupe, d'une corporation, afin de faciliter les phases de développement tout comme les phases de mise en ligne avec des solutions tierces compatible comme Google Cloud Engine, Amazon Web Services etc.

Nous avons ici en outre la possiblité de lancer un projet PHP procédural avec un serveur HTTP Nginx plutôt qu'un serveur HTTP apache.

C'est très simple. installez Docker, clonez ce projet et lancez la commande :

```shell
docker-compose up -d 
```

Normalement, conformément au fichier de configuration (*docker-compose.yml*), toutes les images dockers devraient être téléchargées sur votre machine et l’environnement sera prêt à afficher "hello world" dans à l'adresse localhost ou 127.0.0.1.

## Prérequis

- docker // voir la version spécifié dans https://docs.docker.com/docker-for-windows/install/
- docker-compose

## Composer

Pour avoir composer, il faut rentrer dans le container php pour le télécharger à la main (pour le moment)

```shell
docker-compose up -d php
docker-compose exec php bash
php -r "copy('https://getcomposer.org/installer', 'composer-setup.php');"
php -r "if (hash_file('sha384', 'composer-setup.php') === '756890a4488ce9024fc62c56153228907f1545c228516cbf63f885e036d37e9a59d27d63f46af1d4d07ee0f76181c7d3') { echo 'Installer verified'; } else { echo 'Installer corrupt'; unlink('composer-setup.php'); } echo PHP_EOL;"
php composer-setup.php
php -r "unlink('composer-setup.php');"
mv composer.phar composer && chmod +x composer && mv composer /usr/local/bin
composer --version
``` 

## Aide

> docker-compose up -d [nom du container]

Demande à docker de créer et démarrer le service spécifié dans le fichier de configuration.

 L'option `-d` permet de d'avoir le service qui tourne en arrière-plan pour ne pas être bloquant au niveau I/O sur le terminal.

### À venir

Je vais prochainement ajouter SQL / PHPMyAdmin sur ce repo

Un autre repo avec Symfony arrivera dans la semaine.

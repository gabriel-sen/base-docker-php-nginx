
# Docker Base PHP-nginx

Docker est un simulateur d'environement ou vous pouvez installler difeerent outils pour pouvoir les utiliser.
L'utilité est de pouvoir partager cette configuration avec tout vos collègues pour avoir le même environement de dev sur vos machines. 

Cette environnement de travaille permet de lancer un projet php procedural avec un serveur nginx et non un server apache.
C'est très simple. installez docker, pullez ce projet et lancez la commande : 
  ```shell
  docker-compose up -d 
  ```
  Normalement, conformément au fichier de configuation, toute les images devraient être téléchargé dans votre Docker et l'environement seras prêt à afficher "hello world" dans votre localhost.

## Requirements

- Docker 
  https://docs.docker.com/docker-for-windows/install/
- docker-compose
  ```shell
  docker pull composer:latest
   ```
  https://docs.docker.com/compose/install/
  
- php7.4-fpm-alpine
  ```shell
  docker pull php:fpm-alpine
  ```
  https://hub.docker.com/_/php?tab=tags&page=1&ordering=last_updated
  
- nginx:latest
  ```shell
  docker pull nginx:latest
  ```
  https://hub.docker.com/_/nginx?tab=tags

#### Lancer docker

```shell
docker-compose up -d 

#lance les services définie dans le docker-compose.yml
# l'instruction -d lance docker en arriere plan 

# docker-compose up -d [nom du container]
#lance un container unique 
```
#### Installation de Composer
- installer composer  dans docker : https://getcomposer.org/download/

```shell
php -r "copy('https://getcomposer.org/installer', 'composer-setup.php');"
php -r "if (hash_file('sha384', 'composer-setup.php') === '756890a4488ce9024fc62c56153228907f1545c228516cbf63f885e036d37e9a59d27d63f46af1d4d07ee0f76181c7d3') { echo 'Installer verified'; } else { echo 'Installer corrupt'; unlink('composer-setup.php'); } echo PHP_EOL;"
php composer-setup.php
php -r "unlink('composer-setup.php');"
```

### a venir

Je vais prochainement ajouter SQL / PhpMyadmin sur ce repo
Un autre repo avec Symfony arriveras dans la semain.

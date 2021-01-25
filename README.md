
# Docker Base PHP-nginx

Cette environnement de travaille permet de lancer un projet php procedural type Bac a sable pour apprendre en s'amusant :D

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

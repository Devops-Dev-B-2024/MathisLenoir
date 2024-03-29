# Docker de Mathis LENOIR

### 1. Télécharger Docker Desktop

Disponible à ce [liens](https://desktop.docker.com/win/main/amd64/Docker%20Desktop%20Installer.exe?utm_source=docker&utm_medium=webreferral&utm_campaign=dd-smartbutton&utm_location=module).

### 3.A Récupérer l'image "httpd" ou "nginx"

> $ docker pull httpd
>
> ou
>
> $ docker pull nginx

### 3.B. Voir l'image à bien était téléchargé :

> $ docker image list
>
> httpd ; latest ; ac45b24b92cc ; 2 months ago ; 167MB

### 3.C. Démarrer la container

Le fichier HTML qui sera affiché avec le docker se trouve [ici](./html/index.html).

### 3.D Sans DockerFile
> $ docker run -dit --name test -v /usr/local/apache2/htdocs/:/html/index.html -p 80:80 httpd

### 3.E Sans DockerFile
> $ docker stop [id du docker, voir : docker ps]
>
> $ docker rm [La même id]

### 3.F Sans DockerFile et avec CP
> $ docker run -dit --name test -p 80:80 httpd
> 
> $ docker cp ./html/index.html [id du docker, voir : docker ps]:/usr/local/apache2/htdocs
> 
> $ docker stop [La même id]
>
> $ docker rm [La même id]

### 5.A Avec DockerFile
Le DockerFile est présent [ici](./TP1/DockerFile)

### 5.B Exécution de l'image
> $ docker build -t my-super-sql ./mysql/
>
> $ docker build -t my-phpma ./phpmyadmin/ 
>
> docker network create -d bridge sql-Ynov
>
> $ docker run -dit --network=sql-ynov --name mysql -p 3306:3306 my-super-sql
>
> $ docker run -dit --network=sql-ynov --name phpma -p 80:80 my-phpma

## 5. MySQL et PHPMyAdmin : Dockerfile

### 5.A Récupérer les images
> $ docker pull mysql
>
> et
>
> $ docker pull phpmyadmin

### 5.B Exécuter deux containers depuis les images
Le DockerFile est présent MySQL [ici](./TP2/mysql/Dockerfile).

Le DockerFile est présent PHPMyAdmin [ici](./TP2/phpmyadmin/Dockerfile).

## 6. MySQL et PHPMyAdmin : docker-compose

### 6.A A quoi sert Docker-Compose ?

> Docker-Compose permet est outil ayant pour but de gérer plusieurs container à la fois, cela permet un déploiement plus efficace, et plus stable.

### 6.B Quel est la commande pour lancer un Docker-Compose ?

> $ docker-compose -f .\docker-compose.yaml up

### 6.C Ecrire un fichier docker compose : 
Le fichier docker-compose est présent [ici](./TP2/docker-compose.yaml).
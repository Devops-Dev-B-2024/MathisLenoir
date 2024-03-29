# Docker de Mathis LENOIR

### Récupérer l'image "httpd" ou "nginx"

> $ docker pull httpd
>
> ou
>
> $ docker pull nginx

### Voir l'image à bien était téléchargé :

> $ docker image list
>
> httpd ; latest ; ac45b24b92cc ; 2 months ago ; 167MB

### Démarrer la container

Le fichier HTML qui sera affiché avec le docker se trouve [ici](./html/index.html).

### Sans DockerFile
> $ docker run -dit --name test -v /usr/local/apache2/htdocs/:/html/index.html -p 80:80 httpd
>
> $ docker stop [id du docker, voir : docker ps]
>
> $ docker rm [La même id]
### Sans DockerFile
> $ docker run -dit --name test -p 80:80 httpd
> 
> $ docker cp ./html/index.html [id du docker, voir : docker ps]:/usr/local/apache2/htdocs
> 
> $ docker stop [La même id]
>
> $ docker rm [La même id]

### Avec DockerFile
Le DockerFile est présent [ici](./TP1/DockerFile)

> $ docker run -dit --name test -p 80:80 my-apache2

La différence visible ici est que cela facilite l'utilisation de la dite commande, mais aussi, que celle-ci est bien plus courte que précédemment.

### MySQL et PHPMyAdmin : Dockerfile

> $ docker pull mysql
>
> et
>
> $ docker pull phpmyadmin

Le DockerFile est présent MySQL [ici](./TP2/mysql/Dockerfile).

Le DockerFile est présent PHPMyAdmin [ici](./TP2/phpmyadmin/Dockerfile).

### MySQL et PHPMyAdmin : docker compose

#### A quoi sert Docker-Compose ?

> Docker-Compose permet est outil ayant pour but de gérer plusieurs container à la fois, cela permet un déploiement plus efficace, et plus stable.

#### Quel est la commande pour lancer un Docker-Compose ?

> $ docker-compose -f .\docker-compose.yaml up

Le fichier docker-compose est présent [ici](./TP2/docker-compose.yaml).
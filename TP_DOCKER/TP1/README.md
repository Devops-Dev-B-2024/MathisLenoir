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
> docker run -dit --name test -v /usr/local/apache2/htdocs/:/html/index.html -p 80:80 httpd
>
> docker stop [id du docker, voir : docker ps]
>
> docker rm [La même id]
### Sans DockerFile
> docker run -dit --name test -p 80:80 httpd
> 
> docker cp ./html/index.html [id du docker, voir : docker ps]:/usr/local/apache2/htdocs
>
> docker stop [La même id]
>
> docker rm [La même id]

### Avec DockerFile
Le DockerFile est présent [ici](./DockerFile)

> docker run -dit --name test -v /var/www/html:/html -p 80:80 httpd
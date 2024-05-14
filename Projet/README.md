# Projet stack LAMP via HELM

## Installation (Windows)
###### Nous partons du principe que Docker, minikube et HELM sont installé et lancé.

### Accéder au répertoire qui contient la chart
> $ cd < repostiory >

### Créer un package de la chart
> $ helm package ./

### Installer la chart sur votre minikube
> $ minikube install < nom-de-votre-chart >.tgz

### Récupérez le nom des pods
> $ kubectl get pod

### Exposez le port du site web (php-apache)
> $ kubectl expose pod < nom-du-pod > --type=NodePort --port=80

### Générez un liens vers votre site
> $ minikube service < nom-du-pod > --url

Vous pouvez désormer naviguer sur votre site.

---
## Informations supplémentaires

Le projet est basé sous [WordPress](https://fr.wordpress.org/).
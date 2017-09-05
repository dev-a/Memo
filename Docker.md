# Memo docker:

## Sommaire
- [Arrêter et supprimer tous les conteneurs](#arrêter-et-supprimer-tous-les-conteneurs)
- [Supprimer tous les conteneurs qui ne sont plus en fonctionnement](#supprimer-tous-les-conteneurs-qui-ne-sont-plus-en-fonctionnement)
- [Se connecter en bash à un container en fonctionnement](#se-connecter-en-bash-à-un-container-en-fonctionnement)
- [Supprimer tous les reseaux existants](#supprimer-tous-les-reseaux-existants)
- [Sous windows gerer les chemins repertoires](#sous-windows-gerer-les-chemins-repertoires)
- [Construire un conteneur "dev-a/mon_nom" depuis un dockerfile dans le repertoire courant](#construire-un-conteneur-dev-amon_nom-depuis-un-dockerfile-dans-le-repertoire-courant)
- [Nettoyage docker "mode brutus"](#nettoyage-docker-mode-brutus)
- [Utilisation de portainer.io](#utilisation-de-portainerio)
  - [Lancer portainer](#lancer-portainer)
---
## Arrêter et supprimer tous les conteneurs
> *docker rm $(docker ps -aq) -f*

## Supprimer tous les conteneurs qui ne sont plus en fonctionnement
> *docker rm $(docker ps -q -f status=exited)*

## Se connecter en bash à un container en fonctionnement
> *docker exec -it [container-id] bash*

## Supprimer tous les reseaux existants
> *docker network rm $(docker network ls -q)* 

(produira des erreurs sur les réseaux en fonctionnement ou ceux interne)

## Sous windows gerer les chemins repertoires
creer un fichier .env avec "COMPOSE_CONVERT_WINDOWS_PATHS=1"

## Construire un conteneur "dev-a/mon_nom" depuis un dockerfile dans le repertoire courant 
> docker build -t dev-a/mon_nom .

## Nettoyage docker "mode brutus"
> sudo systemctl stop docker

> sudo su -

> rm -r /var/lib/docker/

> sudo systemctl start docker


## Utilisation de portainer.io
### Lancer portainer 
> *docker run -d -p 9000:9000 --label appli=portainer -v /var/run/docker.sock:/var/run/docker.sock portainer/portainer*

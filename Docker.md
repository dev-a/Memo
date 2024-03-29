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
```sh
docker rm $(docker ps -aq) -f
```

## Supprimer tous les conteneurs qui ne sont plus en fonctionnement
```sh
docker rm $(docker ps -q -f status=exited)
```

## Se connecter en bash à un container en fonctionnement
```sh
docker exec -it [container-id] bash
```

## Supprimer tous les reseaux existants
```sh
docker network rm $(docker network ls -q)
```

(produira des erreurs sur les réseaux en fonctionnement ou ceux interne)

## Télécharger un fichier depuis un conteneur vers la machine hôte
```sh
docker <containerId>:/file/path/within/container /host/path/target
```

## Sous windows gerer les chemins repertoires
creer un fichier .env avec "COMPOSE_CONVERT_WINDOWS_PATHS=1"

## Construire un conteneur "dev-a/mon_nom" depuis un dockerfile dans le repertoire courant 
```sh
docker build -t dev-a/mon_nom .
```

## Nettoyage docker "mode brutus" (des repertoires /var/lib/docker/)
```shell
sudo systemctl stop docker
#sudo su -
sudo rm -r /var/lib/docker/
sudo systemctl start docker
```

Voir aussi https://github.com/chadoe/docker-cleanup-volumes

## Utilisation de portainer.io
### Lancer portainer 
#### Avec authentication
```sh
docker run -d -p 9000:9000 --label appli=portainer -v /var/run/docker.sock:/var/run/docker.sock portainer/portainer
```
#### Sans authentication
```sh
docker run -d -p 9000:9000 --label appli=portainer -v /var/run/docker.sock:/var/run/docker.sock portainer/portainer --no-auth
```

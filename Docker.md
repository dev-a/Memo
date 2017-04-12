# Memo docker:

## Arrêter et supprimer tous les conteneurs
*docker rm $(docker ps -aq) -f*

## Supprimer tous les conteneurs qui ne sont plus en fonctionnement
*docker rm $(docker ps -q -f status=exited)*

## Se connecter en bash à un container en fonctionnement
*docker exec -it [container-id] bash*

## Supprimer tous les reseaux existants
*docker network rm $(docker network ls -q)* 

(produira des erreurs sur les réseaux en fonctionnement ou ceux interne)

## Sous windows gerer les chemins repertoires
creer un fichier .env avec "COMPOSE_CONVERT_WINDOWS_PATHS=1"

## Utilisation de portainer.io
### Lancer portainer 
*docker run -d -p 9000:9000 -v /var/run/docker.sock:/var/run/docker.sock portainer/portainer*

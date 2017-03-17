# Memo docker:
## Arrêter et supprimer tous les conteneurs
*docker rm $(docker ps -aq) -f*

## Se connecter en bash  à un container en fonctionnement
*docker exec -it [container-id] bash*

## Supprimer tous les reseaux existants
*docker network rm $(docker network ls -q)* 

(produira des erreurs sur les réseaux en fonctionnement ou ceux interne)

## Sous windows gerer les chemins repertoires
creer un fichier .env avec "COMPOSE_CONVERT_WINDOWS_PATHS=1"

#Memo docker:
##Arrêter et supprimer tous les conteneurs
*docker rm $(docker ps -aq) -f*

##Se connecter en bash  à un container en fonctionnement
*docker exec -it [container-id] bash*

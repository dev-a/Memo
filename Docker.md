#Memo docker:
##Arrêter et supprimer tous les conteneurs
*docker rm $(docker ps -aq) -f*

##se connecter en bash  à un container en fonctionnement
*docker exec -it [container-id] bash*

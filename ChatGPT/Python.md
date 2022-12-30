Pour créer un environnement virtuel Python, vous pouvez utiliser la commande `venv` intégrée à Python. Voici comment procéder :

 1. Ouvrez une fenêtre de terminal ou de commande.
 2. Assurez-vous d'avoir Python installé sur votre ordinateur. Si ce n'est pas le cas, vous pouvez le télécharger et l'installer à partir du site web officiel de Python : https://www.python.org/downloads/
 3. Naviguez jusqu'à l'emplacement où vous souhaitez créer votre environnement virtuel en utilisant la commande `cd`. Par exemple, si vous souhaitez le créer dans le répertoire "env" situé sur votre bureau, tapez :
```sh
 cd Desktop/env
```
 4. Exécutez la commande suivante pour créer un environnement virtuel nommé "monenv" :
```sh
python3 -m venv monenv
```
Remarque : si vous utilisez Python 2, utilisez la commande `python -m venv monenv` au lieu de `python3 -m venv monenv`.

Votre environnement virtuel Python est maintenant créé. Pour l'activer, utilisez la commande suivante :
```sh
source monenv/bin/activate
```
Vous devriez maintenant voir le nom de votre environnement virtuel entre parenthèses à gauche de votre invite de commande, comme ceci :
```sh
(monenv) user@machine:~/Desktop/env$
```
Vous pouvez maintenant utiliser pip (le gestionnaire de paquets Python) pour installer des paquets et des bibliothèques dans votre environnement virtuel. Par exemple, pour installer la bibliothèque numpy, utilisez la commande suivante :
```sh
 (monenv) user@machine:~/Desktop/env$ pip install numpy
```
Pour désactiver votre environnement virtuel, utilisez la commande `deactivate` :
```sh
(monenv) user@machine:~/Desktop/env$ deactivate
```
Vous pouvez maintenant utiliser votre environnement virtuel comme un espace de travail séparé pour votre projet Python, sans interférer avec les paquets et bibliothèques installés sur votre système global. Cela peut être utile pour éviter les conflits de versions de paquets ou pour travailler sur des projets qui nécessitent des versions spécifiques de bibliothèques.




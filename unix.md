# Memo Unix:

## Extraire chaque .zip dans un sous repertoire à son nom
> find -name '\*.zip' -exec sh -c 'unzip -d "${1%.\*}" "$1"' _ {} \\;



## commandes perso non structurée :

```shell
# on copie de fichier DEV.properties (qui traine et on le mets à la racine)
find . -name "*.bat" -printf 'cp %h/socle/*/contexts/DEV.properties  %h/params_tmp.properties \n' | sh
# on remplace par les bonnes valeurs du full_param.properties
find -name 'params_tmp.properties' -printf $'awk -F= \'NR==FNR{if(length($2)!=0)A[$1]=$2;next}$1 in A{$2=A[$1]}1\' OFS==  ./full_param.properties %h/params_tmp.properties > %h/param.properties\n' | sh
# on supprime les fichiers temporaires
find . -name 'params_tmp.properties' -printf 'rm %h/params_tmp.properties \n' | sh # -c echo $0
```

```shell
 for D in `find .  -maxdepth 1 -type d -name '*SIP'`
 do
 find $D  -name 'Postgres.properties'  -printf "cp %h/Postgres.properties $D/param.properties\n" | sh
 done
```

```shell
#rechercher les fichiers param.properties et les fusionner dans tmp_merge_param.txt
 find . -name 'param.properties' -exec cat {} \;  > tmp_merge_param.txt
 ```


## Afficher la date dans le shell
```shell
watch -n 1 date
 ```

```shell
while true; do clear; date; sleep 1; done
 ```

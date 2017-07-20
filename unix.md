# Memo docker:

## Extraire chaque .zip dans un sous repertoire à son nom
> find -name '\*.zip' -exec sh -c 'unzip -d "${1%.\*}" "$1"' _ {} \;

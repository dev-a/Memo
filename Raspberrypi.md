# Memo Raspberry-pi (raspbian)
## connaitre la tension en entrée du Rapsberry pi 
> vcgencmd measure_volts core
## modifier la résolution par défaut VNC
> sudo nano /boot/config.txt

on dé-commente
>framebuffer_width=1280

>framebuffer_height=720


## Installation d'Hadoop sur un raspberry pi (en cours)
### On télécharge Hadoop
> wget  http://apache.crihan.fr/dist/hadoop/common/hadoop-2.8.1/hadoop-2.8.1.tar.gz 

> tar xvf hadoop-2.8.1.tar.gz 

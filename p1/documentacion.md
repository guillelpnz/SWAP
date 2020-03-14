# Práctica 1 de Servidores Web de Altas Prestaciones

![Logo ugr](https://i2.wp.com/canal.ugr.es/wp-content/uploads/2017/07/logo-UGR-color-corporativo-vertical.jpg)

## Guillermo Lupiáñez Tapia



### Pasos seguidos para hacer la práctica:

Primeramente, lo que hice fue crear dos máquinas virtuales, de 1024MB cada una, e instalé en ellas Ubuntu Server 18 y LAMP.

A una de ellas, antes de arrancarla, le configuré la red. Para esto, creé una nueva red anfitrión y activé una segunda interfaz
en modo anfitrión en esa máquina. De esta forma, nos evitamos tener que configurar desde dentro de la máquina la red.

En la otra, arranqué directamente sin configurar la red. Por lo que tuve que editar el fichero "/etc/netplan/50-cloud-init.yaml".
Básicamente lo cambié de forma que fuese igual al fichero .yaml de la otra máquina. Posteriormente, apagué la máquina, configuré el
apartado de red de igual manera que había hecho con la primera máquina y volví a arrancarla. Por último ejecuté el comando:

`sudo netplan apply`

Este es el contenido de los ficheros .yaml:

![Ficheros .yaml](https://github.com/guillelpnz/SWAP/blob/master/p1/netplan.png)

Para comprobar la conectividad entre ambas máquinas hice ssh desde las dos máquinas:

![ssh](https://github.com/guillelpnz/SWAP/blob/master/p1/ssh.png)

Y también hice un curl con la propuesta de archivo .html del guion:

Desde m1 a m2:

![curl](https://github.com/guillelpnz/SWAP/blob/master/p1/curl%20de%20m1%20a%20m2.png)

Desde m2 a m1:

![curl](https://github.com/guillelpnz/SWAP/blob/master/p1/curl%20de%20m2%20a%20m1.png)

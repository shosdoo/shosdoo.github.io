---
layout: single
title: Comandos
date: 2024-07-12
classes: wide
header:
  teaser: /assets/images/bob.png
categories:
  - github
tags:
  - github
  - comandos
  - git
---

# Notas de comandos para recordar

![](/assets/images/moon.png)

----

## Git


`git init`

Este comando crea un nuevo repositorio y configura las herramientas que git necesita para comenzar a rastrear los cambios realizados en el proyecto

Un proyecto consta de 3 partes
directorio de trabajo donde se edita, elimina y organiza archivos
El area de preparacion donde enumera los cambios que realiza en el directorio de trabajo
Un repositirio, donde almacena permanentemente esos cambios como diferentes versiones del proyecto

`git status`

Cuando vamos escribiendo el script cambiara el contenido del directorio de trabajo, podemos comprobarlo con "git status"

`git add filename`

Para que git empieze a seguir los cambios es necesario agregar el archivo al area de preparacion con el comando "git add" y con git status ya nos empezara a reportar los cambios

`git diff`

Este comando nos sirve para ver diferencias entre el script una vez que este en seguimiento con git add, el signo + nos marcara los cambios que se han hecho, y con "git add filename" podemos agregar los nuevos cambios al area de preparacion

`git commit -m "Frase"`

Este comando nos permite agregar permanentemente los cambios al repositorio del area de preparacion, es necesario pasarle un mensaje de el tipo de cambio que se realiza 

`git log`

Esta opcion nos permite ver un historial de los cambios, donde incluira un hash en sha de 40 caracteres que indentifica la confirmacion, el autor, el mensaje de confirmacion y la fecha y hora


## Ejemplo:
 
1- Se realizaria un git init, el el directorio donde este el script

2- Una vez haya cambios, se realizara un git diff para ver si se realizaron, despues un "git add filename" para agregar al area de preparacion, y un git status para confirmar la modificacion

3- Despues de que se haya guardado la modificacion, realizamos un compromiso, con "git commit -m 'frase'"
agregando el comentario describiendo el cambio, y con git log podemos ir viendo los cambios realizados

====

`git show HEAD`

En git el compromiso mas actual se conoce como HEAD, para verlo podemos usar el comando "git show HEAD", la salida de este comando mostrara la salida de el comando git log, mas los cambios que se realizaron, como git diff

`git checkout HEAD filename`

En git cuando queremos cambiar una linea de el codigo ya que nos arrepentimos, podemos usar el comando de arriba, este nos funciona para mandarnos a una version anterior de el script, en caso de que no recordemos exactamente como era

`git add filename1 filename2`

Tambien podemos agregar varios archivos al area de preparacion en una sola linea una vez que hayamos modificado ambos

`git reset HEAD filename`

Este comando nos sirve para elminar un archivo de el area de preparacion en caso de que nos hayamos equivocado y enviarlo, ejemplo tenemos dos archivos, uno modificado correctamente y uno que borramos algo que nos importaba, hacemos un git add de ambos sin poner atencion, al hacer el comando de arriba, el archivo que enviamos por equivocacion lo quitara de el area de preparacion, no lo mandara a una version anterior, solo lo quita para poder corregirlo

`git reset <hash>`

En este comando podemos volver a una version en especifico de el script, haciendo un git log y obteniendo los primeros 7 caracteres de el hash sha, podemos hacer el comando de arriba y nos realizara el cambio

====

<https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet>

Hoja de trucos de markdown y algunos ejemplos:

markdown
\* italic
** bold
~ strike

title 
\====\
subtittle
\--------\
\# Title de mi documento


====

`git branch`

Este comando nos sirve para saber en que rama estamos, en la salida el asterisco * muestra la rama en que estamos

`git branch new_branch`

Es la estructura para poder crear una nueva rama

`git checkout new_branch`

Asi es para cambiar a la rama que queramos

`git merge filename`

Este comando nos sirve para fusionar un archivo en distintas ramas, por ejemplo estando en la rama master(main), podemos fusionarlo con las otras ramas con el comando

En caso de que hagamos commit de un mismo archivo en distintas ramas y con merge lo queramos fusionar, nos dara un error si es diferente la modificacion, para eso tendremos que ir al archivo donde nos mostrara las diferencias de cada rama y debemos elegir con cual quedarnos, HEAD sera la rama main, y el otro la rama que creamos

`git branch -d raiz_aEliminar \| o -D`

Con este comando eliminamos la rama que no queramos una vez que hayamos fucionado lo que nos interesa

Ejemplo, con git branch enumeramos las raiz, despues creamos una nueva con git branch "raiz_nueva", despues cambiamos a ella con 'git checkout raiz', una vez en esa raiz hacemos las modificaciones que queramos, una vez terminado hacemos un 'git add filename' y un 'git commit -m "comentario"', si aprueban nuestra modificacion, en la rama master(main) lo que haran es fusionarlo, con el comando 'git merge raiz', y de esta manera si es que no hay conflictos en modificaciones para la fusion, se agregara lo de la nueva rama a la rama master(main)


====

## Control remoto

`git clone`

Este comando nos permite copiar un repositorio remoto a nuestra maquina

`git remote -v`

Este comando nos sirve para ver la ruta origen de el repositorio que clonamos

`git fetch`

este comando nos sirve para ver si se han realizado actualizaciones de el repositorio remoto

`git merge origin/master`

Este comando nos sirve para fusionar la rama que realizo los cambios en el origin a nuestra rama master en el repositorio clonado

`git push \| git push origin main`

Este comando nos permite agregar nuestro poyecto de la rama que creamos a el origin de el repositorio creado

====

`git rebase`

`git fork`

Sirve para clonar un repositorio y trabajar sobre el, en caso de que queramos contribuir tambien se puede

`git fesh upstream`

`git pull`

Nos sirve para mantener actualizado nuestro repositorio local de los cambios de el remoto

`git reflog`

Este comando nos permite recuperar el hash de algun commit que hayamos borrado
 y ya solo hariamos un 

`git reset --hard \<hash\>`

## Creacion de alias

`git config --global alias.log-mejorado "comando"`

Ahora solo hariamos un 

`git <comando>`

y se ejecutara

## Gitignore
Sirve para decir que archivos ignorar, por ejemplo para que no suba archivos que no queramos que esten dentro de el directorio de trabajo, solo funciona para archivos que nunca fueron subidos antes
Por ejemplo para ignorar distintos archivos de una misma extension con:
### *.txt
Aqui ignora todo lo que termina en .txt

### !ola.txt
No ignora este archivo exclusivamente

### dire/
Ignora todo lo de un directorio

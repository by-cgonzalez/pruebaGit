# ¿Qué es Git, para qué se usa y qué resuelve?

Git es un sistema de control de versiones que nos permite llevar un histórico sobre los cambios de nuestro proyecto, no es el único sistema de control de versiones, pero sí el más usado. Fue creado por Linus Torvalds.  **Git y GitHub no son lo mismo**, uno es el sistema de control de versiones y el otro es la red social de programadores.

Los repositorios son una estructura de datos que almacenan información sobre archivos y directorios. Es el inicio de todo proyecto con Git, dentro de un repositorio encontraremos  **ramas**, no son más que la duplicación de un objeto bajo un repositorio, permite trabajar en paralelo para al final unir los cambios.

## Verificar versión de Git
Antes de que instalemos Git es necesario que revisemos si ya está instalado en nuestro sistema, por lo general en los sistemas operativos basados en Unix está instalado (MacOS o Linux); para verificar escribimos en la terminal de comandos:

```sh
$ git --version
git version 2.17.2
```
Si el comando aparece y retorna una versión quiere decir que fue está instalado dentro del sistema y no necesita hacerse una instalación.

## Instalar Git en Windows

Es como instalar una aplicación más en Windows, el instalador lo consigues acá  [https://gitforwindows.org](https://gitforwindows.org/), debes descargarlo y abrirlo. Allí se te abrirá una ventana de instalación y solo debes seguir los pasos que te diga.  
Git nos instala una terminal que se llama git shell esto es una terminal distinta a la que trae el sistema operativo, es muy similar a la que podríamos tener en Unix, incluso puede ser un reemplazo de Hyper o de la terminal de Ubuntu.

## Configurar Git

La configuración que haremos es poner dentro de git nuestro nombre y correo electrónico, para que de esta manera todo lo que hagamos esté de cierta forma “firmado” con nuestros datos. Debemos irnos a la terminal de comandos y ejecutar:  }

```sh
$ git config --global user.name "Carlos Gonzalez"
$ git config --global user.email "carlos@gonzalez.cl"
```
Allí deberás completar tu información personal, esta que acabamos de poner es solo de ejemplo, no es real.


## Cómo crear un repositorio, primer commit, reset y logs

Aprende el flujo básico de Git: crear un repositorio, crear un commit y ver un histórico de los commits.

Para comenzar con un nuevo repositorio en Git debemos correr el siguiente comando:
```sh
$ git init
```
Al correr el comando nuestra terminal nos va a mostrar que nos encontramos dentro de la rama master, la rama principal de todo proyecto en Git. Además, si ejecutamos  `ls -la`  veremos que hay una carpeta oculta llamada “.git”.

Todo cambio tiene varios estados dentro de Git:
-   Sin seguimiento
-   Sin cambios
-   Con cambios
-   En stagging

Para ver el estado del repositorio ejecutamos el comando  `git status`. Podemos añadir un archivo con el comando  `git add <nombre del archivo>`, una vez lo tenemos añadido podemos dar commit con el comando  `git commit -m <mensaje del commit>`. Con  `git log`  podemos visualizar un histórico de los commits.

Dentro de Git es posible regresar entre commits con el comando  `git reset`, tenemos dos opciones para regresar:

-   `--soft`: vamos a movernos al commit que le indiquemos, sin eliminar los commits de por medio.
-   `--hard`: nos movemos al commit que indiquemos y regresamos el repositorio al estado del commit, borrando todos los commits de por medio.

## Ramas, rebase y merge

Recuerda que una rama es la duplicación de un objeto sobre el repositorio y nos va a permitir trabajar en paralelo para después unir los cambios a nuestro proyecto, en este caso a nuestra rama master, los comandos principales son:

-   `git checkout -b develop`: según el commit en el cual ejecutemos este comando va a ser el punto en el cual se va a crear una rama idéntica, en este caso con el nombre de “develop”.
-   `git merge develop`: va a añadir los commits a la rama master.
-   `git rebase develop`: va a añadir los commits a la rama master unificando ambas ramas y conservando la historia de la misma.

# Github: configuración, repositorio remoto, push y pull

GitHub es la red social de programadores, como todo buen programador necesitas desplegar tus proyectos desde la terminal, para ello debes añadir una llave SSH a tu cuenta de GitHub. Dentro de GitHub crear un repositorio es bastante rápido y sencillo, puedes elegir si va a ser un repositorio público o privado y el tipo de licencia que va a tener tu proyecto, si es un proyecto open source lo mejor es añadir una licencia MIT.

## Cómo escribir un buen README

No hay un estándar sobre cómo escribir un buen README, cada proyecto es diferente y depende de cada uno. Pero hay ciertas partes que sí o sí debería contener un buen README.

1.  Nombre: Especificamos cómo se llama nuestro proyecto.
    
2.  Descripción: es donde diremos para qué exactamente es el proyecto, qué problemas resuelve y cualquier información relevante.
    
3.  Instalación: muestra los pasos específicos para instalar el proyecto. Por lo general se muestra un pedazo del código necesario para la instalación.
    
4.  Cómo usar: describe rápidamente casos de uso en los cuales se puede usar el proyecto, además de mostrar funcionalidades.
    
5.  Cómo contribuir: si es un proyecto open source se describe acá la forma en la que deberían crearse las contribuciones.
    
6.  Licencia: muestra la licencia que tiene el proyecto.  
    En formato markdown podemos escribir cada uno de los items de esta manera:

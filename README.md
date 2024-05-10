# APUNTES CURSO GIT/GITHUB SCESI 
![alt](https://media.licdn.com/dms/image/C561BAQEF5kPCrx_iQA/company-background_10000/0/1583926086892?e=2147483647&v=beta&t=Ejy1pJNHdYyknShdfCVbohGdW6bBQXGBhCcehD7VmlA)
# Clase 1:
## Que es un Controlador de Versiones?
Es un sistema que regitra cada cambio que se hace al codigo fuente de un proyecto en un repositorio.
Esto permite un historial detallado:
* **Que se hizo**
* **Quien lo hizo**
* **Cuando lo hizo**

![alt](https://dinahosting.com/blog/upload/2018/06/Control-de-versiones.jpg)
> VENTAJAS
> * **Cada cambio realizado no implica una copia de todo el proyecto**
> * **Rendimiento:** Solo se guarda lo necesario
> * **Seguridad:** Conserva toda accion
> * **Flexibilidad:** No es necesario un desarrollo **lineal**
## Ques es Git?
Es un controlador de versiones que permite trabajar localmente en un proyecto que esta distribuido entre varias personas que desarrollan un proyecto de software de manera remota.
> *"Cada quien trabaja en una parte del proyecto localmente y los cambios importantes se suben a un repositorio remoto donde se encuentra el proyecto"*
> ![alt](https://www.nettix.com.pe/wp-content/uploads/2020/02/img-1024x511.png)
**Un repositorio es un carpeta donde se almacena un proyecto con sus respectivos cambios y su historico. Estos repositorios pueden ser Locales o Remotos**
# INICIAR UN PROYECTO CON GIT
Para iniciar un proyecto con git se debe seleccionar una carpeta que se convertira en el repositorio. Todos archivos que contenga esta carpeta seran los elementos que componen al proyecto. Existen dos maneras para iniciar nuestro proyecto con Git:
1. `$ git init <nombreArchivoProyecto>`
   
   `$ cd <nombreArchivoProyecto>`


2. `$ cd <nombreArchivoProyecto>`
   
   `$ git init` 

>*Se crea una carpeta que tendra el identificador `(MAIN)`, esto indica que el archivo es el repositorio principal de nuestro proyecto.*

   ![alt](https://www.espai.es/blog/wp-content/uploads/2021/05/rama-master-con-commit-git-1.jpg)

## COMMITS Y SUS ESTADOS
Un commit es una modificacion o agregacion que se hace a un proyecto.

> *Como se menciono anteriormente, no se debe hacer una copia de todo el proyecto para añadir una modificacion. Lo que hace git es identificar solo la parte modificada y añadirlo al proyecto principal, mediante un commit*

Para saber el estado de un archivo se utiliza el siguiente comando:
`$git status`
### MODIFIED: 
Un archivo ha sido creado, eliminado o modificado dentro el repositorio. `Git` identifica esto y lo marca en color rojo como:
* `Modified` si existe una modificacion
* `Untracked` si un archivo se crea o añade
### STAGED:
Utilizando el comando `$git add <archivo.ext>` el archivo pasa a un estado de `Stage`. Este estado indica que el archivo se encuentra **PREPARADO** para realizar un commit y guardar los cambios en el repositorio principal del proyecto. 
`$ git add .` para añadir todos los archivos de la carpeta a `Stage`*(esto puede ser una mala practica a veces, pues habra circunstancias donde NO todas las modificaciones seran añadidas)* 

`$ git restore --staged <archivo>` saca al archivo del area de stage.

`$ git restore --staged .` saca todos los archivos del area de stage.
### COMMITED:
El comando `$ git commit` guarda finalemente el archivo en el repositorio principal del proyecto (local o remoto), *`"Es como guardar un checkpoint en un juego"`*. Al ejecutar un commit, se debe añadir una descripcion clara sobre que se hizo en el commit con respecto al proyecto. Para esto, git abre una ventana emergente donde se pide añadir esa descripcion. Otra forma de realizar esto es `$ git commit -m "descripcion del Commit"`

`$git commit --amend - m "descripcion"` permite reescribir el ultimo commit

![alt text](image.png)

`$ git log` muestra el historial de los commits, donde en primer lugar se encuentra el ultimo commit(HEAD) realizado y en ultimo lugar se encuentra el primer commit ejecutado del proyecto o rama.
> `(HEAD)` indica la posicion o commit actual en la que estamos. 
> Podemos movernos entre commits:
> 
> `$git checkout <nombreRama o hashCommit>`:Permite cambiar de rama incluso si tienes cambios sin confirmar
>
> `$git switch <nomreRama o hashCommit>`:No permite cambiar de rama si tienes cambios sin confirmar
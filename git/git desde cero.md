# Git desde cero



[TOC]



## Fundamentos de git 

https://git-scm.com/book/es/v2/Inicio---Sobre-el-Control-de-Versiones-Fundamentos-de-Git



## ¿Que es Git?

Es un sistema de control de versiones que originalmente fue diseñado para operar en un entorno Linux. Actualmente git es multiplataforma, es decir que ahora ya no solamente es compatible con Linux sino también MacOS Windows.

## Beneficios

> * Trabajo colaborativo
> * Ayuda en conflictos 
> * puedes llevar todo los registros de todo los cambios y avances de tu proyecto
> * Funciona como una máquina del tiempo puedes ir al pasado de tu código o volver al presente
> * Git trabaja con ramas ayuda a que varias personas en un mismo proyecto y puedan hacer modificaciones sin afectar a los demás 

## Instalación de git 

> https://git-scm.com/downloads
>
> descargar e instalar  y todo siguiente 

## Git status

> - `Working directory`: el área de trabajo, en este estado están esos archivos se modificaron 
> - `staging area`: Se les prepara los archivos para ser incluidos en el repositorio.  
> - `repository`:   Los archivos son incluidos al repositorio con el uso de commints.
>
> Mas información https://git-scm.com/book/en/v1/Getting-Started-Git-Basics

## Flujo de trabajo de git 

> 1. Modificas una serie de archivos en tu directorio de trabajo 
> 2. Preparas los archivos, añadiéndolos a tu área de preparación 
> 3. Confirmas los cambios, lo que toma los archivos tal y como están en el área de preparación y almacena esa copia Instantánea de manera permanente en tu directorio de Git    



## Comando  básicos de la terminal 

> * `cd nombre_carpeta`: para ingresar a una carpeta
>
> * `cd ..`: para salir de una carpeta 
>
> * `mkdir nombre_carpeta`: para crear una carpeta 
>
> * `touch file.txt`: para crear un archivo 
>
> * `vim file.txt`: para editar un archivo, a  guardar el archivo presiona `"Esc"` y digita el comando `":wq"` para guardar y salir y para salir sin guardar digitar el comando `":q!"`
>
> * `clear`: limpiar la consola 
>
> * `rm -fr carpeta`: Forzar par borrar una carpeta 
> * `cat archivo.txt`: para ver la información de un archivo 
>



## Comando para obtener ayuda

> * `git help `: Para obtener ayuda  sobre algunos comandos
> * `git help --all`: Para ver todos los comandos de git 
> *   `git help  <verb>` : Para obtener ayuda o información sobre algún comando de git por ejemplo `git help config`

## Config

> Para registrarte en git 
>
> * `git config`: Para configurar 
>* `git config --system user.name 'nombre_usuario'` : Para configurar todo el sistema con un solo usuario
> * `git config --global user.name 'nombre_usuario'`:  Este es el recomendado para configurar el nombre del usuario 
>* `git config --global user.email correlectronico@gmail.com`:  Para configurar el correo electrónico del usuario 
> * `git config --global core.editor vim`: También podemos asignar el editor para editar  los archivos del proyecto  
>* `git config --list`: Para mostrar toda la información de todo el registro anterior 
> 
>
> 



## Inicializar un proyecto 

> Inicializar un proyecto  para ello tenemos que estar ubicados en los archivos mas altos del proyecto para poder inicializar un proyecto  y allí abrimos nuestra terminal  y digitamos el siguiente comando 
>
>  ```bash
>git init
> ```
> 
> 



##  Trabajando con los Comandos de git 

> * `git status`: Para ver el estado de nuestros archivos  y en que área de estado están si están en el área de   working o staging o en el directorio 
>
>   > ```bash
>   > git status 
>   > git status -s // para ver en que area o estado se encuentras nuestros archivos 
>   > ```
>
> * `git diff name_archive`: Permite mostrar la diferencia de los cambios de archivos antes que se agreguen al estado de staging  o al estado de preparación  
>
>   > ```bash
>   > // este git dif solo funciona  en los archivos que no los as agregado aun al área de staging 
>   > git diff index.html | f8df4c0
>   > git diff --staged // y si quieres ver la direferncia de los archivos que estan el area de staging con archivos del repositorio usa este comando 
>   > git diff --cached 
>   > ```
>   >
>   > 
>
> * `git log`: Nos muestra el historial de todos los commit que se hizo en el  proyecto
>
>   >  Este  comando tiene sub comando para trabajar
>   >
>   >  ```bash
>   >  git log -p -2 // Este comando nos muestra las direfencias de cambios de cada commit y le estamos indicando que nos muestre los 2 ultimos registros 
>   >  git log --stat // Nos muestra estadisticas sobre los archivos modifcados en cada información .
>   >  git log --shortstat // Muestra solamente la linea de resumen de la opción  --stat
>   >  git log --name-only // Muestra la lista de archivos afectados
>   >  git log --name-status // solo me muestra que paso en cada archivo por ejemplo algunos se an modificado y otros se an eliminado
>   >  git log --abbrev-commit //Muestra solamente los primeros carcateres de la suma SHA-1 en vez de los 40 caracteres de que compone 
>   >  --graph //Muestra un Gráfico ASCII con la historia  de ramificacion y uniones 
>   >  --pretty= //Muestra las configuraciones usando un formato alternativo. Posibles opciones son oneline, short, full, fuller y format (mediante el cual puedes especificar tu propio formato)
>   >  
>   >  //Comandos que utilizaremos mas sobre git log 
>   >  
>   >  git log --oneline -2 // que nos muestre los commit de forma resumida
>   >  git log --oneline --graph // para mostrar los graficos de las ramificaciones 
>   >  git log --pretty=format:"%h - %an: %s" 
>   >  git log --since (desde)
>   >  git log --since=2.hour | minutes | day |weeks | years | "2008-01-15" 
>   >  git log --after (despues de)
>   >  git log --until, --before (hasta) antes de tal fecha
>   >  git log --since=2018-09-00 --until 2018-11-00
>   >  git log --after='2019-06-10' | git log --after '2019-06-10'
>   >  
>   >  git log --author 'correo@gmail.com' // para filtrar solo los commit de alguien
>   >  git log --grep 'palabra clave' // para buscar dentro de los commit una palabra clave
>   >  git log -S' .dev .ed-grid ' | -Sfunctiona_name // para decirle quienes modificaron estas lineas de códigos 
>   >  
>   >  los formatos que puedas pasar para pretty estan aqui 
>   >  
>   >  %H = Hash de la confirmación
>   >  %h = Hash de la confirmación abreviado
>   >  %T = Hash del árbol
>   >  %t = Hash del árbol abreviado
>   >  %P = Hashes de las confirmaciones padre
>   >  %p = Hashes de las confirmaciones padre abreviados
>   >  %an = Nombre del autor
>   >  %ae = Dirección de correo del autor
>   >  %ad = Fecha de autoría (el formato respeta la opción -–date)
>   >  %ar = Fecha de autoría, relativa
>   >  %cn = Nombre del confirmador
>   >  %ce = Dirección de correo del confirmador
>   >  %cd = Fecha de confirmación
>   >  %cr = Fecha de confirmación, relativa
>   >  %s = Asunto 
>   >  
>   >  // y para utilizarlo ya sabemos 
>   >  git log --pretty=format:"%h - %an: %s"
>   >  //combinacion de comandos
>   >  git log --pretty="%h - %s" --since="2018-10-01"    --before="20178-11-01"
>   >  ```
>
> * `git commit --amend` : Para deshacer  cambios que hayas echo por, ejemplo que te equivocaste al momento de ingresar el asunto del commit 
>
>   > ```bash
>   >  git commit --amend //Con esto podras editar ese ultimo commit pero esto te abrira el editor vim y si quieres omitir esto digite el siguiente comando. 
>   >  
>   > // y si no sabes como funciona vim esto lo encontraras en las primeras líneas de comando básicos de la terminal 
>   >  
>   >  git commit --amend -m "El nuevo mensaje que tendra"
>   >  
>   > ```
>
> * `git reset <file>`: Para deshacer cosas 
>
>   > ```bash
>   > git reset index.html //Para sacar un archivo específico del area staging 
>   > git reset --soft cb61e7c // Para resetear un proyecto de un commit especifico Nota: estos archivos seran trasladados al staging area 
>   > git reset --mixed cb61e7c // Estos archivos incluidos en el commit serán trasladados al working directory en español al area de trabajo 
>   > git reset --hard cb61e7c //Estos archivos incluidos en el commit serán eleminados permanentemente 
>   > ```
>   >
>   > 
>
> * `git rm --cached <file>` : para cancelar todo los archivos del área staging
>
>   > ```bash
>   > git rm --cached index.html // tenemos que ingresar que archivo queremos cancelar del estado de staging
>   > git rm -f index.html //Para eleminar un archivo permanente del proyecto
>   > ```
>   >
>   > 
>
> * `git add -A o .` : Para agregar los archivos al área de staging 
>
>   > ```bash
>   > git add name.txt // para agregar algo específico al area staging
>   > git add -A  // para agregar todo los archivos  que estan en el área de trabajo
>   > git add . // tambien es igual agrega todo
>   > ```
>
> * `git commit `: para pasar los archivos del estado de staging al repositorio principal o ala rama principal  registrando con puntos en el siclo de vida de nuestro proyecto, e indicándolo que cambios se esta realizando 
>
>   > ```bash
>   > git commit  // Por defecto esto nos abrira un editor como vim
>   > git commit -v // Este es parecido al primero pero este te muestra  los cambios mas detallado dentro del editor 
>   > git commit -m "mensaje de commit" // Esta es la forma clásica de hacer commits
>   > git commit -a // si quieres saltarte el paso de git add
>   > git commit -a -m "mensaje de commit "// Nos permite saltarnos el git add y de ingresar el registro en el editor
>   > ```
>   >
>   > 
>
> * `git checkout`: Para moverse en el tiempo de línea del proyecto 
>
>   > ```bash
>   > git checkout a28245f // nos podemos mover mediante los commic  ingresando codigos de los commic, y regresamos en el tiempo como estabamos y cambia todo los commic el contenido del archivo 
>   > 
>   > git checkout v1.0 // para moverse mediante tags
>   > 
>   > ```
>
> * `git clone`:  nos permite  clonar un proyecto de GitHub parar poder contribuir 
>
>   > ```bash
>   > git clone https://github.com/escueladigital/EDgrid.git
>   > ```
>
> * `git remote` : ramas la remotas nos muestra desde donde se esta utilizando ese proyecto 
>
>   > ```bash
>   > git remote --v
>   > 
>   > // y la respuesta seria esta 
>   > 
>   > origin  https://github.com/escueladigital/EDgrid.git (fetch)
>   > origin  https://github.com/escueladigital/EDgrid.git (push)
>   > 
>   > ```
>   >
>
>   
>
> * `git fetch`: nos permite actualizar los cambios nuevos del proyecto que se esta utilizando en el repositorio pero eso solo nos trae la rama del  proyecto si queremos con todos los cambios actualizados necesitamos el siguiente comando 
>
> * `git pull origin master`: para traernos todos los cambios del proyecto  y que todo esta al día 
>
>   >```bash
>   >    git pull origin master 
>   >```
>
> * `git checkout -b nombre_rama`: lo que nos permite hacer esto es  crear una rama  de un punto y poder corregir algún error anterior 
>
>   > ```bash
>   > git checkout -b desarrollo  // para crear y moverse a esa rama
>   > ```
>
> * `git checkout master`: para moverse entre ramas 
>
>   > ```bash
>   > git checkout master // para moverse entre ramas tenermos que ingresar el nombre de la rama 
>   > 
>   > git branch // para mostrar las ramas que existen 
>   > git checkout -- <file.text>
>   > ```
>
> * `git merge nombre_rama`: esto es muy importante a la hora de mezclar ramas, es que tenemos que estar posicionados en la rama principal donde queremos jalar la rama 
>
>   > ```bash
>   > // por ejemplo esta mi rama que cree a partir de la rama master 
>   > HP@DESKTOP-K8FBM90 MINGW64 /c/xampp/htdocs/gitDesdeCero (desarrollo) // esta rama se llama desarrollo y aqui hice mis cambios y agrege nuevos archivos  y si quiero mezclar todo estos cambios a la rama principal tenemos que posiconarnos en la rama principal que es master y nos movemos con git checkout master 
>   > y desde alli podemos ejecutar este comando 
>   > git merge desarrollo
>   > 
>   > ```
>   > 
>   
>   * `git branch`: Para mostrar las ramas 
>
> *  `git branch -D nombre_rama`: esto es para eliminar una rama principal 
>
>   > ```bash
>   > git branch -D desarrollo
>   > ```
>
> * `git mv old_name new_name`: Para renombrar un archivo 
>
>   >
>   >
>   >```bash
>   >git mv main.css main3.css // pero para hecer esto el archivo tiene que estar sin modificaciones es decir no tiene que estar en el área de working 
>   >
>   >```
>   >
>   >





## Integrar proyecto local con GitHub

> 1. para esto tenemos que crear un llave publicó 
>
>    ```bash
>    ssh-keygen -t rsa #comando para generar la llave del repositorio
>    
>    ```
>
>    
>
> ```bash
> ssh-keygen -t rsa // comando para generar el la llave del repositorio
> // y seria algo asi 
> 
> Generating public/private rsa key pair.
> Enter file in which to save the key (/c/Users/HP/.ssh/id_rsa):
> /c/Users/HP/.ssh/id_rsa already exists.
> Overwrite (y/n)? y
> Enter passphrase (empty for no passphrase):
> Enter same passphrase again:
> Your identification has been saved in /c/Users/HP/.ssh/id_rsa.
> Your public key has been saved in /c/Users/HP/.ssh/id_rsa.pub.
> The key fingerprint is:
> SHA256:7gkKfP6Mpc+IJ2dSp4NNJ6s9DLSLR5ncREXm+URnI34 HP@DESKTOP-K8FBM90
> The key's randomart image is:
> +---[RSA 2048]----+
> |     o+ o +      |
> |    .o + + .     |
> |   .  o o E      |
> |  . .  o .       |
> | o *    S        |
> | .B = o.         |
> | ooO.*o .        |
> |. **@O o .       |
> | .oBB== o        |
> +----[SHA256]-----+
> 
> ```
>
> 2. agregar la llave publica ala cuenta de git  
>
> 3. conectar con el proyecto local 
>
>    > ```bash
>    > 
>    > 
>    > ```
>
> * `git pull origin master`: para traernos todo el contenido del repositorio 
>
>   > ```bash
>   > git pull origin main
>   > ```
>   
> * `git push origin master`: para agregar todo los nuevos archivos al repositorio 



## Trabajar con remotos 

> -  `git remote -v` : Te muestra los repositorios a los que puedes trabajar remotamente
>
> - `git remote add [nombre][url]`: Para añadir repositorios remotos 
>
>   > ```bash
>   > git remote add origin https://github.com/JerryApazaYllatupa/claseFinalGit
>   > // y de esta forma podemos añadir un repositorio remoto a  nuestro local 
>   > ```
>   >
>   > 

## GitIgnore

esto es el nuevo contenido 
este es el cambio desde la web



# El error de Git "fatal: negarse a fusionar historias no relacionadas"

GitErrorGit PullHistorias no relacionadasGit Merge

![Equipo Edpresso](https://www.educative.io/cdn-cgi/image/f=auto,fit=cover,w=32,h=32/v2api/author/profile/6547532599525376/image/5933301341618176)

Equipo Edpresso







------

El error de Git **“fatal: negarse a fusionar historias no relacionadas”** ocurre cuando se fusionan dos proyectos *no relacionados* (es decir, proyectos que no son conscientes de la existencia del otro y tienen historiales de confirmaciones que no coinciden).

![visor de svg](https://www.educative.io/api/edpresso/shot/4755609222119424/image/5534126872461312)

Considere los siguientes dos casos que arrojan este error:

- Ha clonado un proyecto y, de alguna manera, el `.git`directorio se eliminó o se corrompió. Esto hace que Git desconozca su historial local y, por lo tanto, generará este error cuando intente *presionar* o *extraer del* repositorio remoto.
- Ha creado un nuevo repositorio, le ha agregado algunas *confirmaciones* y ahora está intentando *extraer* de un repositorio remoto que ya tiene algunas confirmaciones propias. Git también arrojará el error en este caso, ya que no tiene idea de cómo se relacionan los dos proyectos.

## Solución

El error se resuelve alternando el interruptor *permitir-historiales no relacionados* . Después de un comando `git pull`o `git merge`, agregue la siguiente etiqueta:

```git
git pull origin master --allow-unrelated-histories
```



**Nota:** Ten en cuenta que este artículo es un tanto avanzado, pensado para personas que ya trabajan con Git. Puedes aprender cosas más básicas que damos por sabidas aquí en el [Manual de Git](https://desarrolloweb.com/manuales/manual-de-git.html).

## Git branch

El comando `git branch` es el que usaremos principalmente para trabajar con la creación de ramas, borrado de ramas y demás. Sin embargo, no es el único comando para la operativa que veremos en este artículo, ya que existen otros subcomandos de Git útiles y necesarios para trabajar con ramas, como `checkout` para moverse entre ramas o `merge` para fusionar ramas.

Puedes comenzar tu primera práctica para trabajar con ramas. Haremos algo tan sencillo como lanzar el comando "`git branch`" a secas. Esto nos dará el listado de ramas que tengamos en un proyecto. Pero hay que advertir que las ramas de un repositorio local pueden ser distintas de las ramas de un repositorio remoto. Por ejemplo, cuando clonas un repositorio de GitHub generalmente estás clonando únicamente la rama master y no todas las ramas que se hayan creado a lo largo del tiempo. Otro ejemplo es cuando creas una rama en tu repositorio local. En este caso la rama la tendrás simplemente en tu proyecto local y no se subirá al repositorio remoto hasta que no lo especifiques. Ovbiamente, todas estas cosas, y otras, son las que vamos a ver en este artículo.

## La rama master

Cuando inicializamos un proyecto con Git automáticamente nos encontramos en una rama a la que se denomina "master".

**Puedes ver las rama en la que te encuentras** en cada instante con el comando:

```git
git branch
```

Esta rama es la principal de tu proyecto y a partir de la que podrás crear nuevas ramas cuando lo necesites.

Si has hecho algún commit en tu repositorio observarás que después de lanzar el comando "git branch" nos informa el nombre de la rama como "master".

![img](https://desarrolloweb.com/archivoimg/general/3976.png)

**Nota:** Si no has hecho un commit en tu proyecto observarás que no se ha creado todavía ninguna rama y que el comando branch no produce ninguna salida.

## Crear una rama nueva

El procedimiento para crear una nueva rama es bien simple. Usando el comando branch, seguido del nombre de la rama que queremos crear.

```git
git branch experimental
```

Este comando en sí no produce ninguna salida, pero podrías ver las "branches" de un proyecto con el comando "`git branch`", u obtener una descripción más detallada de las ramas con este otro comando:

```git
git show-branch
```

Esto nos muestra todas las ramas del proyecto con sus commits realizados. La salida sería como la de la siguiente imagen.

![img](https://desarrolloweb.com/archivoimg/general/3977.png)

## Pasar de una rama a otra

Para moverse entre ramas usamos el comando `"git checkout`" seguido del nombre de la rama que queremos que sea la activa.

```git
git checkout experimental
```

esta sencilla operación tiene mucha potencia, porque nos cambiará automáticamente todos los archivos de nuestro proyecto, los de todas las carpetas, para que tengan el contenido en el que se encuentren en la correspondiente rama.

De momento en nuestro ejemplo las dos ramas tenían exactamente el mismo contenido, pero ahora podríamos empezar a hacer cambios en el proyecto experimental y sus correspondientes commit y entonces los archivos tendrán códigos diferentes, de modo que puedas ver que al pasar de una rama a otra hay cambios en los archivos.

Si estando en la rama experimental haces un par de commit, observarás que al hacer el show-branches te mostrará nuevos datos:

![img](https://desarrolloweb.com/archivoimg/general/3978.png)

El comando checkout tiene la posibilidad de permitirte crear una rama nueva y moverte a ella en un único paso. Para crear una nueva rama y situarte sobre ella tendrás que darle un nombre y usar el parámetro -b.

```git
git checkout -b otrarama
```

Como salida obtendrás el mensaje Switched to a new branch 'otrarama'. Eso quiere decir que, además de crear la rama, nuestra cabecera está apuntando hacia esta nueva branch.

Si te dedicas a editar tus ficheros, crear nuevos archivos y demás en las distintas ramas entonces podrás observar que al moverte de una a otra con `checkout` el proyecto cambia automáticamente en tu editor, mostrando el estado actual en cada una de las ramas donde te estás situando. Es algo divertido y, si eres nuevo en Git verás que es una magia que resulta bastante sorprendente.

Como estás entendiendo, el proyecto puede tener varios estados en un momento dado y tú podrás moverte de uno a otro con total libertad y sin tener que cambiar de carpeta ni nada parecido. Si usas un programa de interfaz gráfica de Git, como SourceTree o cualquier otro, podrás ver las ramas en un esquema gráfico más entendible que en la consola de comandos.

![img](https://desarrolloweb.com/archivoimg/general/3979.png)

## Fusionar ramas

A medida que crees ramas y cambies el estado del las carpetas o archivos tu proyecto empezará a divergir de una rama a otra. Llegará el momento en el que te interese fusionar ramas para poder incorporar el trabajo realizado a la rama master.

El proceso de fusionado se conoce como "merge" y puede llegar a ser muy simple o más complejo si se encuentran cambios que Git no pueda procesar de manera automática. Git para procesar los merge usa un antecesor común y comprueba los cambios que se han introducido al proyecto desde entonces, combinando el código de ambas ramas.

Para hacer un merge nos situamos en una rama, en este caso la "master", y decimos con qué otra rama se debe fusionar el código.

El siguiente comando, lanzado desde la rama "master", permite fusionarla con la rama "experimental".

```git
git merge experimental
```

Un merge necesita un mensaje, igual que ocurre con los commit, por lo que al realizar ese comando se abrirá "Vim" (o cualquioer otro editor de consola que tengas configurado) para que introduzcas los comentarios que juzgues oportuno. Salir de Vim lo consigues pulsando la tecla ESC y luego escribiendo ":q" y pulsando enter para aceptar ese comando. Esta operativa de indicar el mensaje se puede resumir con el comando:

```git
git merge experimental -m 'Esto es un merge con mensaje'
```

En la siguiente imagen puedes ver una secuencia de comandos y su salida. Primero el cambio a la rama master "git checkout master", luego el "git branch" para confirmar en qué rama nos encontramos y por último el merge para fusionarla con la rama experimental.

![img](https://desarrolloweb.com/archivoimg/general/3980.png)

Luego podremos comprobar que nuestra rama master tiene todo el código nuevo de la rama experimental y podremos hacer nuevos commits en master para seguir el desarrollo de nuestro proyecto ya con la rama principal, si es nuestro deseo.

Si tenemos un programa de Git por interfaz gráfica podremos ver el diagrama con el combinado de las ramas.

![img](https://desarrolloweb.com/archivoimg/general/3981.png)

### Fusionar los cambios de master en la rama en desarrollo

Durante tu trabajo en el desarrollo del proyecto gestionado con Git también puede ser normal que se vayan haciendo cambios en la rama master, o en otras ramas en desarrollo, y quieras traerlos para tu rama actual. Por ejemplo, la rama experimental está tardando varios días o semanas en completarse y mientras tanto han agregado nuevas features que quieras que esté disponibles también en la rama experimental.

Entonces seguramente querrás traerte los cambios de la rama master. Para ello, estando en la rama experimental, puedes lanzar el siguiente comando.

```git
git merge master -m 'Un mensaje del merge de master en el branch experimental'
```

Ya lo tienes! ahora tu rama está actualizada con todos los cambios en master. Puedes seguir desarrollando tu rama experimental sabiendo que tienes el proyecto actualizado.

## Subir una rama al repositorio remoto (Github o similares)

Como habíamos dicho anteriormente, por mucho que hagas la operativa descrita para crear ramas en tu ordenador, y las puedas ver en tu repositorio local con `git branch`, las ramas no se publicarán en Github o cualquier otro hosting de repositorios remoto. Para que esto ocurra tienes que realizar específicamente la acción de subir una rama determinada.

La operativa de publicar una rama en remoto la haces mediante el comando `push`, indicando la opción "-u" y el nombre de la rama que deseas subir. Por ejemplo de esta manera:

```git
git push -u origin experimental
```

Así estamos haciendo un push, empujando hacia origin (que es el nombre que se suele dar al repositorio remoto), la rama con nombre "experimental".

Por cierto, si subimos el proyecto a Github podremos ver también un diagrama de las ramas que hemos ido creando y fusionando a master, en la sección Graps / Network.

![img](https://desarrolloweb.com/archivoimg/general/3982.png)

## Borrar una rama

En ocasione puede ser necesario eliminar una rama del repositorio, por ejemplo porque nos hayamos equivocado en el nombre al crearla. Aquí la operativa puede ser diferente, dependiendo de si hemos subido ya esa rama a remoto o si todavía solamente está en local.

### Borrado de la rama en local

Esto lo conseguimos con el comando git branch, solamente que ahora usamos la opción "-d" para indicar que esa rama queremos borrarla.

```git
git branch -d rama_a_borrar
```

Sin embargo, puede que esta acción no nos funcione porque hayamos hecho cambios que no se hayan salvado en el repositorio remoto, o no se hayan fusionado con otras ramas. En el caso que queramos forzar el borrado de la rama, para eliminarla independientemente de si se ha hecho el push o el merge, tendrás que usar la opción "-D".

```git
git branch -D rama_a_borrar
```

Debes prestar especial atención a esta opción "-D", ya que al eliminar de este modo pueden haber cambios que ya no se puedan recuperar. Como puedes apreciar, es bastante fácil de confundir con "-d", opción más segura, ya que no permite borrado de ramas en situaciones donde se pueda perder código.

### Eliminar un branch en remoto

Si la rama que queremos eliminar está en el repositorio remoto, la operativa es un poco diferente. Tenemos que hacer un push, indicando la opción --delete, seguida de la rama que se desea borrar.

```git
git push origin --delete rama_a_borrar
```
# gitYGitHubApuntes
Notas para poder usar git y github 

## Links para cada seccion: 

1. [Crear un repositorio en git](https://github.com/angelDariaux/gitYGitHubApuntes#crear-un-repositorio-de-git)
2. [Configurar git](https://github.com/angelDariaux/gitYGitHubApuntes#configurar-git)
3. [Analizar los cambios en los archivos del proyecto](https://github.com/angelDariaux/gitYGitHubApuntes#analizar-los-cambios-en-los-archivos-del-proyecto)
4. [Regresar en el tiempo en git](https://github.com/angelDariaux/gitYGitHubApuntes#regresar-en-el-tiempo-en-git)
5. [Ramas o Branches en Git](https://github.com/angelDariaux/gitYGitHubApuntes#ramas-o-branches-en-git)
6. [Usando GitHub](https://github.com/angelDariaux/gitYGitHubApuntes#usando-github)
7. [Configurar llaves ssh en local](https://github.com/angelDariaux/gitYGitHubApuntes#configurar-llaves-ssh-en-local)
8. [Tags y versiones en git y GitHub (comando arbolito)](https://github.com/angelDariaux/gitYGitHubApuntes#tags-y-versiones-en-git-y-github-comando-arbolito)
9. [Manejo de ramas en GitHub](https://github.com/angelDariaux/gitYGitHubApuntes#manejo-de-ramas-en-github)
10. [Configurando multiples colaborades en github](https://github.com/angelDariaux/gitYGitHubApuntes#configurando-multiples-colaboradores-en-github)
11. [Multiples entornos de trabajo en git](https://github.com/angelDariaux/gitYGitHubApuntes#multiples-entornos-de-trabajo-en-git)
12. [Git Stash: Guardar cambios en memoria y recuperarlos despues](https://github.com/angelDariaux/gitYGitHubApuntes#git-stash-guardar-cambios-en-memoria-y-recuperarlos-despues)
13. [Git Clean: limpiar tu proyecto de archivos no deseados](https://github.com/angelDariaux/gitYGitHubApuntes#git-clean-limpiar-tu-proyecto-de-archivos-no-deseados)
14. [Git cherry-pick: traer commits viejos al head de un branch](https://github.com/angelDariaux/gitYGitHubApuntes#git-cherry-pick-traer-commits-viejos-al-head-de-un-branch)
15. [Reconstruir commits con Amend](https://github.com/angelDariaux/gitYGitHubApuntes#reconstruir-commits-con-amend)
16. [Git reset y Reflog: USESE EN CASO DE EMERGENCIA \!!!](https://github.com/angelDariaux/gitYGitHubApuntes#git-reset-y-reflog-usese-en-caso-de-emergencia)
17. [Buscar archivos y commits de git con grep y log](https://github.com/angelDariaux/gitYGitHubApuntes#buscar-archivos-y-commits-de-git-con-grep-y-log)
18. [Comandos y recursos colaborativos en git y github](https://github.com/angelDariaux/gitYGitHubApuntes#comandos-y-recursos-colaborativos-en-git-y-github-episodio-42)


## CREAR UN REPOSITORIO DE GIT


`git init`                           se inicia un repositorio en local

`git status`                         se ve el estado del proyecto en este momento

`git rm fileName.txt`                elimina el archivo llamado de git, pero sigue estando en el catch (en memoria ram) 

`git rm --chached fileName.txt`      elimina el archivo llamado de git y si lo elimina del catch (se elimina de la memoria ram)

`git add fileName.txt`               agrega un archivo a la historia de git

`git add .`                          agrega todos los archivos nuevos a catch de git.

`git -m "descripcion del commit"`    agrega un commit junto con un mensaje.


##                                   CONFIGURAR GIT



`git config`                                       muestra como funciona la configuracion de git.

`git config --list`                                se ve la configuracion por defecto de mi git.

`git config -l`                                     lo mismo que lo de arriba.

`git config --list --show-origin`                   muestra donde estan las configuraciones guardadas.

`git config --global user.name "Tu nombre aqui"`   cambia el nombre que voy a usar en git.

`git config --global user.email "ejemplo@gmail.com"`    cambia el email que voy a usar en git.

`git log fileName.txt`                              muestra la historia de commits en el archivo.


##                                            ANALIZAR LOS CAMBIOS EN LOS ARCHIVOS DEL PROYECTO


`git show fileName.txt`                                  muestra los cambios hechos en el archivo

`git diff`                                      muestra la diferencia entre lo que tenemos en staging y lo que tenemos en disco duro

`git diff numeroDelPrimerCommit numeroDelUltimoCommit`    comparamos un nuevo commit con algun otro viejo commit y ver sus diferencias.


##                                            REGRESAR EN EL TIEMPO EN GIT


`git reset numeroDelCommit --hard`                  con esto podemos regresar al commit deseado y fuerza todos los cambios al commit llamado ( es el MAS USADO y mas peligroso)

`git reset numeroDelCommit --soft`                  volvemos a la version anterior pero lo que tengamos en staging sigue en staging (en memoria ram antes de dar commit)

`git log --stat`                                    vamos a ver los cambios especificos que se hicieron en cuales archivos apartir de commit.

`git checkout numeroDelCommit fileName.txt`           podemos ver como era el archivo llamado en el numero de commit que seleccionamos sin hacer un reset en el documento.

`git checkout master fileName.txt`               nos muestra la ultima version que habiamos commiteado la ultima vez. (esto es peligroso porque si hacemos commit vamos a borrar el progreso)

`git rm --cached`                             Elimina los archivos del área de Staging y del próximo commit pero los mantiene en nuestro disco duro.

`git rm --force`                              Elimina los archivos de Git y del disco duro. Git siempre guarda todo, por lo que podemos acceder al registro de la existencia de los archivos, de modo que podremos recuperarlos si es necesario (pero debemos usar comandos más avanzados)

`git reset HEAD`                              Este es el comando para sacar archivos del área de Staging. No para borrarlos ni nada de eso, solo para que los últimos cambios de estos archivos no se envíen al último commit, a menos que cambiemos de opinión y los incluyamos de nuevo en staging con git add, por supuesto.


##                                                     RAMAS O BRANCHES EN GIT


`git commit -am "commit a agregar"`                      esto le da add a los cambios y agrega un commit (solo funciona si no es un archivo nuevo al que no se la dado add .)

`git branch nombreDeLaNuevaRama`                         asi creamos nuevas ramas en git.

`git branch -D nombreDelaRama`                           asi borramos las ramas.

`git push origen --delete nombreDeLaRama`                asi borramos las ramas en remoto.  

`git checkout nombreDeLaRama`                            asi nos movemos a una rama diferente.

`git branch`                                             muestra las ramas que tenemos.

`git branch -r`                                          muestra las ramas que tenemos en remoto.

`git branch -a`                                          muestra las ramas locales y las remotas.

`git merge ramaAUnificar`                                estando en la rama principal, hacemos merge para agregar los ultimos cambios hechos en la otra rama.



##                                                      USANDO GITHUB


`git remote add origin direccionUrlDelRepositorio`       asi se agrega un repositorio remoto usando https SUPER IMPORTANTE CUANDO INICIAMOS UN NUEVO REPOSITORIO EN GIT!!!

`git remote`                                        podemos ver los respositorios remotos

`git remote -v`                                     podemos ver la URL de los repositorios remotos

`git push origin nombreDeLaRama`                    asi mandamos los cambios hechos a github de la rama que estamos seleccionando.

`git pull origin nombreDelaRama`                    traemos los cambios desde le repositorio remoto hacia la rama seleccionada.

`git pull origin master --allow-unrelated-histories`     CASO SUPER AISLADO con esto podemos fucionar los cambios de local con los del repositorio remoto.

##                                            CONFIGURAR LLAVES SSH EN LOCAL


1. Estando en el HOME del sismtema: 

`ssh-keygen -t rsa -b 4096 -C "ejemplo@gmail.com"`         asi se genera la llave publica y privada.

2. Generada la llave PUBLICA la debemos copiar y llevarla a github para poder comunicarnos con el respositorio remoto.

`eval $(ssh-agent -s)`           Estando en la terminalmcon esto evaluamos si todo esta funcionando bien con las llaves criptograficas.

    
3. Ahora debemos agregar la llave que acabamos de crear.

Estando en NUESTRA terminal ejecutamos: 

`ssh-add rutaDondeTenemosNuestraLlaveSSHPRIVADA`

4. Estando en la carpeta del PROYECTO ejecutamos:

`git remote set-url origin(ElNombreDelRepoEnLocal) git@github.com:direccionDelRepoRemotoDeGit`

`git pull origin master`             esto lo hacemos para unir el origin con la rama master del repo remoto.



##                                        TAGS Y VERSIONES EN GIT Y GITHUB (comando Arbolito)


git log --all                                               nos muestra todos los cambios hechos en nuestro repositorio local
git log --all --graph                                   lo mismo de arriba pero con lineas para hacer las facil leer los cambios
git log --all --graph --decorate --oneline               podemos ver toda la historia de nuestro proyecto de manera grafica (aqui se creamos el comando arbolito)

git tag -a nombreDelTag -m "mensajeDelTag" numeroDelHashDondePonerElTag         asi colocamos un tag en el hash del commit deseado.

git tag                                             nos muestra una lista de los tags que tenemos en el proyecto
git show-ref --tags                                 muestra a que commit esta asignado cada tag en el proyecto
git push origin --tags                               con esto mandamos nuestros tags al repo remoto.
git tag -d nombreDelTag                             asi eliminamos los tags dentro del repo LOCAL.    
git push origin :refs/tags/nombreDelTagABorrar         asi se eliminan los tags en el repositorio REMOTO


##                                           MANEJO DE RAMAS EN GITHUB


git show-branch                              muestra las ramas que existe y cual a sido su historia.
git show-branch --all                        lo mismo de arriba pero con mas detalles.
gitk                                         muestra toda la historia de manera visual.


#                                         CONFIGURANDO MULTIPLES COLABORADORES EN GITHUB

git clone direccionDeGitHub                       asi clonamos un repositorio siendo colaboradores


##                                             MULTIPLES ENTORNOS DE TRABAJO EN GIT

     REBASE solo debe usarse en el entorno local, NO debe ser mandado al repositorio remoto. SE DEBE EJECTUAR EL REBASE EN LAS 2 RAMAS LEER TODO ANTES DE HACER UN REBASE!
     
     Estando en la rama que queremos unir de sin dejar rastro de la historia: 

git rebase ramaAModificar                    con esto modificamos la rama llamada desde la rama que queremos unir sin dejar rastro en el historial de git.

     Estabdi en la rama que se modificara de manera permanente 

git rebase ramaExperiemental                 con esto terminamos de modificar la rama original con la rama experimental.


##                                         GIT STASH: GUARDAR CAMBIOS EN MEMORIA Y RECUPERARLOS DESPUES

Stahs siver para cuando estas en una rama pero quieres hacerle modificaciones a otra rama SIN hacerle commit a la rama actual donde estamos trabajando. Guarda los cambios en un lugar temporal
     Estando en la rama actuial donde no queremos hacer commit todavia: 

git stash                                    guarda los cambios en un lugar temporal sin modificar el mocumento y perminitiendonos ir a la otra rama sin perder el progreso y sin necesidad de hacer commit.
git stash list                                vemos lo que tenemos en stash. WIP= Work In Progress
git stash pop                                vemos el stash que teniamos antes y los cambios que habiamos ejecutado durante el stash.
git stash branch nombreDeLaNuevaRama         con esto salvamos los cambios que hicimos en el stash en otra rama.
git stash drop                               con esto eliminamos lo que tenemos en stash.


##                                           GIT CLEAN: LIMPIAR TU PROYECTO DE ARCHIVOS NO DESEADOS

     git clean sirve para eliminar archivos que no han sido trackeados y que no queremos agregar al respositorio.

git clean --dry-run                               podemos ver lo que se va a borrar sin borrarlo.
git clean -f                             se borran los archivos no trackeados, pero deja los archivos con el mismo nombre que los que si estan traqueados (toca borrarlos a mano) y que los los .gitignore


##                                           GIT CHERRY-PICK: TRAER COMMITS VIEJOS AL HEAD DE UN BRANCH

git log --online                        podemos ver los commits de forma ordenada.

     Desde la rama que tomara los cambios:

git cherry-pick numeroDelHash                     nos traemos solos los cambios que hicimos en se commit. 


##                                          RECONSTRUIR COMMITS CON AMEND


git commit --amend -m "nuevoNombreDelCommit"           con esto reparamos el nombre del ultimo commit de la rama donde estamos.


##                                     GIT RESET Y REFLOG: USESE EN CASO DE EMERGENCIA


git reflog                                             aqui se ve TODO y se ven los "HEAD" del proyecto es decir los cambios hechos y ver donde estaba el apuntador.
git reset --HARD numeroDelHash                      con el head que sacamos del reflog podemos usar reset y regresar todo antes de haber hecho los cambios indeseados.


##                                    BUSCAR ARCHIVOS Y COMMITS DE GIT CON GREP Y LOG

git grep palabraABuscar                      con esto buscamos la palabra dentro de nuestro proyecto
git grep -n palabraABuscar                   lo mismo de arriba pero nos dice el numero de linea.
git grep -c palabraABuscar                   cuenta el numero de veces que fue usada la palabra selecionada.
git grep -c "<\p>"                            lo mismo de arriba pero este es usado para cuando tenemos los caracteres <> para buscar un parrafo dentro de nuestro codigo.

git log -S "palabraABuscar"                  con esto buscamos la palabra seleccionada pero dentro de los commits.



##                                           COMANDOS Y RECURSOS COLABORATIVOS EN GIT Y GITHUB


git shortlog                                      con este podemos ver cuantos commits ha hecho cada miembro del proyecto
git shortlog -sn                                  nos muesta las personas que han hecho los commits
git shortlog -sn --all                            muestra tdos los commits hasta los que fueron borrados. 
git shortlog -sn --all --no-merges                nos muestra todos los commits menos los merges.
git config --global alias.stats "shortlog -sn --all --no-merges"           asi creamos un alias llamado stats dentro del entorno git y NO el global y va a ejecutar shorlog ...

git blame -c nombreDelArchivo                           aqui podemos ver quien creo cada linea del codigo
git blame nombreDelArchivo -L15,45 -c                   podemos ver quien modifico esas lines en el archivo invocado.

























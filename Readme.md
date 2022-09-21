## Curso de GIT
Hay 4 etapas:
- working (area de trabajo)
- staged (add)
- commited (commit)
- remote (push)
recordemos que tenemos que usar pull para traer el trabajo desde un repositorio
# Comandos:
- git add
- git commit -m "Added..."
- git remote add origin https://github.com/HectorBusSan/curseGit.git
- git push -u origin master
Si queremos recuperar del repositorio remoto
- git pull
# Remplazar Marter por Main
- git branch -m master main (Crear la rama main y pasa todo a la rama main)
- git push -u origin main (usamos ahora con main)
- cambiar el head de master a main
- git symbolic-ref refs/remotes/origin/HEAD refs/remotes/origin/main
- git push origin --delete master
# Repositorio nuevo con main
- git init
- git add .
- git commit -m "Primer Commit"
- git branch -M main
- git remote add origin http://...
- git push -u origin main
# Ayuda
- git (comando) -h (solicitamos ayuda sobre el comando)
- git add -h
- git help add (abre la ayuda en le navegador)
# Ignorar Archivos
- .gitignore
- archivo.ext (ignora el archivo)
- carpeta (nombre de la carpeta)    
- archivo_desde_raiz.ext (ignora archivo especifico en la raiz)
- *.log (ignora todos los archivos que tienen extención .log)
- !producto.log (todos excepto producto.log)
- doc/*.txt (ignora todo .txt en carpeta doc)
- doc/**/*.txt (ignora todo .txt en doc y subcarpetas)
- generador de archivos .gitignore
- https://github.com/HectorBusSan/BranchMain.git
<<<<<<< HEAD
- git push (ya solo sin poner origin main porque solo tenemos una rama).
# Clonar
- seleccionamos donde lo vamos clonar el repositorio
- git clone http://
# Ramas
- git branch nombre-rama (crear rama)
- git checkout nombre-rama (cambiar a rama especifica)
- git checkeout -b rama (crear y cambiar a esa rama)
- git branch -d nombre-rama(eliminar rama)
- git branch -D nombre-rama(forzar eliminación)
- git branch (todas las ramas)
- git branch --no-merged (ramas no fucionadas con la rama actual)
- git branch --merged (ramas fucionadas a la rama actual)
- (rebasar rama)
- git checkout rama-secundaria
- git rebase rama-principal
# Fusiones
- Fast-Forward (Fusion automatica donde hay cambios solo en un archivo y no hay conflictos de resolver)
- Manual Merge (Fusión que hay que hacer manual para resolver confictos de duplicidad de contenido)
==========
- git merge nombre-rama (juntara el archivo faltante)
si quieres eliminar una rama remota despues de fucionar:
- git push origin --delete nombre-rama
# Cambios
- git commit --amend --no-edit (No modificar el mensaje del ultimo commit solo contenido)
- git commit --amend -m "Nuevo mensaje para ultimo commit" (puede presentar conflicto se recomiendo hacer pull, con esta opción podemos cambiar commit y contenido usa git pull y acepta o rechaza los ca   mbios actuales)


Recuerda que puedes tener conflictos si a lo mandaste al repositprio remoto el commit a cambiar hay que tener cuidado.


Tienes que crear un nuevo commit si no quiere conflictos para salir de Main|Merging.


Recuerda que los cmabios seran mas faciles desde tu local.


- por ejemplo eliminamos algo en el utlimo commit que es importante 0o0:
- git reset --hard HEAD~1 (Eliminar el utlimo commit)
=============


no solo con **checkout** podemos cambiar de rama tambien de commit segun su id
- git checkout nombre-rama
- git checkout id-commit


=============


para ver el historial de commits usamos **log**
- git log (todos los commits)
- git log --oneline (todos los commits en una linea)

# Historial de Cambios *LOG*
- git log
- git log --oneline
- git log > commits.txt (Crea archivo de texto con todos lo commits)
- git log --pretty=format:"%h - %an, %ar : %s" (Solicita en commit: id - creador,minutos : nombre)
- git -n (el numero de commits que quieres ver)
- git log --after "2022-09-14 00:00:00"
- git log --before= "2022-09-14 00:00:00"
- git log --after= "2022-09-14 00:00:00" --before "2022-15-08 00:00:00"
- git log reflog (información de cambios, fuciones, ramas e inserciones)
- git diff (diferencias entre el stage y el working directory)
=========
- git log --oneline --graph --all (para ver todos los commits a una linea con una grafica)
- git log --oneline --graph --all > graph.txt (en un txt los commits de manera grafica)
# Reseteo del historial
- git status
- git reset --soft (borrar HEAD)
- git reset --mixed (borrar HEAD y Staging)
- git reset --hard (borrar todo Head, Staging y Word Directory)
- git reset id-commit (desacer cambios de todos los commits despues del commit indicado, perservando los cambios localmente)
- git reset --hard id-commit (desacer todos el historial y regresar al commit especificado)
# Resetear Repositorio
- cd carpeta-repositorio
- mv .git/config ~/saved_git_config (lo guarda en tu carpeta de usuario ~ rama principal de pc)
- rm -rf .git (elimina git)
- git init
- git branch -M main
- git add .
- git commit -m "Commit inicial"
- git ~/saved_git_config .git/config (solicita de regreso el archivo de configuración)
- git push --force origin main (push forzado)
# Remotos
- git remote (origenes remotos del repositorio)
- git remote -v (muestra los orgines remotos con detalle)
- git remote *add* nombre-origin http://github... (agregar origen remoto)
- git remote *rename* nombre-viejo nombre-nuevo (renombrar un origin remoto)
- git remote *remove* nombre-origin (eliminar origen remoto)
- git checkout --track -b rama-remota origin/rama-remota (descargar una rama remota a local diferente a la principal)
# Etiquetas
Versión: 2.0.0
- Primer numero la versión (no es compatible con versiones anteriores)
- Segundo numero funcionalidades (funcionalidades nuevas agregadas a la versión anterior)
- Tercer numero Parches (Parches para corregir errores a la versión anterior)
Esta es la Versión Semantica.

Opciones de inicio: 0.0.1 o la 1.0.0
- git tag (mostrar etiquetas)
- git tag numero-versión (crear etiqueta)
- git tag -d numero-versión (eliminar etiqueta)
- git show numero-versión (mostrar info de la eqtiqueta)

Maneras de crear una etiqueta:
- (sincronizar equiqueta del repositorio local al remoto)
- git add .
- git tag v1.0.0
- git commit -m "v1.0.0"
- git push origin numero-versión
- (generar etiqueta anotada "con mensaje de commit")
- git add .
- git tag -a "v1.0.0" -m "Mensaje de la etiqueta"
- git push --tags


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
## Ignorar Archivos
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
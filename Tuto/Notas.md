# Comandos GIT

## ADD
* git add .                         |-> Marca todos los artefactos modificados como candidatos para ser subidos al repositorio
* git add archivo                   |-> Marca un artefacto en específico como candidato para ser subido al repositorio
* git add archivo archivo archivo   |-> Marca los artefactos especificados como candidato para ser subido al repositorio
* git add *.ext                     |-> Marca todos los artefactos modificados con la extensión indicada en el directorio actual para ser subidos al repositorio
* git add "*.ext"                   |-> Marca todos los artefactos modificados con la extensión indicada para ser subidos al repositorio
* git add dir/                      |-> Marca todos los artefactos modificados de un directorio indicado para ser subidos al repositorio
* git add dir/*.ext                 |-> Marca todos los artefactos modificados de un directorio indicado con extensión específica para ser subidos al repositorio
* git add -u                        |-> Actcaliza los artefactos marcados

## BRANCH
* git branch                        |-> Me muestra las ramas creadas
* git branch nombre-branch          |-> Crea una nueva rama
* git merge nombre-branch           |-> Une una rama a la rama principal
* git branch -d nombre-branch       |-> Elimina una rama

## CHEKOUT
* git checkout -- .                 |-> Obtiene la ultima versión del proyecto
* git checkout -- archivo           |-> Obtiene la ultima versión de un archivo en específico
* git checkout nombre-branch        |-> Me ubica en la rama indicada
* git checkout -b nombre-branch     |-> Crea una nueva rama y me ubica en la misma

## CLONE
* git clone https://github.com/bitcubico/udemy-heroes.git                 |-> Clona un repositorio localmente
* git clone https://github.com/bitcubico/udemy-heroes.git nombre_dir>    |-> Clona un repositorio localmente indicando el nombre del directorio

## COMMIT
* git commit                            |-> Confirma el envío al repositorio de los artefactos marcados
* git commit -m "Mensaje"               |-> Confirma el envío al repositorio de los artefactos marcados permitiendome agregar un mensaje en linea
* git commit -am "Mensaje"              |-> Marca todos los artefactos modificados como candidatos para ser subidos al repositorio y confirma el envío al repositorio de los artefactos marcados
* git commit --amend                    |-> Modifica el mensaje del último commit realizado
* git commit --amend -m "Mensaje        |-> Modifica el mensaje del último commit realizado permitiendome agregar un mensaje en línea

## CONFIG
* git --version                                             |-> Muestra la versión de git
* git config --global user.name "mcubico"                   |-> Crea el usuario que va a hacer modificaciones desde esta máquina
* git config --global user.email "mcubico33@gmail.com"      |-> Crea el email del usuario que va a hacer modificaciones desde esta máquina
* git config --global -e            |-> Muestra el archivo que contiene la configuración de los usuarios
* git config core.autocrlf true     |-> Corrige problema con la ejecución del comando CRLF
* git config --global alias.nombre "log --oneline --decorate --all --graph"   |-> Sirve para crear alias de comandos en git
* git init  |-> Indica que ese directorio será un repositorio

## DIFF
* git diff                    |-> Muestra la diferencia entre la última versión y la actual de los archivos modificados 
* git diff --staged           |-> Muestra la diferencia entre la última versión y la actual de los archivos modificados que están en el staged o marcados para subir al repositorio
* git diff nombre-branch> nombre-branch-2      |-> Muestra las diferencias entre dos ramas

## HELP
* git help              |-> Muestra la ayuda de git
* git help comando      |-> Muestra la ayuda de un comando de git

## LOG
* git log               |-> Muestra el historial de commits realizados con sus mensajes
* git log --oneline     |-> Muestra el historial de commits realizados con sus mensajes en una sola línea
* git reflog            |-> Muestra el historial de commits realizados con sus mensajes en toda la historia del repositorio

## MV
* git mv nombre_archivo.ext nombre_archivo_nuevo.ext  |-> Renombra un archivo conservando todo su historial

## PULL
* git pull          |-> Obtiene la última versión del repositorio e intenta hacer un merge
* git pull fetch    |-> Obtiene la última versión sin hacer merge

## PUSH
* git push                        |-> Sube los artefactos al repositorio
* git push -u origin master       |-> Sube los artefactos al repositorio especificando el nombre de la realizar
* git push --tags                 |-> Sube los tags al repositorio

## REBASE
* git rebase master           |-> Agrega los commit del master posteriores a la rama donde estoy ubicado para que quede todo actualizado

## RESET
* git reset . | archivo | *.ext | dir/ ... etc      |-> Excluye artefactos de un listado de artefactos marcados
* git reset --soft HEAD o idCommit    |-> Revierte los cambios del último commit (HEAD apunta a los últimos cambios registrados HEAD^ apunta a uno arriba)
* git reset --mixed HEAD o idCommit   |-> Revierte los cambios realizados en determinado commit conservando los cambios locales
* git reset --hard HEAD o idCommit    |-> Revierte los cambios realizados en determinado commit eliminando los cambios locales

## RM
* git rm nombre_archivo.ext |-> Elimina un archivo conservando todo su historial (Se debe realizar commit para confirmar el cambio)

## STASH
* git stash                                   |-> Guarda los cambios sin hacer commit y me actualiza los recursos al último commit
* git stash save "Mensaje"                    |-> Guarda los cambios sin hacer commit agregando un mensaje descriptivo al final
* git stash save --keep-index                 |-> Guarda todos los cambios de los archivos menos los que estan marcados para subir al repositorio
* git stash save --include-untracked          |-> Guarda todos los cambios incluyendo los archivos que git no les da seguimiento
* git stash list                              |-> Despliega todos los stash guardados
* git stash pop                               |-> Obtiene los cambios en los artefactos del primer stash y elimina el stash de la lista
* git stash drop                              |-> Elimina el primer stash de la lista
* git stash drop stash@posicionStash          |-> Elimina el stash con el id especificado
* git stash apply stash@posicionStash         |-> Carga el stash con el id especificado
* git show stash                              |-> Muestra todo lo que se hizo en cada uno de los stash en la lista
* git show stash stahs@posicionStash          |-> Muestra todo lo que se hizo en un stash específico de la lista
* git stash clear                             |-> Borra todas las entradas de un stash sin opción de recuperar
* git stash clear stahs@posicionStash         |-> Borra todas las entradas de un stash sin opción de recuperar

## STATUS
* git status                  |-> Muestra todos los artefactos candidatos para subir al repositorio
* git status -s               |-> Muestra todos los artefactos candidatos para subir al repositorio de forma simplificada
* git status -s -b            |-> Muestra todos los artefactos candidatos para subir al repositorio de forma simplificada y espefificando la rama en la que se está trabajando

## TAG
* git tag                                         |-> Muestra todos los tags creados
* git tag nombre-tag                              |-> Crea un nuevo tag
* git tag -a v1.0.0 -m "Mensaje"                  |-> Crea un nuevo tag con una anotación y un mensaje para el mismo
* git tag -a v0.1.0 idCommit -m "Mensaje"         |-> Agrega un tag a un commit específico
* git show v1.0.0                                 |-> Despliega la información de un tag específico
* git push --tags                                 |-> Sube los tags al repositorio GITHUB

# GITHUB

## Ejemplo de como se crea un nuevo repositorio asociado a un proyecto en GITHUB
1. echo "# git-tuto" >> README.md
2. git init
3. git add README.md
4. git commit -m "first commit"
5. git remote add origin https://github.com/bitcubico/git-tuto.git
6. git push -u origin master

## Comandos de GITHUB:
* git fetch                       |-> Obtiene la última versión del repositorio sin hacer un merge
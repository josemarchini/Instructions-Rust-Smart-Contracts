## Cómo colaborar en un proyecto con Git

*   [Fork del repositorio](#fork-del-repositorio)
*   [Clonar el repositorio](#clonar-el-repositorio)
*   [Actualizar la rama main](#actualizar-la-rama-main)
*   [Crear una rama](#crear-una-rama-nueva)
*   [Ver donde estas parado](#ver-donde-estas-parado)
*   [Hacer los cambios](#hacer-los-cambios)
*   [Agregar los archivos para commitear](#agregar-archivos-para-commitear)
*   [Crear commit con comentario](#crear-commit-con-comentario)
*   [Enviar commit a la rama remota](#enviar-commit-a-la-rama-remota)
*   [Si es el primer commit a enviar pushear al origen](#si-es-el-primer-commit-a-enviar-pushear-al-origen)
*   [Actualizar branch/rama con main](#actualizar-branch-rama-con-main)
*   [Mergear branch/rama a main](#mergear-branch-rama-a-main)
*   [Hacer un Pull Request](#hacer-un-pull-request)
*   [Cambiar el nombre del branch](#cambiar-nombre-al-branch)
*   [Guardar los cambios locales sin commitear](#guardar-cambios-locales-git-stash)

## Fork del repositorio

El primer paso es hacer "Fork" del repositorio.

## Clonar el repositorio

Después de tener el repositorio en nuestra cuenta, seleccionar la dirección del repositorio "SSH o HTTP" y clonar:

`$ git clone https://github.com/User/NombreRepo.git`

Dentro de la carpeta que genera, comprobar la URL del repositorio:

`$ git remote -v`

Antes de realizar modificaciones agregar la URL del repositorio original del proyecto:

`$ git remote add upstream https://github.com/User/RepoOriginal(Forkeado)`

Comprobar

`$ git remote -v`

## Actualizar la rama Main

Antes de empezar a trabajar, obtener los últimos cambios del repositorio original:

`$ git pull -r upstream main`


## Crear una rama nueva

1. pararse en main
2. actualizar rama con origen remoto: `git pull`
3. crear branch con nombre tiger-xx: `git checkout -b "tiger-xx"`

## Ver donde estas parado

`git status`

## Hacer los cambios:
## Agregar archivos para commitear

`git add .` o `git add [nombre archivo]`


## Crear commit con comentario
(siempre poniendo primero el nombre del branch)
`git commit -m "tiger-xx creacion del componente bla bla y actualizacion de bla bla`


## Enviar commit a la rama remota
(para que quede actualizado)
`git push`

## Si es el primer commit a enviar pushear al origen
`$ git push origin feature-nombre-rama`

## Actualizar branch-rama con main
(siempre antes de mergear a master primero actualizar la rama con main, para resolver conflictos en rama y NO en main)
1. Pararse en rama: `git pull origin main`


## Mergear branch-rama a main
1. Pararse en main y traer la rama (previamente actualizada con main): `git pull origin tiger-xx`


## Hacer un pull request

1. Hacer click en "Compare & Pull Request"
2. Escribir cambios del Pull Request.
3. Si todo está bien, enviar con el botón "Send Pull Request".
4. Esperar a que el titular del repositorio lo revise, acepte y mezcle en la rama correspondiente.


## Cambiar el nombre del branch
Si al crear el branch te equivocaste de nombre y todavia no lo pusheaste al origen, se puede cambiar localmente
`git branch -m [nuevo-nombre]`

## Borrar carpeta .git para iniciar un nuevo repositorio
lo primero que tienes que hacer es borrar la carpeta .git de tu directorio de trabajo(esta contiene toda la informacion de git"
(copy the next comand)

1. rm -rf .git
2. rm -rf <carpeta_de_repositorio> .git (en el caso quieras corrar toda tu carpeta NO RECOMENDADO)

Luego vuelves a hacer.. git init

## Ahora sigues todos los pasos para volver a iniciar tu repositorio
1. (first commit)
git commit -m "first commit"

2.(next) le das un nombre a tu branch principal
git branch -m main 

3.(next) agregas tu repositorio remoto
git add remote origin <aqui va la url de tu repositorio en github
                            
4.(next) haces el primer push si el repositorio esta vacio
git push -u origin main 
                            
5.(en el caso el repositorio ya tenga archivos y ramas es mejor hacer primero un git pull o git --rebase, para traerte todos los cambios de tu repositorio)
git pull -f origin main
                            
git pull origin main
                            
git pull --rebase                            
                            
## Cambiar el nombre a un commit anterior
git commit --amend -m "an updated commit message"                            

                          
## Guardar los cambios locales sin commitear
Si estas trabajando en algunos cambios y necesitas cambiar de branch por algun otro asunto, y tus cambios todavia no estan listos para ser commiteados, entonces hay una opcion de guardar los cambios locales y volver a agarrarlos despues.

Para guardarlos sin commitear
`git stash`

Para volver a trabajar en esos cambios 
`git stash pop`

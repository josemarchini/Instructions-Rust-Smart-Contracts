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


## Guardar los cambios locales sin commitear
Si estas trabajando en algunos cambios y necesitas cambiar de branch por algun otro asunto, y tus cambios todavia no estan listos para ser commiteados, entonces hay una opcion de guardar los cambios locales y volver a agarrarlos despues.

Para guardarlos sin commitear
`git stash`

Para volver a trabajar en esos cambios 
`git stash pop`

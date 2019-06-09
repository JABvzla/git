# GIT

_by José Bonito_

- [Crear el repositorio `git init <ruta>`](#crear-el-repositorio-git-init-ruta)

- [Ver el estado de los ficheros `git status`](#ver-el-estado-de-los-ficheros-git-status)

  - [Sin seguimiento `untracked`](#sin-seguimiento-untracked)

  - [Sin modificaciones `unmodified`](#sin-modificaciones-unmodified)

  - [Modificado `modified`](#modificado-modified)

  - [Fichero staged `staged`](#fichero-staged-staged)

- [Agregar ficheros al stage `git add <nombre-del-fichero>`](#agregar-ficheros-al-stage-git-add-nombre-del-fichero)

- [Crear un commit `git commit -m "mensaje del commit"`](#crear-un-commit-git-commit-m-mensaje-del-commit)

- [Ver historial de commits `git log`](#ver-historial-de-commits-git-log)

- [Ver listado de ramas `git branch`](#ver-listado-de-ramas-git-branch)

- [Viajando entre commits `git checkout <nombre-branch o delta-commit>`](#viajando-entre-commits-git-checkout-nombre-branch-o-delta-commit)

- [Traer ficheros de otra rama o commit `git checkout <nombre-branch o delta-commit> <fichero o directorio>`](#traer-ficheros-de-otra-rama-o-commit-git-checkout-nombre-branch-o-delta-commit-fichero-o-directorio)

- [Crear rama `git checkout -b <nombre-rama-nueva>`](#crear-rama-git-checkout-b-nombre-rama-nueva)

- [Unir ramas `git merge rama-a-unir`](#unir-ramas-git-merge-rama-a-unir)

- [Comparar fichero entre ramas o commits `git diff <rama-1> <rama-2> <fichero>`](#comparar-fichero-entre-ramas-o-commits-git-diff-rama-1-rama-2-fichero)

- [Subir cambios `git push <repo> <rama>`](#subir-cambios-git-push-repo-rama)

- [Bajar cambios `git pull <repo> <rama>`](#bajar-cambios-git-pull-repo-rama)

### Crear el repositorio `git init <ruta>`:

Para crear un repositorio es necesario decirle a git en que directorio se va a crear, luego del comando `git init` se debe agregar la ruta del directorio `git init ruta/de/mi-carpeta`, si no se le especifica ninguna ruta se creara el dentro del directorio situado.
[_Documentación Oficial_](https://git-scm.com/book/es/v1/Fundamentos-de-Git-Obteniendo-un-repositorio-Git)

### Ver el estado de los ficheros `git status`:

Git usa 4 estados para facilitar el seguimiento de los ficheros, estos cuatro estados son `untracked`, `unmodified`, `modified`, `staged`.

#### Sin seguimiento `untracked`:

Un fichero es `untracked` cuando no hay registro del mismo en el histórico de git, cuando se crea un repositorio nuevo, todos los ficheros empiezan con el estado `untracked`.

#### Sin modificaciones `unmodified`:

Un fichero es `unmodified` cuando existe un registro previo del mismo en el histórico de git pero no posee ninguna diferencia con el ultimo guardado.

#### Modificado `modified`:

Cuando un fichero es distinto al ultimo guardado es considerado `modified`, cuando un fichero es borrado tambien es considerado como `modified`.

#### Fichero staged `staged`:

Cuando se realiza un commit se guardan unicamente los ficheros que están en el `stage`.

### Agregar ficheros al stage `git add <nombre-del-fichero>`:

Con `git add <nombre-del-fichero>` podrás agregar ficheros al stage, ejemplo `git add ./ruta/mi-archivo.js`, si se especifica un directorio se agregaran al stage todos los ficheros `modified` dentro del fichero.

### Crear un commit `git commit -m "mensaje del commit":

Para guardar los cambios que están `staged` ejecutar `git commit -m "mensaje"`, luego de crear un commit los ficheros `staged` pasaran a `unmodified` los `modified` seguirán siendo `modified` estos no serán guardados.

### Ver historial de commits `git log`:

Para ver el historial de commits ejecutar `git log` por defecto te mostrará el historial de commit desde el HEAD, si desea ver el historial de una rama o un commit se pueden especificar ejemplo: `git log nombre-rama` `git log a2a4d5b`. si deseamos ver los commit con menos en una sola linea cada una se puede usar el parámetro `--oneline` ejemplo: `git log nombre-rama --oneline`.

### Ver listado de ramas `git branch`:

Si deseas ver el listado de ramas ejecuta el comando `git branch`, en la consola veras un listado de las ramas existente y se mostrara de color verde la rama donde estas situado actualmente.

### Viajando entre commits `git checkout <nombre-branch o delta-commit>`:

Cuando deseamos ir a un commit o rama solo debemos escribir `git checkout` y el nombre de la rama o delta del commit ejemplos: `git checkout nombre-rama` `git checkout c18aca0`.

### Traer ficheros de otra rama o commit `git checkout <nombre-branch o delta-commit> <fichero o directorio>`

En algunos casos deseamos traer un fichero o directorio entero sin salir de nuestro estado actual para eso hacemos un `git checkout` especificando el nombre de otra rama o delta con el nombre del fichero o directorio que queremos traer ejemplos: `git checkout rama2 archivo.js` o `git checkout a2ca5sd4 ./directorio`.

### Crear rama `git checkout -b <nombre-rama-nueva>`:

Para crear una rama y moverte a ella automáticamente escribe el nombre de la rama nueva seguido de `git checkout -b` ejemplo `git checkout -b rama-nueva`, la rama se creará a partir de la localización actual en git.

### Unir ramas `git merge rama-a-unir`:

Para unir dos ramas unicamente debemos ejecutar `git merge` y especificar el nombre de la otra rama que deseamos unir.

### Comparar fichero entre ramas o commits `git diff <rama-1> <rama-2> <fichero>`:

En muchas ocasiones deseamos conocer cual es la diferencia de un fichero entre dos commits (o ramas), para eso podemos usar `git diff` seguido de los delta (o ramas) y el archivo en cuestión, ejemplos: `git diff rama-1 c5asd4 archivo.js`.

### Subir cambios `git push <repo> <rama>`.

Para subir tus cambios a un repositorio remoto utilizar `git push origin` y el nombre de la rama a subir ejemplo: `git push origin rama1`.

### Bajar cambios `git pull <repo> <rama>`.

Para descargar tus cambios de un repositorio remoto utilizar `git pull origin` y el nombre de la rama a descargar ejemplo: `git pull origin rama1`.

### TODO

- [ ] Links de doc oficial.
- [ ] Doc glosario.
- [ ] Doc metodologías.
- [ ] Revisar la ortografía de todo el documento

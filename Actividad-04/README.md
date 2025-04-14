## Actividad 4

Establezco la información de usuario que será registrada en los commits
```bash
git config --global user.name "GersoZz"
git config --global user.email "gersonzuniga@uni.pe"
```

Verifico la información

```bash
$ git config --global -l
user.name=GersoZz
user.email=gersonzuniga@uni.pe
```

Creamos un directorio y nos posicionamos en él
```bash
mkdir Actividad-04
cd Actividad-04
```

Inicializamos un repositorio local de git

```bash
$ git init
Initialized empty Git repository in F:/UNI/25-1/CC3S2A - Desarrollo de Software/Actividad-04/.git/
```


Creamos el archivo README.md
```bash
echo "README" > README.md
```

Revisamos los cambios detectados por git 
```bash
$ git status
On branch main

No commits yet

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        README.md

nothing added to commit but untracked files present (use "git add" to track)
```

Agregamos el archivo al área de preparación
```bash
git add README.md
git status
```

Revisamos nuevamente los cambios

```bash
$ git status
On branch main

No commits yet

Changes to be committed:
  (use "git rm --cached <file>..." to unstage)
        new file:   README.md
```

Visualizamos que el archivo ha sido agregado al área de preparación y está listo para ser commiteado

Procedemos a hacer un commit 

```bash
$ git commit -m "Initial commit with README.md"
[main (root-commit) f65d30a] Initial commit with README.md
 1 file changed, 1 insertion(+)
 create mode 100644 README.md
```

revisamos nuevamente con git status

```bash
$ git status
On branch main
nothing to commit, working tree clean
```

Vemos que ya no tenemos cambios en el area de preparación, el único cambio que había fue comiteado

Revisamos el historial de commits
```bash
$ git log
commit f65d30a54919a5b7baf242906c109d19c7b80b07 (HEAD -> main)
Author: GersoZz <gersonzuniga@uni.pe>
Date:   Mon Apr 14 09:48:38 2025 -0500

    Initial commit with README.md
```

Probamos otra forma de revisar el historial de commits

```bash
$ git log --graph --pretty=format:'%x09 %h %ar ("%an") %s'
*        f65d30a 6 minutes ago ("GersoZz") Initial commit with README.md
```

Visualizamos que este comando muestra el hash del commit, hace cuanto fue comiteado, el usuario que lo hizo y el mensaje del commit

### Agregamos el archivo CONTRIBUTING y actualizamos el README

```bash
$ echo "CONTRIBUTING" > CONTRIBUTING.md
$ echo "README\n\nWelcome to the project" > README.md
$ git add .

W10@W10PC MINGW64 /f/UNI/25-1/CC3S2A - Desarrollo de Software/Actividad-04 (main)
$ git commit -m "Set up the repository base documentation"
[main 95cc685] Set up the repository base documentation
 2 files changed, 2 insertions(+), 1 deletion(-)
 create mode 100644 CONTRIBUTING.md
```

### Agregamos un archivo Python

```bash
$ echo "print('Hello World')" > main.py
$ git add .

W10@W10PC MINGW64 /f/UNI/25-1/CC3S2A - Desarrollo de Software/Actividad-04 (main)
$ git commit -m "Add main.py"
[main f45c517] Add main.py
 1 file changed, 1 insertion(+)
 create mode 100644 main.py
```

### Revisamos el historial de commits

```bash
$ git log --oneline
f45c517 (HEAD -> main) Add main.py
95cc685 Set up the repository base documentation
f65d30a Initial commit with README.md
```
Visualizamos el commit donde agregamos al archivo main.py

## Ramas

Creamos una rama y nos pasamos a ellla

```bash
W10@W10PC MINGW64 /f/UNI/25-1/CC3S2A - Desarrollo de Software/Actividad-04 (main)
$ git branch feature/new-feature

W10@W10PC MINGW64 /f/UNI/25-1/CC3S2A - Desarrollo de Software/Actividad-04 (main)
$ git checkout feature/new-feature
Switched to branch 'feature/new-feature'
```

## Preguntas


## Ejercicio 1 Manejo avanzado de ramas y resolución de conflictos

```bash
W10@W10PC MINGW64 /f/UNI/25-1/CC3S2A - Desarrollo de Software/Actividad-04 (main)
$ git branch feature/advanced-feature

W10@W10PC MINGW64 /f/UNI/25-1/CC3S2A - Desarrollo de Software/Actividad-04 (main)
$ git checkout feature/advanced-feature
Switched to branch 'feature/advanced-feature'
```

Hacemos una edicion en main.py y commiteamos el cambio

```bash
W10@W10PC MINGW64 /f/UNI/25-1/CC3S2A - Desarrollo de Software/Actividad-04 (feature/advanced-feature)
$ git add main.py

W10@W10PC MINGW64 /f/UNI/25-1/CC3S2A - Desarrollo de Software/Actividad-04 (feature/advanced-feature)
$ git commit -m "Add greet function in advanced feature"
[feature/advanced-feature c613936] Add greet function in advanced feature
 1 file changed, 4 insertions(+), 1 deletion(-)
```

Nos movemos a la rama main y editamos main.py

```bash
W10@W10PC MINGW64 /f/UNI/25-1/CC3S2A - Desarrollo de Software/Actividad-04 (main)
$ git add main.py

W10@W10PC MINGW64 /f/UNI/25-1/CC3S2A - Desarrollo de Software/Actividad-04 (main)
$ git commit -m "Update main.py message in main branch"
[main aedc143] Update main.py message in main branch
 1 file changed, 1 insertion(+), 1 deletion(-)
```

Intentamos hacer merge de la rama feature/advanced-feature en la rama main

```bash
W10@W10PC MINGW64 /f/UNI/25-1/CC3S2A - Desarrollo de Software/Actividad-04 (main)
$ git merge feature/advanced-feature
Auto-merging main.py
CONFLICT (content): Merge conflict in main.py
Automatic merge failed; fix conflicts and then commit the result.
```

Nos sale que hay un conflicto, lo resolvemos


Abrimos el archivo main.py
```bash
W10@W10PC MINGW64 /f/UNI/25-1/CC3S2A - Desarrollo de Software/Actividad-04 (main|MERGING)
$ vi main.py
```

Visualizamos el conflicto
```bash
<<<<<<< HEAD
print('Hello World - updated in main')
=======
def greet():
    print('Hello from advanced feature')
greet()
>>>>>>> feature/advanced-feature
~
```

Resolvemos el conflicto
```bash
def greet():
    print('Hello from advanced feature')
    print('Hello World - updated in main')
greet()
~
```

Registramos el cambio en un commit
```bash
W10@W10PC MINGW64 /f/UNI/25-1/CC3S2A - Desarrollo de Software/Actividad-04 (main|MERGING)
$ git add main.py

W10@W10PC MINGW64 /f/UNI/25-1/CC3S2A - Desarrollo de Software/Actividad-04 (main|MERGING)
$ git status
On branch main
All conflicts fixed but you are still merging.
  (use "git commit" to conclude merge)

Changes to be committed:
        modified:   main.py


W10@W10PC MINGW64 /f/UNI/25-1/CC3S2A - Desarrollo de Software/Actividad-04 (main|MERGING)
$ git commit -m "Resolve merge conflict between main and feature/advanced-feature"
[main d172c03] Resolve merge conflict between main and feature/advanced-feature
```

Finalmente borramos la rama que fusionamos
```bash
W10@W10PC MINGW64 /f/UNI/25-1/CC3S2A - Desarrollo de Software/Actividad-04 (main)
$ git branch -d feature/advanced-feature
Deleted branch feature/advanced-feature (was c613936).
```
…

##  Ejercicio 2: Exploración y manipulación del historial de commits

### 1. Ver el historial detallado de commits:

```bash
git log -p
```

Se visualiza todos los commits con los cambios especificos que se realizaron


### 2. Filtrar commits por autor

```bash
git log --author="GersoZz"
```
Aparece todos los commits que hizo el usuario "GersoZz"

### 3. Revertir un commit

Dado que el último commit fue de un merge que resolvía un conflicto entre la rama `feature/advanced-feature` y la rama `main`, usaremos el flag `-m 1` para decirle al comando revert que mantenga los cambios de la rama main y no los de la rama `feature/advanced-feature` 

```bash
git revert -m 1 HEAD
```

En efecto verificamos que el nuevo commit de revert se ha registrado

```bash
$ git log --oneline
2c7deae (HEAD -> main) Revert "Resolve merge conflict between main and feature/advanced-feature"
d172c03 Resolve merge conflict between main and feature/advanced-feature
aedc143 Update main.py message in main branch
c613936 Add greet function in advanced feature
f45c517 (feature/new-feature) Add main.py
95cc685 Set up the repository base documentation
f65d30a Initial commit with README.md
```

### 4. Rebase interactivo

Para una ejecución más limpia de este comando realizamos 4 commits sencillos y luego fusionaremos los 3 últimos usando squash

```bash
$ git log --oneline
f9023ab (HEAD -> main) add file_D
3633723 add file_C
d12194a add file_B
e76cc73 add file_A
2c7deae Revert "Resolve merge conflict between main and feature/advanced-feature"
d172c03 Resolve merge conflict between main and feature/advanced-feature
aedc143 Update main.py message in main branch
c613936 Add greet function in advanced feature
f45c517 (feature/new-feature) Add main.py
95cc685 Set up the repository base documentation
f65d30a Initial commit with README.md
```

Ejecutamos el rebase interactivo
```bash
$ git rebase -i HEAD~3
```

Establecemos la nueva configuracion

```bash
pick d12194a add file_B
squash 3633723 add file_C
squash f9023ab add file_D
# Rebase e76cc73..f9023ab onto e76cc73 (3 commands)
#
# Commands:
```

Como resultado, hemos fusionado los 3 ultimos commits

```bash
W10@W10PC MINGW64 /f/UNI/25-1/CC3S2A - Desarrollo de Software/Actividad-04 (main)
$ git rebase -i HEAD~3
[detached HEAD 4bcb63d] add files B, C, and D
 Date: Mon Apr 14 10:48:50 2025 -0500
 3 files changed, 3 insertions(+)
 create mode 100644 file_B.txt
 create mode 100644 file_C.txt
 create mode 100644 file_D.txt
Successfully rebased and updated refs/heads/main.
```

El historial de commits ha quedado asi,

```bash
W10@W10PC MINGW64 /f/UNI/25-1/CC3S2A - Desarrollo de Software/Actividad-04 (main)
$ git log --oneline
4bcb63d (HEAD -> main) add files B, C, and D
e76cc73 add file_A
2c7deae Revert "Resolve merge conflict between main and feature/advanced-feature"
d172c03 Resolve merge conflict between main and feature/advanced-feature
aedc143 Update main.py message in main branch
c613936 Add greet function in advanced feature
f45c517 (feature/new-feature) Add main.py
95cc685 Set up the repository base documentation
f65d30a Initial commit with README.md
```

### 5. Visualización gráfica del historial:
Con este comando es fácil ver como las ramas se han fusionado

```bash
git log --graph --oneline --all
```

```bash
$ git log --graph --oneline --all
* 4bcb63d (HEAD -> main) add files B, C, and D
* e76cc73 add file_A
* 2c7deae Revert "Resolve merge conflict between main and feature/advanced-feature"
*   d172c03 Resolve merge conflict between main and feature/advanced-feature
|\
| * c613936 Add greet function in advanced feature
* | aedc143 Update main.py message in main branch
|/
* f45c517 (feature/new-feature) Add main.py
* 95cc685 Set up the repository base documentation
* f65d30a Initial commit with README.md
```
## Ejercicio 3: Creación y gestión de ramas desde commits específicos

Creamos una nueva rama desde el commit `2c7deae`

```bash
W10@W10PC MINGW64 /f/UNI/25-1/CC3S2A - Desarrollo de Software/Actividad-04 (main)
$ git branch bugfix/rollback-feature 2c7deae

W10@W10PC MINGW64 /f/UNI/25-1/CC3S2A - Desarrollo de Software/Actividad-04 (main)
$ git checkout bugfix/rollback-feature
Switched to branch 'bugfix/rollback-feature'
```

Realizamos un cambio en main.py y lo commiteamos

```bash
W10@W10PC MINGW64 /f/UNI/25-1/CC3S2A - Desarrollo de Software/Actividad-04 (bugfix/rollback-feature)
$ vi main.py

W10@W10PC MINGW64 /f/UNI/25-1/CC3S2A - Desarrollo de Software/Actividad-04 (bugfix/rollback-feature)
$ git add main.py

W10@W10PC MINGW64 /f/UNI/25-1/CC3S2A - Desarrollo de Software/Actividad-04 (bugfix/rollback-feature)
$ git commit -m "Fix bug in rollback feature"
[bugfix/rollback-feature 76d27c5] Fix bug in rollback feature
 1 file changed, 2 insertions(+), 1 deletion(-)
```

Fusionaremos el cambio realizado, en la rama `bugfix/rollback-feature`, en la rama `main`

```bash
W10@W10PC MINGW64 /f/UNI/25-1/CC3S2A - Desarrollo de Software/Actividad-04 (bugfix/rollback-feature)
$ git checkout main
Switched to branch 'main'

W10@W10PC MINGW64 /f/UNI/25-1/CC3S2A - Desarrollo de Software/Actividad-04 (main)
$ git merge bugfix/rollback-feature
Merge made by the 'ort' strategy.
 main.py | 3 ++-
 1 file changed, 2 insertions(+), 1 deletion(-)
```
La fusion se hizo sin conflictos, revisamos el historial de commits

```bash
W10@W10PC MINGW64 /f/UNI/25-1/CC3S2A - Desarrollo de Software/Actividad-04 (main)
$ git log --graph --oneline
*   7f8b57c (HEAD -> main) Merge branch 'bugfix/rollback-feature'
|\
| * 76d27c5 (bugfix/rollback-feature) Fix bug in rollback feature
* | 4bcb63d add files B, C, and D
* | e76cc73 add file_A
|/
* 2c7deae Revert "Resolve merge conflict between main and feature/advanced-feature"
*   d172c03 Resolve merge conflict between main and feature/advanced-feature
|\
| * c613936 Add greet function in advanced feature
* | aedc143 Update main.py message in main branch
|/
* f45c517 (feature/new-feature) Add main.py
* 95cc685 Set up the repository base documentation
* f65d30a Initial commit with README.md
```

Finalmente borramos la rama donde se hizo la actualizacion
```bash
W10@W10PC MINGW64 /f/UNI/25-1/CC3S2A - Desarrollo de Software/Actividad-04 (main)
$ git branch -d bugfix/rollback-feature
Deleted branch bugfix/rollback-feature (was 76d27c5).
```
### Ejercicio 4: Manipulación y restauración de commits con git reset y git restore
#### git reset

Editamos main.py y commiteamos
```bash
W10@W10PC MINGW64 /f/UNI/25-1/CC3S2A - Desarrollo de Software/Actividad-04 (main)
$ vi main.py

W10@W10PC MINGW64 /f/UNI/25-1/CC3S2A - Desarrollo de Software/Actividad-04 (main)
$ git add main.py

W10@W10PC MINGW64 /f/UNI/25-1/CC3S2A - Desarrollo de Software/Actividad-04 (main)
$ git commit -m "Introduce a change to be reset"
[main 576dd66] Introduce a change to be reset
 1 file changed, 1 insertion(+), 2 deletions(-)
```

Ejecutamos el git reset hard
```bash
W10@W10PC MINGW64 /f/UNI/25-1/CC3S2A - Desarrollo de Software/Actividad-04 (main)
$ git reset --hard HEAD~1
HEAD is now at 7f8b57c Merge branch 'bugfix/rollback-feature'
```

Visualizamos que con git reset no queda rastro de que alguna vez se realizo el commit

```bash
W10@W10PC MINGW64 /f/UNI/25-1/CC3S2A - Desarrollo de Software/Actividad-04 (main)
$ git log --oneline
7f8b57c (HEAD -> main) Merge branch 'bugfix/rollback-feature'
76d27c5 Fix bug in rollback feature
4bcb63d add files B, C, and D
e76cc73 add file_A
2c7deae Revert "Resolve merge conflict between main and feature/advanced-feature"
d172c03 Resolve merge conflict between main and feature/advanced-feature
aedc143 Update main.py message in main branch
c613936 Add greet function in advanced feature
f45c517 (feature/new-feature) Add main.py
95cc685 Set up the repository base documentation
f65d30a Initial commit with README.md
```

#### git restore


Realizamos un cambio en el README.md

```bash
W10@W10PC MINGW64 /f/UNI/25-1/CC3S2A - Desarrollo de Software/Actividad-04 (main)
$ echo "Another line in README" >> README.md
```

Visualizamos que existe una modificacion

```bash
W10@W10PC MINGW64 /f/UNI/25-1/CC3S2A - Desarrollo de Software/Actividad-04 (main)
$ git status
On branch main
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   README.md

no changes added to commit (use "git add" and/or "git commit -a")
```

Deshacemos los cambios realizados con `git restore` y verificamos los cambios
```bash
W10@W10PC MINGW64 /f/UNI/25-1/CC3S2A - Desarrollo de Software/Actividad-04 (main)
$ git restore README.md

W10@W10PC MINGW64 /f/UNI/25-1/CC3S2A - Desarrollo de Software/Actividad-04 (main)
$ git status
On branch main
nothing to commit, working tree clean
```

Visualizamos que `git restore` deshace los cambios que se quedaron en el workspace

### Ejercicio 5: Trabajo colaborativo y manejo de Pull Requests
En este ejercicio usaré este repositorio

```bash
W10@W10PC MINGW64 /f/UNI/25-1/CC3S2A - Desarrollo de Software/repositorio (main)
$ git checkout -b feature/activity-4-first-part
Switched to a new branch 'feature/activity-4-first-part'
```
He actualizado este README.md y lo commitearé


<!-- 
# User info

![git config](./images/1-datos.png)


# git log

![git log](./images/2-log.png)


### git log --graph --pretty=format:'%x09 %h %ar ("%an") %s'

![git log --graph --pretty=format:'%x09 %h %ar ("%an") %s'](./images/3-log_v2.png)

### git log --oneline

![git log --oneline](./images/4-log_oneline.png)


## Crear una rama desde una rama específica

![git checkout -b](./images/5-branch.png)


# Preguntas

### ¿Cómo te ha ayudado Git a mantener un historial claro y organizado de tus cambios?

Cada progreso que hago en mi código lo registro mediante un commit. Si más adelante me doy cuenta que cierta feature está fallando, puedo revisar exacatmente el commit donde hice ese cambio y corregirlo facilmente.

### ¿Qué beneficios ves en el uso de ramas para desarrollar nuevas características o corregir errores?

Es útil para separar el código que se va a usar en los dintintos ambientes: Producción, Pruebas, Desarrollo. De esta forma nos aseguramos que el código que se usa en producción sea lo mejor posible.

### Realiza una revisión final del historial de commits para asegurarte de que todos los cambios se han registrado correctamente.

Todo ok

![git log --oneline](./images/6-log.png)

### Revisa el uso de ramas y merges para ver cómo Git maneja múltiples líneas de desarrollo.

En efecto, sí.

![git log --oneline](./images/7-branches.png)

# Ejercicios

### Resolver conflictos 

Conflicto

![alt text](./images/8-conflict.png)

Resolucion del conflicto

![alt text](./images/9-conflict_solve.png)

Merge y borrar rama

![merge](./images/10-merge.png)


## Ejercicio 2: Exploración y manipulación del historial de commits

### Ver el historial detallado de commits:

```bash
git log -p
```

![git log -p](./images/11-log_p.png)


### Filtrar commits por autor

```bash
git log --author="GersoZz"
```

![git log --author](./images/12-log_author.png)
-->

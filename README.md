# AL FINAL DEL ARCHIVO SE AÑADIERON LOS COMANDOS UTILIZADOS Y LA COPIA DE LA CONSOLA DONDE SE DESARROLLÓ EL EJERCICIO 
#
#
#
# HOgit
Repositorio con ejercicios para practicar comandos básicos de git

## Qué podemos hacer

### Commits
Modificar un archivo y agregarlo al repositorio como un nuevo commit

### Branches
Creamos un branch acerca de las charlas, y decimos que nos parecen buenísimas
Pasos con los que armamos el repo de github de HOgit.


## Cómo creamos este repositorio

Inicialmente estaba creado en github (desde la WEB) con 
sólo un README. EN cualquier lugar pueden (y deberían!)
correr `git status` y `git branch -a` para chequear
en qué estado está el repositorio y en qué branch están:


Clonamos un repositorio de github con sólo un README

```
git clone https://github.com/wtpc/HOgit.git
cd HOgit
```

Editamos el archivo de README y hacemos un nuevo commit

```
vi README.md (EL ARCHIVO SE EDITÓ POR FUERA DE LA CONSOLA, AÑADIENDO ESTE TEXTO DESDE GEDIT"
.........
git add README.md
git commit
```

Ya hay un nuevo snapshot. Ahora creamos una branch

```
git branch charlas
```

y nos movemos a ella

```
git checkout charlas
```

en esta branch, editamos README.md de nuevp

```
vi README.md (EL ARCHIVO SE VOLVIÓ A MODIFICAR EXTERNAMENTE DESDE GEDIT, SOLO QUE AHORA ESTOY PARADA EN LA RAMA "CHARLAS"
...
git add README.md 
git commit
```

ahora vamos a master (que no tiene estos cambios, porque es otra branch!)

```
git checkout master
```

y a partir de master creamos una nueva branch

```
git branch ejercicios
git checkout ejercicios
```

editamos un archivo nuevo, ejercicios.md

```
vi ejercicios.md
...
git add ejercicios.md
git commit
```

Y ahora, en master, hacemos un merge de ambas branches por separado:
(fíjense que no importa que el orden sea el mismo que en el que 
las modificamos. es sensato porque las branches no se comunican)

```
git merge --no-ff ejercicios
git merge --no-ff charlas
```

la opción --no-ff sirve para que no "mezcle" las dos branches, y queda más prolijo el network. recomienod que la usen siempre, pero no es fundamental.

si quieren ver cómo quedó la historia del repo:

```
git log --oneline --graph
```

finalmente, hacemos un push de todas las branches:

```
git push -u origin master
git push -u origin ejercicios
git push -u origin charlas
```

y listo! en nuestra cuenta de github ya tiene que estar subido. pueden ver el network de github que les va a mostrar la historia

Luego también editamos este readme para agregar los comandos con los que hicimos el repositorio


```
vi README.md
...
git add README.md
git commit
```

y el push

```
git push
```

###### COMANDOS #######
# COMANDOS UTILIZADOS PARA EL DESARROLLO DEL EJERCICIO DE GIT

```
$ git clone https://github.com/leilaguzman/HOgit.git
$ cd HOgit
$ ls
$ ls -a
$ git status
$ git add README.md
$ git status
$ git commit
$ git config --global user.email "leilaguzman95@gmail.com"
$ git config --global user.name "Leila"
$ git status
$ git commit
$ git status
$ git branch -a
$ gir branch charlas
$ git checkout charlas
$ git branch
$ git status
$ git add README.md
$ git commit
$ git status
$ git checkout master
$ git branch ejercicios
$ git branch -a
$ git checkout ejercicios
$ git branch -a
$ git add ejercicios.md
$ git commit
$ git status
$ git checkout master
$ git merge --no-ff ejercicios
$ git merge --no-f charlas
$ git log --oneline --graph
$ git status
$ git push -u origin master
$ git push -u origin ejercicios
$ git push -u origin charlas
$ git add README.md
$ git commit
$ git push 

```

## COPIA DE LA CONSOLA DONDE SE DESARROLLÓ DEL EJERCICIO 
```
lachinis@ubuntu-lachinis:~$ git --version
```
git version 2.25.1
```
lachinis@ubuntu-lachinis:~$ git clone https://github.com/leilaguzman/HOgit.git
```
Clonando en 'HOgit'...
remote: Enumerating objects: 21, done.
remote: Total 21 (delta 0), reused 0 (delta 0), pack-reused 21
Desempaquetando objetos: 100% (21/21), 3.17 KiB | 141.00 KiB/s, listo.
```
lachinis@ubuntu-lachinis:~$ cd HOgit
lachinis@ubuntu-lachinis:~/HOgit$ ls
```
ejercicios.md  README.md
```
lachinis@ubuntu-lachinis:~/HOgit$ ls -a
```
.  ..  ejercicios.md  .git  README.md
```
lachinis@ubuntu-lachinis:~/HOgit$ git status
```
En la rama master
Tu rama está actualizada con 'origin/master'.

Cambios no rastreados para el commit:
  (usa "git add <archivo>..." para actualizar lo que será confirmado)
  (usa "git restore <archivo>..." para descartar los cambios en el directorio de trabajo)
	modificado:     README.md

sin cambios agregados al commit (usa "git add" y/o "git commit -a")
```
lachinis@ubuntu-lachinis:~/HOgit$ git add README.md 
lachinis@ubuntu-lachinis:~/HOgit$ git status
```
En la rama master
Tu rama está actualizada con 'origin/master'.

Cambios a ser confirmados:
  (usa "git restore --staged <archivo>..." para sacar del área de stage)
	modificado:     README.md

```
lachinis@ubuntu-lachinis:~/HOgit$ git commit -m TEXTO AÑADIDO DESDE GEDIT leilaguzman95@gmail.com
```
error: ruta especificada 'AÑADIDO' no concordó con ningún archivo(s) conocido por git
error: ruta especificada 'DESDE' no concordó con ningún archivo(s) conocido por git
error: ruta especificada 'GEDIT' no concordó con ningún archivo(s) conocido por git
error: ruta especificada 'leilaguzman95@gmail.com' no concordó con ningún archivo(s) conocido por git
```
lachinis@ubuntu-lachinis:~/HOgit$ git commit
```

*** Por favor cuéntame quien eres.

Corre

  git config --global user.email "you@example.com"
  git config --global user.name "Tu Nombre"

para configurar la identidad por defecto de tu cuenta.
Omite --global para configurar tu identidad solo en este repositorio.

fatal: no es posible auto-detectar la dirección de correo (se obtuvo 'lachinis@ubuntu-lachinis.(none)')
```
lachinis@ubuntu-lachinis:~/HOgit$ git config --global user.email "leilaguzman95@gmail.com"
lachinis@ubuntu-lachinis:~/HOgit$ git config --global user.name "Leila"
lachinis@ubuntu-lachinis:~/HOgit$ git status
```
En la rama master
Tu rama está actualizada con 'origin/master'.

Cambios a ser confirmados:
  (usa "git restore --staged <archivo>..." para sacar del área de stage)
	modificado:     README.md

```
lachinis@ubuntu-lachinis:~/HOgit$ git commit
```
[master 67db6f3] Primer texto añadido desde Gedit
 1 file changed, 1 insertion(+), 1 deletion(-)
```
lachinis@ubuntu-lachinis:~/HOgit$ git status
```
En la rama master
Tu rama está adelantada a 'origin/master' por 1 commit.
  (usa "git push" para publicar tus commits locales)

nada para hacer commit, el árbol de trabajo está limpio
```
lachinis@ubuntu-lachinis:~/HOgit$ git branch -a
```
* master
  remotes/origin/HEAD -> origin/master
  remotes/origin/charlas
  remotes/origin/ejercicios
  remotes/origin/master
```
lachinis@ubuntu-lachinis:~/HOgit$ git branch charlas
lachinis@ubuntu-lachinis:~/HOgit$ git checkout charlas
```
Cambiado a rama 'charlas'
```
lachinis@ubuntu-lachinis:~/HOgit$ git branch
```
* charlas
  master
```
lachinis@ubuntu-lachinis:~/HOgit$ git status
```
En la rama charlas
Cambios no rastreados para el commit:
  (usa "git add <archivo>..." para actualizar lo que será confirmado)
  (usa "git restore <archivo>..." para descartar los cambios en el directorio de trabajo)
	modificado:     README.md

sin cambios agregados al commit (usa "git add" y/o "git commit -a")
```
lachinis@ubuntu-lachinis:~/HOgit$ git add README.md
lachinis@ubuntu-lachinis:~/HOgit$ git commit -m Segundo Texto añadido a README.d
```
error: ruta especificada 'Texto' no concordó con ningún archivo(s) conocido por git
error: ruta especificada 'añadido' no concordó con ningún archivo(s) conocido por git
error: ruta especificada 'a' no concordó con ningún archivo(s) conocido por git
error: ruta especificada 'README.d' no concordó con ningún archivo(s) conocido por git
```
lachinis@ubuntu-lachinis:~/HOgit$ git commit
```
[charlas 64850f7] Segundo texto añadido a "README"
 1 file changed, 2 insertions(+), 2 deletions(-)
```
lachinis@ubuntu-lachinis:~/HOgit$ git status
```
En la rama charlas
nada para hacer commit, el árbol de trabajo está limpio
```
lachinis@ubuntu-lachinis:~/HOgit$ git checkout master
```
Cambiado a rama 'master'
Tu rama está adelantada a 'origin/master' por 1 commit.
  (usa "git push" para publicar tus commits locales)
```
lachinis@ubuntu-lachinis:~/HOgit$ git branch ejercicios
lachinis@ubuntu-lachinis:~/HOgit$ git branch -a
```
  charlas
  ejercicios
* master
  remotes/origin/HEAD -> origin/master
  remotes/origin/charlas
  remotes/origin/ejercicios
  remotes/origin/master
```
lachinis@ubuntu-lachinis:~/HOgit$ git checkout ejercicios
```
Cambiado a rama 'ejercicios'
```
lachinis@ubuntu-lachinis:~/HOgit$ git branch -a
```
  charlas
* ejercicios
  master
  remotes/origin/HEAD -> origin/master
  remotes/origin/charlas
  remotes/origin/ejercicios
  remotes/origin/master
```
lachinis@ubuntu-lachinis:~/HOgit$ git add ejercicios.md
lachinis@ubuntu-lachinis:~/HOgit$ git commit
```
[ejercicios 274357e] Tercer texto añadido en este ejercicio, el primero para el archivo "ejercicios.md"
 1 file changed, 1 insertion(+)
```
lachinis@ubuntu-lachinis:~/HOgit$ git status
```
En la rama ejercicios
nada para hacer commit, el árbol de trabajo está limpio
```
lachinis@ubuntu-lachinis:~/HOgit$ git checkout master
```
Cambiado a rama 'master'
Tu rama está adelantada a 'origin/master' por 1 commit.
  (usa "git push" para publicar tus commits locales)
```
lachinis@ubuntu-lachinis:~/HOgit$ git merge --no-ff ejercicios
```
Merge made by the 'recursive' strategy.
 ejercicios.md | 1 +
 1 file changed, 1 insertion(+)
```
lachinis@ubuntu-lachinis:~/HOgit$ git merge --no-f charlas
```
Merge made by the 'recursive' strategy.
 README.md | 4 ++--
 1 file changed, 2 insertions(+), 2 deletions(-)
```
lachinis@ubuntu-lachinis:~/HOgit$ git log --oneline --grapgh
```
fatal: argumento no reconocido: --grapgh
```
lachinis@ubuntu-lachinis:~/HOgit$ git log --oneline --graph
```
*   c2cc4d4 (HEAD -> master) Merge branch 'charlas'
|\  
| * 64850f7 (charlas) Segundo texto añadido a "README"
* |   aca8115 Merge branch 'ejercicios'
|\ \  
| |/  
|/|   
| * 274357e (ejercicios) Tercer texto añadido en este ejercicio, el primero para el archivo "ejercicios.md"
|/  
* 67db6f3 Primer texto añadido desde Gedit
* 373ee43 (origin/master, origin/HEAD) Cambiado protocolo por defecto a https
* ed74bb6 Agregados comandos
*   5339e09 Merge branch 'charlas'
|\  
| * 5ffe580 (origin/charlas) Más cosas de git!
* |   ab6622e Merge branch 'ejercicios'
|\ \  
| |/  
|/|   
| * c0e2aa2 (origin/ejercicios) Agregamos un nuevo archivo
|/  
* 0896d0e Info de qué hacer
* de70e76 Initial commit
 ESC
[1]+  Detenido                git log --oneline --graph
^Z       
```
lachinis@ubuntu-lachinis:~/HOgit$ git status
```
En la rama master
Tu rama está adelantada a 'origin/master' por 5 commits.
  (usa "git push" para publicar tus commits locales)

nada para hacer commit, el árbol de trabajo está limpio
```
lachinis@ubuntu-lachinis:~/HOgit$ git push -u origin master
```
Username for 'https://github.com': leilaguzman
Password for 'https://leilaguzman@github.com': 
Enumerando objetos: 15, listo.
Contando objetos: 100% (15/15), listo.
Compresión delta usando hasta 4 hilos
Comprimiendo objetos: 100% (12/12), listo.
Escribiendo objetos: 100% (12/12), 1.55 KiB | 264.00 KiB/s, listo.
Total 12 (delta 3), reusado 0 (delta 0)
remote: Resolving deltas: 100% (3/3), completed with 1 local object.
To https://github.com/leilaguzman/HOgit.git
   373ee43..c2cc4d4  master -> master
Rama 'master' configurada para hacer seguimiento a la rama remota 'master' de 'origin'.
```
lachinis@ubuntu-lachinis:~/HOgit$ git push -u origin ejercicios
```
Username for 'https://github.com': leilaguzman
Password for 'https://leilaguzman@github.com': 
Total 0 (delta 0), reusado 0 (delta 0)
To https://github.com/leilaguzman/HOgit.git
   c0e2aa2..274357e  ejercicios -> ejercicios
Rama 'ejercicios' configurada para hacer seguimiento a la rama remota 'ejercicios' de 'origin'.
```
lachinis@ubuntu-lachinis:~/HOgit$ git push - origin charlas
```
fatal: ruta extraña '-' bloqueada
```
lachinis@ubuntu-lachinis:~/HOgit$ git push -u origin charlas
```
Username for 'https://github.com': leilaguzman
Password for 'https://leilaguzman@github.com': 
remote: Invalid username or password.
fatal: Autenticación falló para 'https://github.com/leilaguzman/HOgit.git/'
```
lachinis@ubuntu-lachinis:~/HOgit$ git push -u origin charlas
```
Username for 'https://github.com': leilaguzman
Password for 'https://leilaguzman@github.com': 
Total 0 (delta 0), reusado 0 (delta 0)
To https://github.com/leilaguzman/HOgit.git
   5ffe580..64850f7  charlas -> charlas
Rama 'charlas' configurada para hacer seguimiento a la rama remota 'charlas' de 'origin'.

```

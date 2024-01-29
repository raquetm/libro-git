# Ejercicios ramas git
Partiendo del repositorio libro creado en el ejercicio anterior:
Crea una nueva rama bibliografia y muestra las ramas del respositorio.
```bash
git branch bibliografia
git branch
```
      bibliografia
    * master

Cambia a la rama bibliografía y crea el fichero bibliografía.txt y añade la siguiente referencia:
```bash
git checkout bibliografia
nano bibliografia.txt
```
    caperucita roja,  Trina Schart Hyman, Charles Perrault

Comitea los cambios con el mensaje “Añadida primera referencia bibliográfica”.
```bash
git add bibliografia.txt
git commit -m "Añadida primera referencia bibliográfica"
```
    [bibliografia 4fcea41] Añadida primera referencia bibliografica
    1 file changed, 1 insertion(+)
    create mode 100644 bibliografia.txt


Fusionar la rama bibliografía con la rama master y eliminar la rama bibliografía.
```bash
git checkout master
git merge bibliografia
```
    Actualizando 09eeef5..4fcea41
    Fast-forward
    bibliografia.txt | 1 +
    1 file changed, 1 insertion(+)
    create mode 100644 bibliografia.txt

```bash
git branch -d bibliografia
```
    Eliminada la rama bibliografia (era 4fcea41).

Crea la rama harrypotter. En esta rama modifica el fichero bibliografía.txt para que contenga las siguientes referencias:

    Harry Potter y la piedra filosofal, J. K. Rowling
    Harry Potter y el cáliza de fuego, J. K. Rowling

```bash
git branch harrypotter
git checkout harrypotter
```
Comitea los cambios con el mensaje “Añadida bibliografía de harry potter”.
```bash
git add bibliografia.txt
git commit -m "Añadida bibliografía de harry potter"
```
    [harrypotter bb0aaa1] Añadida bibliografía de harry potter
    1 file changed, 2 insertions(+), 1 deletion(-)

En la rama master modifica el fichero bibliografía.txt y añade la siguiente línea:

    El Rey León, Rob Minkoff, Roger Allers 

```bash
git checkout master
nano bibliografia.txt
```
Fusiona la rama harrypotter con la rama master. Resuelve el conflicto y comitea los cambios.
```bash
git stash save "antes de la fusión"
git merge harrypotter
```
    Actualizando 4fcea41..bb0aaa1
    Fast-forward
    bibliografia.txt | 3 ++-
    1 file changed, 2 insertions(+), 1 deletion(-)

```bash
git add bibliografia.txt
git commit -m "bibliografía final"
```

# Ejercicios repositorios remotos git 
Crea un repositorio en GitHub con el nombre libro-git. Añádelo como url remota en nuestro repositorio local de libro creado en el ejercicio anterior.
Añade todo lo que tenemos que el repositorio libro al repositorio remoto y comprueba que los cambios están subidos correctamente.
```bash
git remote -v
git remote add origin https://github.com/raquetm/libro-git.git
```
Colabora en el repositorio remoto de otro compañero. Clona su repositorio. Añade el fichero autores.txt que contenga tu nombre y tu correo electrónico. Haz un commit y sube los cambios al repositorio remoto de tu compañero.

```bash
cd repos
git clone https://github.com/MiguelTorres23/libro-git.git
```
    Clonando en 'libro-git'...
    remote: Enumerating objects: 18, done.
    remote: Counting objects: 100% (18/18), done.
    remote: Compressing objects: 100% (9/9), done.
    remote: Total 18 (delta 4), reused 17 (delta 3), pack-reused 0
    Desempaquetando objetos: 100% (18/18), 40.69 KiB | 534.00 KiB/s, listo.

```bash
nano autores.txt
```

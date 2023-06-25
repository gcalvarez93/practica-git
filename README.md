# Practica Git KeepCoding

## ¿Qué comando utilizaste para el paso 11?¿Por qué?  
`git reset --hard HEAD~1`  
Porque al deshacer el último commit vamos al commit que es el padre del actual, esto lo hacemos con `git reset HEAD~1`, y como queremos  
descartar los cambios que hemos realizado, utilizamos la opción `--hard`.  

## ¿Qué comando o comandos utilizaste en el paso 12? ¿Por qué?
`git reset --hard HEAD@{1}`
Porque al rehacer el commit en este caso, estamos yendo al hijo del commit actual, podríamos haber ejecutado dos comandos: `git reflog` y después  
`git reset --hard <hash_commit>`, pero en este caso, el commit de donde venimos se puede visitar utilizando HEAD@{1} ya que estamos situados 
en el padre del commit al que queremos ir.

## El merge del paso 13, ¿Causó algún conflicto? ¿Por qué?  
No causa ningún conflicto ya que la rama *styled* fue creada a partir de la rama *main*, por tanto, *styled* incluye el trabajo de *main*,
por lo que devuelve *Already up-to-date*.  

## El merge del paso 19, ¿Causó algún conflicto? ¿Por qué?
Si, causó conflicto debido a que el commit al que apunta *styled* y el commit al que apunta *htmlify* son hijos de un mismo commit, es decir,
ninguna de estas ramas incluye el trabajo de la otra, además, estos commits han modificado las mismas líneas del mismo archivo y git no  
sabe cual es el resultado que queremos conservar, y por lo tanto, no podemos mergear las ramas. Es un merge no fast forward.  

## El merge del paso 21, ¿Causó algún conflicto? ¿Por qué?
No causó conflicto ya que es un merge fast-forward, lo único que hay que hacer es mover el puntero de la rama *main* al commit al que
apunta la rama *styled*.

## ¿Qué comando o comandos utilizaste en el paso 25?
* `git config --global alias.graph "log --decorate --graph"`  
* `git graph`

El primer comando lo utilizo para para crear un alias para el grafo, usé el modificador `--decorate` para verlo con
colores, etiquetas y ramas, y el modificador `--graph` para mostrar el árbol de commits. El segundo comando lo utilicé para ejecutar el grafo.

## El merge del paso 26, ¿Podría ser fast forward? ¿Por qué?
Sí, porque *main* es el padre de *title*, por tanto, están en la misma línea temporal. Todo el trabajo de *main* está incluido en la
rama title.

## ¿Qué comando o comandos utilizaste en el paso 27?
`git reset HEAD~1`  
Porque deshacer el último commit es ir al commit padre del actual. No he utilizado la opción `hard` para no perder los cambios en el working copy.  

## ¿Qué comando o comandos utilizaste en el paso 28?  
`git reset --hard HEAD`  
Ya estoy situados en el commit que quiero, por tanto, lo que hago simplemente es restaurar el working copy a como estaba en el
commit actual. Utilizando `HEAD` me refiero al commit actual.

## ¿Qué comando o comandos utilizaste en el paso 29?   
`git branch -D title`
Como la rama *title* está por encima de la rama *main*, no me deja eliminarla con la opción -d, por lo que tengo que eliminarla de manera
forzada con la opción -D.

## ¿Qué comando o comandos utilizaste en el paso 30?  
* `git reflog`
* `git reset --hard 2580882`

El primer comando es para encontrar el commit donde realizo el merge de la rama *main* con *title*, y el segundo para acceder al commit
dejando el working copy en el estado en el que estaba.

## ¿Qué comando o comandos usaste en el paso 32?  
* `git log`
* `git reset --hard 0d484e1f90946f31262bfcbff35f484b2e8a5c1a`

El primer comando lo uso para ver la lista de commits de la rama *main*, y poder localizar el commit inicial, y el segundo para moverme hasta él. He 
utilizado el modificador `--hard` para dejar el working copy como en el momento en el que se realizó el commit inicial.

## ¿Qué comando o comandos usaste en el punto 33?
* `git reflog`
* `git reset --hard 2580882`

El primer comando lo uso para ver los pasos que he seguido hasta llegar al commit actual, y así poder localizar el commit al que quiero moverme. Y el
segundo para moverme hasta el dejando el working copy tal y como estaba.

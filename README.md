- ¿Qué comando utilizaste en el paso 11? ¿Por qué? 

    `git reset --hard HEAD~1`
	
	*Utilicé ese comando porque quería ir un paso atrás y deshacer el commit, modificando el "Working Copy"*

- ¿Qué comando o comandos utilizaste en el paso 12? ¿Por qué? 

	`git reflog`

	*Primero utilicé "reflog" para buscar el punto exacto en el que estaba antes de deshacer el commit en el paso anterior*

	`git reset --hard bbe3e3a`

	*Aquí quería deshacer el último paso realizado (cuando deshice el commit perdiendo los datos del "Working Copy"). Es por ello que "bbe3e3a" hace referencia a la posición del paso en el que estábamos antes de deshacer el primer commit.*

- El merge del paso 13, ¿Causó algún conflicto? ¿Por qué? 

	Usé el comando (desde la rama "styled"):

	`git merge master`

	No causó ningún conflicto aún habiendo modificaciones en el archivo git-nuestro.md (dentro de la rama "styled"), arrojando el mensaje "Already up to date".

	Esto se debe a que la rama "styled" es hija de "master", por lo que "styled" ya tiene "master" y no se han producido cambios en ella, y entonces nos dice que ya se encuentra actualizada. Para hacer el merge correctamente habría que hacerlo desde "master", para crear así un nuevo "commit" con el contenido de "styled".

- El merge del paso 19, ¿Causó algún conflicto? ¿Por qué? 

	Usé los siguientes comandos para realizar el "merge":

	`git checkout styled` (Desde la rama "htmlify")

	`git merge htmlify` (Ya desde la rama "styled")

	El "merge" si causó conflictos. El motivo es porque ambas ramas son hijas de "master", pero se han realizado cambios en ambas ramas. Entonces, al haber realizado cambios desde "htmlify" en el archivo git-nuestro.md y querer desde la rama "styled" absorber la rama "htmlify", GIT detecta que el archivo git-nuestro.md de cada rama es diferente, por lo que nos avisa de que debemos resolver esos conflictos antes de completar el "merge".

- El merge del paso 21, ¿Causó algún conflicto? ¿Por qué? 

	El "merge" desde "master" a "styled" no causó conflictos y se realizó un "merge con fast-forward". El motivo es porque la rama "master" no ha sido modificada desde la creación de la rama hija "styled", por lo que la rama "master" se desplaza hasta el último "commit" de la rama "styled" para poder tener acceso a todos los cambios de esa rama. Si el archivo git-nuestro.md hubiese sido modificado en la rama "master" antes del "merge" con "styled", entonces sí hubiese habido conflictos y tendríamos que haberlos resuelto antes de completar el "merge".

- ¿Qué comando o comandos utilizaste en el paso 25? 

	Usé el siguiente comando:

	`git log --graph`

	Luego usé también el siguiente, para verlo de forma simplificada en una línea:

	`git log --graph --oneline`

- El merge del paso 26, ¿Podría ser fast forward? ¿Por qué? 

	Sí podría haber sido "fast-forward". Porque desde la rama "master" no se ha creado un "commit" nuevo después de que se creara el "commit" de la rama "title".

- ¿Qué comando o comandos utilizaste en el paso 27? 

	Usé el siguiente comando (para no perder los cambios en "Working Copy"):

	`git reset HEAD~1`

- ¿Qué comando o comandos utilizaste en el paso 28? 

	Primero usé el siguiente comando para ver los cambios:

	`git status`

	Luego utilicé el comando:

	`git restore git-nuestro.md`

- ¿Qué comando o comandos utilizaste en el paso 29? 

	Eliminé la rama "title" con el comando:

	`git branch -D title`

- ¿Qué comando o comandos utilizaste en el paso 30? 

	Primero usé el siguiente comando para ver los identificadores de los cambios realizados:

	`git reflog`

	Luego utilicé el siguiente comando para volver al paso donde se hizo el "merge" y así "deshacer lo deshecho":

	`git reset --hard 2790d1c`

- ¿Qué comando o comandos usaste en el paso 32? 

	Primero usé el siguiente comando para ver los identificadores de los cambios realizados:

	`git reflog`

	Luego utilicé el siguiente comando para volver al "commit" inicial:

	`git reset 00ac4c8`

- ¿Qué comando o comandos usaste en el punto 33?

	Primero usé el siguiente comando para ver los identificadores de los cambios realizados:

	`git reflog`

	Luego utilicé el siguiente comando para volver al estado final, cuando puse título al poema:

	`git reset c8bb202`

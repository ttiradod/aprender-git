\# Aprendiendo Git y GitHub



Este repositorio lo he creado para aprender desde cero cómo funciona Git y cómo subir mis proyectos a GitHub.



\## Diferencia entre Git y GitHub



\* \*\*Git\*\* controla las versiones de mis proyectos en mi ordenador.

\* \*\*GitHub\*\* guarda una copia de esos proyectos en Internet.

\* Git y GitHub no se sincronizan automáticamente.



\## Flujo básico de trabajo



```text

Modificar un archivo

&#x20;       ↓

git status

&#x20;       ↓

git add

&#x20;       ↓

git commit

&#x20;       ↓

git push

&#x20;       ↓

Proyecto actualizado en GitHub

```



\## Comandos para moverme por las carpetas



\### Ver en qué carpeta estoy



```bash

pwd

```



\### Entrar en una carpeta



```bash

cd nombre-carpeta

```



Ejemplo:



```bash

cd aprender-git

```



También puedo utilizar una ruta completa:



```bash

cd "/c/Users/teres/Desktop/PYTHON/aprender-git"

```



\### Ver los archivos de una carpeta



```bash

ls

```



La primera letra es una `l` minúscula.



\### Ver también los archivos ocultos



```bash

ls -a

```



En un repositorio Git permite ver la carpeta oculta `.git`.



\## Configuración inicial de Git



\### Configurar mi nombre



```bash

git config --global user.name "Teresa Tirado"

```



\### Configurar mi correo



```bash

git config --global user.email "teresat250@gmail.com"

```



Estos datos se guardan como autora de los commits. No tengo que volver a escribirlos en cada commit.



\### Consultar el nombre configurado



```bash

git config --global user.name

```



\### Consultar el correo configurado



```bash

git config --global user.email

```



\## Crear un repositorio local



\### Inicializar Git en una carpeta



```bash

git init

```



`init` significa inicializar.



Este comando convierte la carpeta actual en un repositorio Git y crea una carpeta oculta llamada `.git`, donde se almacena el historial.



No sube nada a GitHub.



\## Consultar el estado del proyecto



```bash

git status

```



`git status` no modifica nada. Solo informa de:



\* Archivos nuevos.

\* Archivos modificados.

\* Archivos preparados.

\* Cambios pendientes de guardar.

\* Rama en la que estoy.



Regla para recordarlo:



```text

status = mirar

```



\## Preparar archivos



\### Preparar un archivo concreto



```bash

git add hola.py

```



\### Preparar todos los cambios



```bash

git add .

```



`git add` selecciona los cambios que entrarán en el siguiente commit.



No guarda todavía una versión y tampoco sube nada a GitHub.



Regla para recordarlo:



```text

add = seleccionar o preparar

```



\## Crear un commit



```bash

git commit -m "Añade el primer programa en Python"

```



Un commit es un punto de guardado dentro del historial de Git.



El mensaje debe explicar brevemente qué cambio he realizado.



Regla para recordarlo:



```text

commit = guardar una versión local

```



\### Corregir el mensaje del último commit



```bash

git commit --amend -m "Nuevo mensaje correcto"

```



Esto sustituye el último commit por otro con el mensaje corregido.



Si el commit ya estaba en GitHub, hay que actualizarlo con cuidado:



```bash

git push --force-with-lease

```



\## Consultar el historial



\### Ver el historial resumido



```bash

git log --oneline

```



Ejemplo:



```text

807b6ab Añade el primer programa en Python

```



Cada commit tiene un identificador propio.



\## Conectar el repositorio con GitHub



\### Añadir un repositorio remoto



```bash

git remote add origin https://github.com/ttiradod/aprender-git.git

```



Significado:



\* `remote`: repositorio que está fuera de mi ordenador.

\* `add`: añadir una conexión.

\* `origin`: nombre habitual que se le da al repositorio principal de GitHub.

\* La URL indica dónde está el repositorio.



Este comando conecta ambos repositorios, pero todavía no sube archivos.



\### Ver los repositorios remotos configurados



```bash

git remote -v

```



Muestra la dirección utilizada para:



\* `fetch`: traer cambios.

\* `push`: enviar cambios.



\### Consultar solamente la dirección de `origin`



```bash

git config --get remote.origin.url

```



\## Subir los commits a GitHub



La primera vez:



```bash

git push -u origin main

```



Significado:



\* `push`: enviar commits a GitHub.

\* `origin`: repositorio remoto.

\* `main`: rama principal.

\* `-u`: recordar la conexión entre `main` y `origin/main`.



Después de hacerlo una vez, normalmente basta con:



```bash

git push

```



Regla para recordarlo:



```text

push = ordenador → GitHub

```



`git push` solo sube commits. No sube cambios que todavía no tengan commit.



\## Abrir, ver y ejecutar archivos



\### Abrir un archivo con el Bloc de notas



```bash

notepad hola.py

```



\### Abrir un archivo con Visual Studio Code



```bash

code hola.py

```



\### Abrir toda la carpeta actual en Visual Studio Code



```bash

code .

```



El punto `.` representa la carpeta actual.



\### Ver el contenido en Git Bash



```bash

cat hola.py

```



\### Ejecutar un programa de Python



```bash

python hola.py

```



\## Otros comandos útiles



\### Ver exactamente qué líneas he modificado



```bash

git diff

```



Muestra los cambios que todavía no he preparado con `git add`.



\### Descartar cambios no guardados en un commit



```bash

git restore hola.py

```



Devuelve el archivo a la versión del último commit.



Hay que utilizarlo con cuidado, porque elimina los cambios locales que todavía no estén guardados.



\### Descargar cambios desde GitHub



```bash

git pull

```



Regla para recordarlo:



```text

pull = GitHub → ordenador

```



\### Descargar un repositorio completo



```bash

git clone URL\_DEL\_REPOSITORIO

```



Crea una carpeta con los archivos, el historial y la conexión con GitHub.



\## Significado de algunos mensajes



\### `Untracked files`



Git ve el archivo, pero todavía no lo está controlando.



Solución:



```bash

git add nombre-archivo

```



\### `Changes not staged for commit`



El archivo ha cambiado, pero todavía no está preparado.



\### `Changes to be committed`



El archivo está preparado y entrará en el siguiente commit.



\### `Nothing to commit, working tree clean`



Todos los cambios actuales están guardados en commits.



No significa necesariamente que estén subidos a GitHub.



\## Resumen principal



```text

git status = mirar el estado

git add = preparar cambios

git commit = guardar una versión local

git push = subir los commits a GitHub

git pull = traer cambios desde GitHub

```



\## Proceso habitual



```bash

git status

git add nombre-archivo

git commit -m "Descripción del cambio"

git push

```








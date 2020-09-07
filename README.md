## Learn-The-Git
Tutorial para los divers | Cómo funciona Git | Los comandos más importantes | GitFlow | blabla



'Git is the most popular distributed version control system' Esto significa que cada desarrollador tiene el repositorio viviendo en su máquina

#Instalando Git
En linux: sudo apt-get install git
En Mac: Solo bajatelo de la página de Git
Corre git --version para asegurarte tienes la versión más reciente
Ahora necesitas agregar variables globales para poder identificarte
1. git config --global user.name "Yamanakster"
2. git config --global user.name "yamanakster@dive.ai"
3. git config --list (Este solo para ver que hayas metido bien los parámetros)



git init: Te crea una instancia de Git

Antes de hacer tu primer commit
Verifica el status del git con 
git status:
Este comando te va a decir que tienes X Untracked Files 

Cuando hay files que no quieres agregar agregar a tu git crea un
touch .gitignore
aquí puedes ir escribiendo todos los files que quieres que Git ignore. Puedes usar wildcards
Con eso ya no te aparecerá el file en Untracked Files

Para agregar archivos a la staging area debes de darle
git add <file> (O puedes usar -A para agregar a todos)
y ya están disponibles para ser commited
con git reset <file> los puedes quitar

Para hacer commit debes poner git commit -m "Comentario con el cual quieres subir el o los archivos" <file>
  
Para ver el historial de lo que se ha hecho puedes usar el command
git log


git help verb para preguntar por un comando que no entiendes y te lleva al man page

#Para rastrear un proyecto remóto (El caso más usual)
Digamos que el repositorio ya existe y quieres clonartelo.
Entonces haces
git clone <url> <lugar dónde clonar> (puedes poner . para hacerlo en el current directory)

*Cuando lo intentes hacer debes clonarlo a un directorio vacío*

git remote -v: Te dice en donde vive el clon del repositorio
git branch -a: Te muestra las ramas que tiene el repositorio


#Haciendo cambios al código
Una vez que clonas el repositorio lo siguiente es interactuar con él
Lo primero es hacer las modificaciones que necesites
Después de hacerlas. Puedes poner
git status y verás que git te muestra que el archivo que modificaste no está en staged aún

Con git diff: Te muestra los cambios que le hiciste a tu código

Primero haces commit a estos cambios de manera local. Pero ya que le diste commit quieres empujarlo al repositorio.

Primero 
git pull origin master: Va a jalar el repositorio con los cambios más recientes desde la última vez que lo hiciste. Aquí origin es el nombre del repositorio y master es el branch
git push origin master: En esta branch se va a subir nuestro código

Normalmente no trabajarías en el main de tu Git. Lo más común es hacerlo en una branch
















# Senado Mexicano
Web scrapping de la página del senado | Limpieza y almacenamiento en MongoDB | Extracción y traducción a pandas | Gráficas descriptivas con Seaborn



## About 

* Este proyecto recaba información de la página del [Senado](https://www.senado.gob.mx/64/) mexicano de cada Senador. Utilizando Scrapy se recaba información detallada de su
semblanza, intervenciones, votaciones, información personal y asistencias. Esta data se guarda en un NoSQL utilizando PyMongo para después extraerse y obtener información 
descriptiva de la data.


## Requirements

Este proyecto utiliza Python. También se requiere bajar MongoDB para generar las bases de datos.

Vas a necesitar descargar las siguientes herramientas
1. Python (3.7.8 recommended)
2. MongoDB Community Edition (4.2 recommended)
3. Git (obviously)

Para el Web Scrapping utilizaremos Scrappy. Aquí les dejo la instalación para Windows que es un poco más compleja que en UNIX (que solo es pip install scrapy)
* Vamos a [Python Binaries para Windows](https://www.lfd.uci.edu/~gohlke/pythonlibs/#twisted) en #twisted
* Descarga la versión adecuada a tu versión de Python y versión de Windows
* Abre la terminal en donde descargaste el file y dale pip install "nombre del archivo que descargaste"

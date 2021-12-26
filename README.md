Resumen general de Git y Github

Git es un software de control de versiones, para el mantenimiento de versiones asi mismo trabajando localmente desde tu computador haciendo multiples tareas como push, merge, commit, entre otros que mostrare a continuacion

Iniciando con git en la terminal de ubuntu la forma ideal de iniciar git (git init) posteriormente agregando los archivos o archivo (git add) con un punto o agregando cada archivo manualmente y agregando un comentario siendo indispensable para futuras versiones (git commit -m "MENSAJE") verificando con (git log) para mostrar cambios en el archivo y mostrar todos los "commits" de el proyecto mencionado o usando un (git show) para mostrar los "commits" y a la vez comparando los cambios en la terminal 

Explicando un poco el flujo de trabajo de git dentro de sus servidores: En esto podemos mencionar 3 lugares dentro de git el DIRECTORIO, STAGING Y REPOSITORIO 
al iniciar un proyecto de git en la carpeta se crea la carpeta .git (oculto en los archivos) a su vez creando la base de datos de git dentro de la carpeta elegida para poder guardar los repositorios, y en esta etapa los archivos estan de modo (UNTRACKED) y es necesario poder agregar (git add) para que pueda ser (TRACKED)  EN ESTA ETAPA ESTA EN LA BASE DE DATOS (STAGING) esperando a ser enviada con un commit  a la rama MASTER AGREGANDO VERSIONES EN EL PROCESO (REPOSITORIO)

A pesar de esto no acaba ahi ya que, existen ramas que pueden ser añadidas (git branch [NOMBRE]) para poder cambiar entre ramas secundarias, cabe recalcar que al ir de rama en rama cada uno de ellos modificara los archivos segun la rama señalada y esto se logra con (git checkout [RAMA]) IMPORTANTE MENCIONAR QUE ES NECESARIO ENVIAR A LA BASE DE DATOS ANTES DE PODER CAMBIAR DE RAMA O EXISTE LA POSIBILIDAD DE ROMPER TODO EL CODIGO REALIZADO EN LA RAMA ACTUAL.
           
Es muy util saber en que rama encontranos y esto se logra con (git show) o que seria mejor usando (git branch) señalando en que rama te encuentras actualmente
todo esto permite tener multiples ramas y trabajar en el proyecto detalladamente (header, footer, main) esto siendo en desarrolo web
Mencionando lo maravilloso de esto podemos unir ramas como haciendo un merge: Ubicandonos en la rama master y que nuestro objetivo sea jalar el codigo de nuestra rama "header" usamos (git merge [RAMA]) y simplemente entrando al proyecto posteriormente verificandolo

A pesar de los grandes beneficios que es usar git para el sistema de versiones esto puede causar conflictos si 2 personas modifican la misma linea de codigo
y esto se soluciona de 2 maneras 

1ro: Esto se arregla estando en la rama master y borrando lo innecesario, quedandose con lo que se necesita y corrigiendo un conflicto
2do: Y la otra solucion te lo da si tienes instalado VisuaStudio es con cual quedarte para el proyecto

Pero y si queremos volver en el pasado usar otra version de nuestro proyecto esto se logra con (git reset [Numero de la base de datos]) habiendo 2 variaciones de esto un reset brusco que se denomina (git reset [Numero de la base de datos] --hard) o un reset simple (git reset [Numero de la base de datos] --soft) que ese numero simplemente te sale con un (git log) mostrando los commits y un numero extenso
Automaticamente regresando al pasado pero debemos tener cuidado con este comando ya que puede ser borrado gran parte de tu proyecto si no tienes idea de lo que haces

Un atajo util que se puede usar para poder hacer un "commit" y agregar a la vez es con (git commit -am "[MENSAJE]") ahorrandote mucho tiempo

Aun seguiremos viendo git y multiples comandos mas pero ya relacionado al mundo de Github

GitHub es una usado para alojar proyectos utilizando el sistema de control de versiones Git se utiliza Generalmente para la creacion de codigo fuente desde el año 2010 siendo la mas popular y usada por miles de usuarios en todo el mundo 

Para poder uni nuestro repositorio local a un servidor remoto 

Debemos hacerlo de la siguiente manera (git remote [Usar la url producido desde github]) y a la vez verificando a que servidor remoto se unio esto verificandolo con git (git remote -v) dando 2 resultados como un "fetch" o "push"

Posteriormente dejandote enviar a este nuevo repositorio remoto agregado desde github con un "Push" siendo los pasos

Antes de eso debemos configurar el usuario y el correo de la siguiente forma para no crear conflictos
git config --global user.name "Tu"
git config --global user.email me@example.com

y ahora haciendo un resumen de como enviar tu repositorio a un repositorio remoto desde github

git init (Inicializando init en tu home)
git add . (Para poder agregar todo los documentos)
git commit -m "Este es un commit" (Agregando el comentario)
git remote add origin https://github.com/holasoyunaurl (Especificando la ruta remota de tu repositorio en la nube)
git push origin master

y solo con eso acabas de subir el proyecto pero eso no es todo ya que en las opciones que te puede dar github hay 2 opciones las cuales puedes usar (ssh y https)
y la forma mas segura es usar ssh (SECURITY SHELL) para que tus repositorios esten a salvo pero para esto debemos crear una llave publica y privada 

en la home de la terminal vamos a usar el comando (ssh keygen) para generar la llave (id_rsa) viniendo a ser privada y que jamas deberias compartir y (id_rsa.pub) que es lo que usaremos dandole click a settings seleccionando ssh keygen y copiando la llave con (cat id_rsa.pub) para poder previasualizar y posteriormente copiar agregandole un nombre descriptivo y asi mismo poder usar ssh para los links remotos de nuestros repositorios 

Haciendo mencion a git habiendo un comando que muestra las ramas de una manera muy ordenada y eficiente este es (git log --all -graph-decorate --oneline) 

Tags de Github

Entre las multiples cosas los tags son importantes para mencionar versiones dentro de versiones como si tuvieras un proyecto que estas modificando el logo y modificas el logo hasta llegar a la version final agregando tags de el mismo pero visualizado para usuarios de github

Este se agrega de la siguiente forma

git tag -a [nombre del tag] -m "mensaje" (hash) /// que hash vendria a ser como el numero de la base de datos mencionada anteriormente 













Un pull request es usado en un ambiente de trabajo siendo verificado (DevOps) creando una rama especifica para previasualizar con otra rama aparentando ser el MASTER

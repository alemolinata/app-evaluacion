app-evaluacion
==============

ESTRUCTURA DE ARCHIVOS
( + = folder  )
( - = archivo )

+ proyecto

	+ sass (Nada de esto se sube a internet, son sólo archivos de proceso)
		+ inuit.css (Éste folder no se toca, es una librería que normaliza y tiene algunas variables y mixins útiles)
		+ ui (Aquí es donde van todos los archivos SASS con todos los estilos de la página web)
			- evaluation, flexbox, fonts, forms, general, etc... 
		- _vars.scss (Variables SASS que se usan a través del proyecto)
		- style.scss (ÉSTE es el archivo que se compila, aquí se deben importar todos los archivos scss que se quieran incluir al proyecto)
		- watch (si se usa compass, este archivo ya no es necesario, si no, es este el que se necesita correr para compilar los archivos scss)

	+ www (Aquí están ya los HTML's, imágenes, CSS's compilados, etc)
		+ css (Aquí van los CSS's minificados)
		+ fonts (las tipografías que uso son de Google Fonts, así que sólo está la icon-font para los íconos)
		+ images 
		+ js (Aquí yo no he puesto nada porque imagino que usan algún framework de JS y no quiero que haya conflicto)
		- todos los HTML's

	- config.rb (Este determina todas las rutas y configuraciones para que Compass compile los archivos SASS)



PARA USAR COMPASS:
1.  Instalar Compass en su computadora. 
	En Mac:
		$ gem update --system
		$ gem install compass

2a. Crear proyecto en Compass (no es necesario en este caso)
		$ compass create <myproject>
2b. Instalar Compass a un proyecto existente (No sé si sea necesario en el caso de este proyecto, porque yo lo instalé ya)
		$ cd <myproject>
		$ compass install

3.  Compilar archivos SASS y SCSS
		$ cd <myproject>
		$ compass watch


CONFIGURACIONES DE COMPASS
Para configurar las rutas y cómo se compilan los CSS's, se deben hacer cambios al archivo config.rb
Creo que config.rb debe ir en el root del proyecto, y es ahí donde se debe correr el comando compass watch para generar los archivos.

Puedes mover de lugar la carpeta de SASS, la de WWW, llamarla de otra manera, y no hay ningún problema.
Sólo cambia las rutas de los directorios (sass, css, images, js, fonts) de forma relativa a config.rb y todo debe funcionar sin ningún problema.


NOTA IMPORTANTE:
Antes de usar Compass, al minificar yo renombraba el archivo a style.min.css, pero Compass no tiene la manera de hacerlo, por lo que ahora el import en el HTML del CSS debe importar style.css en vez de style.min.css






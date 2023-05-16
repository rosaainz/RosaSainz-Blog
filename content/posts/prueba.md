---
title: "Crea un blog con Hugo y Github Pages"
description: "¡Hey! Espero te ayude esta guia para crear un blog con Hugo y Github Pages ◡̈"
draft: false
---

# Tutorial para crear tu blog con Hugo y Github Pages!

Ya sea que quieras crear un blog personal o para darle visibilidad a tu marca,  **Hugo** es una gran opción ya que es fácil de configurar, sus temas son fácilmente exportables y algunos ya cuentan con integración a Google Analytics. Pero primero que nada... ¿Qué es Hugo? 


## ¿Qué es Hugo?

Hugo es un generador de sitios web estáticos, con esto me refiero a que no tendras BackEnd parael manejo de base de datos, esta escrito en Go, que es un lenguaje de programación compilado y concurrente, esto quiere decir que compila directamente a lenguaje máquina con la capacidad de ejecutar múltiples tareas simultáneamente, lo que puede resultar en programas más eficientes y escalables. Actualmente es utilizado por varias empresas y organizaciones, como Google, Uber, Dropbox, Docker, entre otras, ojo aquí. 

## Instalar Hugo
### macOS
Para instalar Hugo en Mac usaremos Brew, que es un gestor de paquetes con el cual podras instalar, actualizar y gestionar una gran variedad de software y herramientas en tu sistema operativo, de forma rápida y sencilla, desde la línea de comandos.

💡 Brew se basa en la filosofía de software libre y código abierto, y está escrito en Ruby.

🍺 Aquí te dejo el enlace en donde estan los pasos para instalar Brew: https://brew.sh/index_es

Ahora si... para instalar Hugo con brew solo ejecuta el siguiente comando en tu terminal:

```shell
	brew install hugo
```

### Linux
Para instalar Hugo en Linux usaremos Snap, que es un sistema de paquetes universal para distribuciones de Linux.
La instalación de snap depende de la distribución de Linux que estés utilizando (Ubuntu, Fedora, Debian, etc). 
Aquí te dejo algunos ejemplos: 

#### Ubuntu
```shell
	sudo apt install snapd
```

#### Fedora
```shell
	sudo dnf install snapd	
```
Una vez que tengas snap podemos correr el siguiente comando para instalar Hugo:

```shell
	snap install hugo	
```

#### Windows
Para instalar Hugo en Windows, se puede instalar utilizando los gestores de paquetes Chocolatey o Scoop. Aquí sus páginas: https://chocolatey.org/install y https://scoop.sh/
Ya que tengas alguno de estos gestores puedes correr el comando que corresponda al gestor para instalar Hugo: 
```shell
	choco install hugo-extended -confirm	
```

```shell
	scoop install hugo-extended	
```

Para verificar que Hugo se ha instalado correctamente, ejecuta el siguiente comando: 
```shell
	hugo version
```
Te debe mostrar información de la verión instalada de Hugo:

![Comando para validar que se instalo Hugo](/images/hugoVersion.jpg)


¡Listo! ya tienes Hugo instalado, ahora podemos empezar a crear nuestro Blog 🙌🏼

## Crear proyecto con Hugo

Bien, ya tenemos Hugo en nuestra maquina, ahora crearemos nuestro blog, lo llamaremos "Blog" jeje. 
Para crearlo solo necesitas correr el siguiente comando, es importante que en la terminal te posiciones en el directorio en donde quieres que se cree la carpeta de tu proyecto. 
```shell
	hugo new site Blog	
```
Se va a crear una carpeta con el nombre Blog, la cual contendra todas las carpetas y archivos necesarios para tu sitio. 

Aquí un ejemplo: 
<div class="text-center">
    <img src="/images/crearProyecto.png" alt="Terminal con los comandos necesarios para crear proyecto Hugo y validar">
</div>

{{< figure src="/images/crearProyecto.png" alt="Terminal con los comandos necesarios para crear proyecto Hugo y validar" title="crearProyecto" width="400" class="clase-css" >}}

<p align="center">
  <img src="/images/crearProyecto.png" alt="Terminal con los comandos necesarios para crear proyecto Hugo y validar">
</p>

![Terminal con los comandos necesarios para crear proyecto Hugo y validar](/images/crearProyecto.png)

Es importante entender que contienen estas carpetas y archivos, ya que eso ayudara a que se más fácil personalizar nuestro blog, algunas de estas carpetas y archivos son: 

* archetypes/: contiene plantillas de contenido predeterminadas para diferentes tipos de contenido. Los arquetipos son especialmente útiles si tu sitio tiene múltiples formatos de contenido. Con los arquetipos de Hugo, puedes crear una plantilla para cada tipo de contenido de tu sitio.
* content/: contiene el contenido de tu sitio web. Cada archivo dentro de esta carpeta representa una página en tu sitio.
* data/: contiene datos estructurados en formatos como CSV, JSON o YAML.
* layouts/: contiene plantillas de diseño en formato HTML y que determinan cómo se mostrará tu contenido en el sitio web.
* static/:  contiene todos los archivos estáticos, como imágenes, CSS y JavaScript, que se utilizarán en el sitio. Hugo copiará todo lo que se encuentre en esta carpeta en la raíz del sitio web cuando se compile el sitio.
* themes/: contiene los temas que se utilizarán en el sitio. Los temas contienen archivos de diseño, hojas de estilo y otros recursos que definen la apariencia y la funcionalidad del sitio.
* config.toml: Este archivo de configuración contiene la configuración global del sitio, como el título del sitio, la descripción, el lenguaje y otros detalles.

Una vez dentro de nuestra carpeta Blog, inicializamos git, esto para poder subirlo a GitHub Pages más adelante. Ejecuta el siguiente comando: 

 ```shell
	git init
```

¡Felicidades! Ya tienes la estructura de tu blog, ahora solo falta agregar el tema de tu agrado, es seria el FrontEnd de tu blog, aquí te dejo todos los temas disponibles https://themes.gohugo.io/ 

## Agregar Tema

La mayoría de los temas de Hugo estan disponibles en un repositorio de GitHub. Para utilizar un tema en un sitio web generado con Hugo, se puede agregar la dirección web del repositorio del tema al archivo de configuración "config.toml" del sitio pero antes es necesario agregarlo a nuestra carpeta del proyecto. 

Para agregar el repositorio del tema que elegimos al repositorio de nuestro blog, usaremos el siguiente comando: 

 ```shell
	git submodule add https://github.com/budparr/gohugo-theme-ananke.git themes/ananke
```
En este ejemplo estoy agregando el tema ananke. Se agrega como submódulo es un repositorio Git incrustado dentro de otro repositorio Git.
Una vez agregado el submódulo, se deben confirmar los cambios en el repositorio principal, utilizando los comandos "git add" y "git commit". Luego, para descargar el código del submódulo, se utiliza el comando "git submodule update".

Ahora si podemos agregarlo en la condiguración "config.toml" del sitio (línea 4):
<div class="text-center">
    <img src="/images/temaConf.png" alt="Agregar tema a la configuración">
</div>

☝🏼 Recomendación: Ve subiendo tus cambios a git, ejemplo: 
```shell
	git add .
	git commit -m "Agregando tema en la configuracion"
```

Si ya llegaste hasta acá ¡Felicidades! ya solo falta levantar nuestro server y empezar a bloguear 🤙🏼

## Levantar Server

Esta parte es muy sencilla pero antes que nada... ¿Cómo que levantar un servidor? ¿A qué se refiere eso? explicare muy breve este tema ya que hay mucho de que hablar y me gustaría escribir otro post para eso. 

En términos simples, ejecutar el archivo ejecutable de un software o aplicación en una computadora o en una red de computadoras, que se encarga de servir las páginas web generadas en el sitio y responder a las solicitudes de los usuarios que acceden al sitio a través de su navegador web. Al levantar un servidor de Hugo, se puede visualizar el sitio web de manera local y realizar pruebas en el mismo antes de publicarlo en un servidor web público

Hugo viene con un servidor web integrado para fines de desarrollo, lo que significa que no es necesario instalar un servidor web como Apache para ver tu sitio localmente.

Para levantar el sitio web de Hugo ejecuta el siguiente comando: 
```shell
	hugo server 
```

Hugo construye sus sitios web en el puerto 1313. Esto significa que, cuando se ejecuta el comando hugo server para levantar un servidor local y previsualizar el sitio web generado por Hugo, este se ejecuta en el puerto 1313. Para visualizar el sitio de nuestro blog de ejemplo solo hay que acceder a http://localhost:1313/ como se muestra en la terminal al momento de ejecutar el comando: 

<div class="text-center">
    <img src="/images/hugoServer.png" alt="Comando hugo server">
</div>

Así es como se ve nuestro blog hasta el momento: 

<div class="text-center">
    <img src="/images/sitio.png" alt="Sitio web">
</div>

## Crear primer post













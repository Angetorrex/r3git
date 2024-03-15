INSTALACIÓN DE DOCKER
Docker es una plataforma que permite crear, implementar, ejecutar, actualizar y gestionar contenedores. Estos contenedores son unidades estandarizadas y ejecutables que integran el código fuente de la aplicación con las bibliotecas y dependencias del sistema operativo requeridas para su funcionamiento en cualquier entorno. En este proyecto, veremos cómo podemos instalar Docker de manera fácil y sencilla en Linux (Ubuntu). 

Requisitos previos
    • Acceso a la terminal de tu sistema operativo.

Instalación
    1. Para empezar a instalar Docker, debemos de tener nuestro inidice de paquetes actualizado, para hacer eso ejecutamos el siguiente comando: 
“sudo apt update”
    2. Instalaremos los paquetes necesarios para permitir que apt utilice un repositorio sobre HTTPS, para eso, ejecutemos el siguiente comando: 
“sudo apt install apt-transport-https ca-certificates curl software-properties-common”.
    3. Agregaremos después, la clave GPG oficial de Docker ejecutando el siguiente comando: 
“curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -”
    4. Después vamos a añadir el repositorio de Docker a las fuentes de APT utilizando el siguiente comando: 
“sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable"”
    5. Para asegurarnos, debemos de actualizar el indice de paquetes otra vez después de agregar el repositorio de Docker. Para esto, ejecute el siguiente comando: 
“sudo apt update”
6. Tenemos que ver que lo  estemos instalando desde el repositorio de Docker en lugar del repositorio predeterminado de Ubuntu, para hacer esto, ejecute el siguiente comando:
“apt-cache policy docker-ce”
    6. Para finalizar, instalaremos Docker con el siguiente comando:
“sudo apt install docker-ce”
7. Para verificar que esta correctamente intalado, utilice el siguiente comando:
“sudo docker run hello-world”

Ejecutando las pruebas
Una de las pruebas que podemos hacer es la de integración, eso se hace ejecutando los siguientes comandos que se proporcionaran, estos comandos serviran para ejecutar las pruebas de integración dentro de un contenedor de Docker proporcionando un entorno de prueba aislado y reproducible.
* “docker run --rm -v $(pwd):/app -w /app node”
* “sudo apt install npm”
* “npm run test:integration”

Pruebas de estilo de codificación.
Para ejecutar estas pruebas vamos a usar ESLint, para esto, necesitaremos ejecutar los siguientes comandos los cual nos ayudaran a ver que las pruebas se realicen en un entorno controlado y reproducible.
* “docker run --rm -v $(pwd):/app -w /app node”
* “npm install”
* “npm run lint”
Despliegue
Para implementar el proyecto en un sistema en vivo utilizando Docker vamos a crear un contenedor, para esto vamos a ejecutar los siguientes comandos:
1. primero tenemos que descargar la imagen, en este ejemplo usaremos Apache HTTP Server (httpd). Para hacer esto, ejecuta el siguiente comando:
“docker pull httpd”
2. creamos un contenedor a partir de la imagen (mi contenedor se llamara “mi-apache”). Para hacer esto, ejecuta el siguiente comando.
“docker create --name mi-apache httpd”
3. una vez ta creado, vamos a iniciar el contenedor con el siguiente comando:
“docker start mi-apache”

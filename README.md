# Entorno de desarrollo Laravel y React 

#### Orientado a practicas de Alumnos FSD con stacks React/Laravel con bases de datos mysql

Motivacion, promover el uso profesional de Docker entre los alumnos para los entornos de desarrollo, evitar la instalacion de stacks no nativos en diferentes sistemas operativos o el uso de installers como xampp, y por tanto lograr homogeneidad de versiones y librerias.

## Config
Toda la configuración del entorno se encuentra en /deploy/develop/docker-compose.yaml


## El .gitignore
se ignoran los directorios /data que es donde las base de datos persistirá los cambios y 
el directorio /source se ignora por defecto, ya que se ha pensado que en el directorio source puedas deployar tu codigo y que cada proyecto tenga su repositorio propio, 
ya sea un repositorio existente o un proyecto de cero podras volcarlo en carpetas dentro del directorio source, por defecto el docker-compose esta configurado para las carpetas

    * source/laravel
    * source/react

si usas otras carpetas debes modificar el archivo /deploy/develop/docker-compose.yaml

## Como empezar
Usar los siguientes scripts con fines de iniciar el proyecto, instalar dependencias, limpiar el entorno etc.

### Scripts

#### cleanup
Para limpiar el entorno, eliminar contenedores y residuos. Es conveniente hacerlo cada vez antes de empezar o para evitar problemas.

> ./bin/cleanup 

#### start
Para inicializar los servicios definidos en /deploy/develop/docker-compose.yaml que es donde se encuentra la configuracion de todo el entorno.

> ./bin/start

#### utils
Para acceder a un contenedor de operaciones, usamos estos contenedores para inicializar un proyecto, react o laravel, instalar dependencias, hacer los dumps, migraciones o cualquier operacion propia del framework.


 * ejemplos
    * ./bin/utils laravel
    * ./bin/utils react
    * ./bin/utils mysql

si definimos mas servicios o cambiamos sus nombres en /deploy/develop/docker-compose.yaml podriamos acceder a un contenedor auxiliar de los mismos con este script.

> ./bin/utils [nombre del servicio]


#### logs
Reconectar con los logs de salida de los servicios

> ./bin/logs

## Puertos por defecto

* React 3000
* Laravel 8000
* PHPMyadmin 8080

aunque puedes modificarlos en /deploy/develop/docker-compose.yaml 
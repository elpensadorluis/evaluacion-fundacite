# Prueba Referente al Nuevo Ingreso de la Unidad de Desarrollo y Mantenimiento de Software de FUNDACITE Mérida

## Instrucciones

### Evaluación de desarrollo de algoritmo

El uso de programación Bash en el shell de Unix es una herramienta primordial para el desarrollo de las actividades del departamento, compatible con POSIX y el intérprete de comandos por defecto en la mayoría de las distribuciones GNU/Linux, además de macOS.

La sintaxis de **bash** es simplemente instrucciones por lotes en consola, donde se utiliza los comandos de linea de la consola de linux junto con una lógica básica de programación para cumplir ciertas taréas repetitivas.

#### Comandos Básico de Bash

El archivo de instrucciones por lotes deberá incluir por buenas práctica la siguiente características:

Deberá comenzar con un encabezado el cual identifica que las siguientes lineas de instrucciones serán basada en las reglas del bash:

 ```bash
 #!/bin/bash
 ```

* El comando `echo` permite imprimir por consola

```bash
echo "Hola Mundo"
```

Lo bueno que tiene trabajar con **bash** es que permite interactuar con comandos nativos de la consola shell de linux, como por ejemplo:

 ```bash
 touch prueba.html 
 ```

Donde el comando `touch` nos permite crear un archivo vacío con el nombre "prueba.html"

 ```bash
 mkdir app
 ```
O el comando `mkdir` para crear una carpeta llamada app en el directorio actual

También podríamos como ejemplo, desear saber en que carpeta estamos y subir un nivel con solo instrucciones para luego mostrar el destino final por consola

 ```bash
 #!/bin/bash
 pwd
 cd ..
 pwd
 
 ```

Una de las virtudes de trabajar con archivos de comando por lotes sh, es poder enviar parámetros a través de la instrucción de ejecución del archivo y manipular cada instrucción como una variable utilizable dentro de las líneas de comando.

Un Ejemplo es el siguiente, se desea hacer un script bash que me permita ingresar el nombre del proyecto y el algoritmo me crea una carpeta en el destino actual y dentro un esquema de trabajo con el archivos index.html y es por ello que creamos el siguiente script llamado "proyecto.sh":

```bash
#!/bin/bash
echo "Creando Esquema de Proyecto, $1"
mkdir $1
cd $1
touch index.html
cd ..
echo "Esquema Terminado..."
```

Siguiendo el ejemplo, deseamos llamar el primer proyecto "poa1", para ello ejecutamos el archivo por lotes que creamos anteriormente y le agregamos el nombre "poa1" como parámetro y dentro del código será invocado con la estructura $1 donde el número indica la posición del parámetro, y si, podemos enviar más de un parámetro y manipularlos según el orden de escritura, todos separados por espacios, quedando la instrucción de la siguiente manera:

 ```shell
 $ sh proyecto.sh poa1
 
 ```
Donde sh es la instrucción en unix para ejecutar un archivo por lotes, "proyecto.sh" es el nombre del archivo por lotes creado anteriormente y "**poa1**" es el parámetro a procesar. El resultado es el siguiente:

 ```shell
poa1/
└── index.html

 ```
Una carpeta llamada "**poa1**" y dentro de ella tres archivos vacíos con las extensiones deseadas.

## Evaluación

Se desea que desarrolle un archivo por lotes llamado "**proyectos-mvc.sh**" que cree la siguiente estructura de trabajo:

 ```shell
app-asistencia/
├── app/
│   ├── controllers/
│   ├── models/
│   ├── routes/
│   └── views/
├── config/
│   ├── config.js
│   ├── env
│   └── express.js
├── package.json
├── public/
│   ├── app.js
│   ├── config/
│   ├── controllers/
│   ├── css/
│   ├── directives/
│   ├── filters/
│   ├── img/
│   ├── services/
│   └── views/
└── server.js
 ```

el nombre del proyecto será "app-asistencia" y deberá ser pasado como parámetro al momento de ejecutar el archivo por lotes de la siguiente manera:

 ```shell
 $ sh proyectos-mvc.sh app-asistencia
 ```

 y con el mismo archivo por lotes "proyectos-mvc.sh" se creará un segundo proyecto llamado "**app-rrhh**", y al ejecutar el siguiente comando deberá ser capaz de generar una estructura para ese proyecto:

  ```shell
  $ sh proyectos-mvc.sh app-rrhh
  ```
  Y como resultado obtener:

   ```shell
   app-rrhh/
├── app
│   ├── controllers
│   ├── models
│   ├── routes
│   └── views
├── config
│   ├── config.js
│   ├── env
│   └── express.js
├── package.json
├── public
│   ├── app.js
│   ├── config
│   ├── controllers
│   ├── css
│   ├── directives
│   ├── filters
│   ├── img
│   ├── services
│   └── views
└── server.js
   
   ```
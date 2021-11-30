## Creación de proyecto

    mvn archetype:generate -DgroupId=com.mycompany.app -DartifactId=my-app \
        -DarchetypeArtifactId=maven-archetype-quickstart -DarchetypeVersion=1.0 -DinteractiveMode=false
        
   >>>>
   
   + groupId: corresponde a package com.mycompany.app de cada clase.
   >>>>

>>>>
+ artifactId: corresponde al nombre de componente o proyecto java desarrollado
>>>>

El comando anterior genera una estructura de directorios como la mostrada a continuación:

    tree

    .
    ├── pom.xml
    └──src
        ├── main
        │   └── java
        │       └── com
        │           └── mycompany
        │               └── app
        │                   └── App.java
        └── test
            └── java
                └── com
                    └── mycompany
                        └── app
                            └── AppTest.java
                            
El archivo pom.xml tiene un contenido similar a este:

    <project>
      <modelVersion>4.0.0</modelVersion>
      <groupId>com.mycompany.app</groupId>
      <artifactId>myapp</artifactId>
      <packaging>jar</packaging>
      <version>1.0.0</version>
    </project>
    
La etiqueta modelVersion hace referencia a la propia estructura del fichero Maven (actualmente es la 4).

La etiqueta packaging indica la forma de empaquetado. Por defecto es .jar.

## Objetivos o metas (goals)

Maven ya tiene predefinidas una serie de metas (goals, en terminología de maven). Son las siguientes:

Las metas que forman parte del ciclo de vida principal del proyecto Maven son:

+ compile: Genera los ficheros .class compilando los fuentes .java
+ test: Ejecuta los test automáticos de JUnit existentes, abortando el proceso si alguno de ellos falla.
+ package: Genera el fichero .jar con los .class compilados
+ install: Copia el fichero .jar a un directorio de nuestro ordenador donde maven deja todos los .jar. De esta forma esos .jar pueden utilizarse en otros proyectos maven en el               mismo ordenador.
+ deploy: Copia el fichero .jar a un servidor remoto, poniéndolo disponible para cualquier proyecto maven con acceso a ese servidor remoto.

Cuando se ejecuta cualquiera de los comandos maven, por ejemplo, si ejecutamos mvn install, maven irá verificando todas las fases del ciclo de vida desde la primera hasta la del comando, ejecutando solo aquellas que no se hayan ejecutado previamente.

También existen algunas objetivos o metas que están fuera del ciclo de vida que pueden ser llamadas, pero Maven asume que estas metas no son parte del ciclo de vida por defecto (no tienen que ser siempre realizadas). 

Estas metas son:

+ clean: Elimina todos los .class y .jar generados. Después de este comando se puede comenzar un compilado desde cero.
+ site: Genera un sitio web con la información de nuestro proyecto.

Por ejemplo, para compilar ejecutaremos:

    mvn  compile
    
y para generar un archivo .jar

    mvn  package
    
 Todos los archivos generados durante la construcción se guardan en la carpeta target.

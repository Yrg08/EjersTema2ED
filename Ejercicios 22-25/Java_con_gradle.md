# Java con Gradle


Gradle es una herramienta para la gestión y construcción de proyectos Java.

De los sistemas de construcción para Java, Gradle es el último en aparecer: el primero fue _ant_ y el segundo _maven_. 

Gradle construye sobre los conceptos de Apache Ant y Apache Maven e introduce un lenguaje especifico del dominio (DSL) basado en Groovy en vez de la forma XML utilizada por Apache Maven y Ant para declarar la configuración de proyecto.
Esta característica hace que el buildfile de gradle sea más conciso y legible.

Al igual que Maven, Gradle trabaja con uno o varios repositorios para usar en red. También al igual que Maven, soporta plugins.

Gradle tiene las siguientes ventajas sobre ant y maven:

- es más rápido que maven y ant para grandes proyectos.
- es organizado como maven sin ser rígido y flexible como ant sin tener que especificar cada tarea.
- tiene soporte para otros lenguajes como C y C++.
- por defecto agrega la dependencia para tests unitarios de JUnit.

Gradle tiene las siguientes desventajas sobre ant y maven:

- tiene peor integración con los IDEs.
- para pequeños proyectos pueden ser más adecuados otros sistemas de construcción.


## Creación de proyecto

```
mkdir  nombre-proyecto  &&  cd  nombre-proyecto
gradle init  --type   java-application
```

Otros tipos de proyectos son: 
- basic
- pom
- groovy-library
- scala-library
- java-library

El comando anterior genera una estructura de directorios como la mostrada a continuación:

```
tree

.
├── build.gradle
├── gradle
│   └── wrapper
│       ├── gradle-wrapper.jar
│       └── gradle-wrapper.properties
├── gradlew
├── gradlew.bat
├── settings.gradle
└── src
    ├── main
    │   └── java
    │       └── App.java
    └── test
        └── java
            └── AppTest.java

```

Se generan 2 _wrappers_ :

- gradlew     (para entornos Linux)
- gradlew.bat (para entornos Windows)

Es aconsejable utilizar estos _wrappers_ o _envoltorios_ puesto que hacen más portable la construcción en equipos con versiones de gradle distintas a las utilizadas por nosotros. No obstante, si no necesitamos construir en otros equipos distintos al nuestro puede utilizarse `gradle` directamente. Para ir adquiriendo buenos hábitos, en el ejemplo mostrado más abajo, se hara uso del wrapper `./gradlew`.

El archivo de construcción `build.gradle` tiene un contenido similar a este:

```
apply plugin: 'java'
apply plugin: 'application'

repositories {
    jcenter()  
}

dependencies {
    compile 'com.google.guava:guava:23.0'  
    testCompile 'junit:junit:4.12'         
}

jar {
    manifest {
       attributes ('Main-Class': 'Main')
    }
}

mainClassName = 'Main'
```


## Tareas (tasks)

Gradle ya tiene predefinidas una serie de tareas (__tasks__, en terminología de gradle).

Las tareas predefinidas pueden verse con el comando:

__``` ./gradlew  tasks ```__

```
:tasks

------------------------------------------------------------
All tasks runnable from root project
------------------------------------------------------------

Build tasks
-----------
assemble - Assembles the outputs of this project.
build - Assembles and tests this project.
buildDependents - Assembles and tests this project and all projects that depend on it.
buildNeeded - Assembles and tests this project and all projects it depends on.
classes - Assembles main classes.
clean - Deletes the build directory.
jar - Assembles a jar archive containing the main classes.
testClasses - Assembles test classes.

Build Setup tasks
-----------------
init - Initializes a new Gradle build. [incubating]
wrapper - Generates Gradle wrapper files. [incubating]

Documentation tasks
-------------------
javadoc - Generates Javadoc API documentation for the main source code.

Help tasks
----------
buildEnvironment - Displays all buildscript dependencies declared in root project 'miapp'.
components - Displays the components produced by root project 'miapp'. [incubating]
dependencies - Displays all dependencies declared in root project 'miapp'.
dependencyInsight - Displays the insight into a specific dependency in root project 'miapp'.
help - Displays a help message.
model - Displays the configuration model of root project 'miapp'. [incubating]
projects - Displays the sub-projects of root project 'miapp'.
properties - Displays the properties of root project 'miapp'.
tasks - Displays the tasks runnable from root project 'miapp'.

Verification tasks
------------------
check - Runs all checks.
test - Runs the unit tests.

.
.
.
```

Como se observa se distinguen 5 tipos de tareas:

- Tareas de construcción, entre otras:
  - `build`
  - `jar`
  - `clean`

- Tareas de configuración, entre otras:
  - `init`
  
- Tarea de documentación:
  - `javadoc`

- Tareas de ayuda, entre otras:
  - `tasks`
  - `help`
  
- Tareas de verificación, entre otras:
  - `test`

El significado de cada tarea resulta bastante evidente debido a su semejanza respecto a otros sistemas de construcción.

Por ejemplo, para compilar, construir y realizar tests de unidad ejecutaremos:

```
./gradlew  build
```

Todos los archivos generados durante la construcción se guardan en la carpeta `build`. En la subcarpeta `build/libs` se guarda el archivo `.jar`.

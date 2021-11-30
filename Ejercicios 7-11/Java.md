+ Compilamos

javac Hola.java

+ Interpretamos y ejecutamos

java Hola

## Script ejecutable

Realmente no es un script, sino bytecode empaquetado en JAR e interpretado por la JVM (Java Virtual Machine).

+ Empaquetamos
jar  cvfe  hola.jar  Hola  Hola.class 

>>> NOTA:

Las opciones utilizadas en el comando jar son:

c: Create      (Crear archivo jar)
v: Verbose     (Mostrar información)
f: File        (Nombre de archivo jar, en este caso hola.jar)
e: Entry point (Punto de entrada, en este caso la clase Hola)
Los argumentos utilizados son:

hola.jar:    (opción f anterior) Archivo .jar resultante.
Hola:        (opción e anterior) Clase que contiene el método main (es decir el punto de entrada)
Hola.class:  Archivos de bytecode a incluir en hola.jar. Pueden ser varios archivos.
Los argumentos deben seguir el mismo orden que las opciones. En este caso indicamos primero el nombre del archivo .jar y luego la clase que contiene el método main.

>>> NOTA IMPORTANTE: La FORMA HABITUAL de ejecutar un archivo .jar es invocando al intéprete java, es decir la siguiente:

java  -jar   hola.jar
Los pasos 2 y 3 siguientes no es la forma habitual de ejecutar un archivo .jar, pero se indican para mostrar su similitud respecto al método usado para otros lenguajes interpretados.
>>>
+ Damos permiso de ejecución

chmod  +x  hola.jar

+ Ejecutamos

./hola.jar                           

##### El archivo tiene una extensión _.jar_
##### El lenguaje primero se compila a su representación intermedia que luego se interpreta en tiempo de ejecución.

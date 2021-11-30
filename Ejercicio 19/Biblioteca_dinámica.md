# Crear paquete jar con la biblioteca

+ Creamos directorio aritmetica

mkdir  aritmetica

+ Creamos clase aritmetica/Aritmetica.java

>>>> package aritmetica;

public class Aritmetica {

  public static int suma (int sumando1, int sumando2) {
        return (sumando1+sumando2);
  }

  public static int resta  (int minuendo, int sustraendo) {
        return (minuendo-sustraendo);
  }

  public static int multiplicacion (int  numero1, int numero2) {
        return (numero1*numero2);
  }

  public static float division (int dividendo, int divisor) {
        return (dividendo/(float)divisor);
  }

}


Archivo aritmetica/Aritmetica.java
Compilamos
javac  aritmetica/Aritmetica.java
Obtenemos un archivo aritmetica/Aritmetica.class con el bytecode.

Creamos paquete jar
jar  cvf  aritmetica.jar  aritmetica/*.class
Instalamos biblioteca en el sistema
Para instalar dicha biblioteca en el sistema debemos copiar aritmetica.jar al directorio de sistema donde se alojan las librerias de extensiones (p.ej: /usr/lib/jvm/java-8-openjdk-amd64/jre/lib/ext). No es necesario mantener el nombre del archivo.

mv  aritmetica.jar  /usr/lib/jvm/java-8-openjdk-amd64/jre/lib/ext/aritm.jar

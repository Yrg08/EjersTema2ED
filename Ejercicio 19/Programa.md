# Crear programa que usa la biblioteca

* Creamos archivo Main.java

import aritmetica.Aritmetica;

public class Main 

{

    private static final int NUM1 = 5;
    private static final int NUM2 = 2;


    public static void main (String[] args) 
    
    {
      System.out.println ("Dados los números " + NUM1 + " y " + NUM2 );
      System.out.println ("La suma es " + Aritmetica.suma(NUM1, NUM2) );
      System.out.println ("La resta es " + Aritmetica.resta(NUM1, NUM2) );
      System.out.println ("La multiplicación es " + Aritmetica.multiplicacion(NUM1, NUM2) );
      System.out.println ("La división es " + Aritmetica.division(NUM1, NUM2) );
    
    }


}


* Compilamos

javac  Main.java

> Obtenemos un archivo Main.class con el bytecode.

>> Al compilar, se enlaza con las bibliotecas necesarias, buscando éstas en el directorio de bibliotecas del sistema. 
>> En nuestro caso en /usr/lib/jvm/java-8-openjdk-amd64/jre/lib para la biblioteca estándar de Java. 
>> Y en /usr/lib/jvm/java-8-openjdk-amd64/jre/lib/ext para las bibliotecas añadidas.

* Ejecutamos

java  Main

> Al ejecutar, se buscan las bibliotecas necesarias en el directorio de bibliotecas del sistema. 
> En nuestro caso en /usr/lib/jvm/java-8-openjdk-amd64/jre/lib para la biblioteca estándar de Java. 
> Y en /usr/lib/jvm/java-8-openjdk-amd64/jre/lib/ext para las bibliotecas añadidas.

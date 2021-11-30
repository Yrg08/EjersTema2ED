Si ejecutamos ant sin argumentos, se ejecutará la regla por defecto y obtendremos la siguiente salida:

ant

    Buildfile: /home/jose/Proyectos/DAW1-ED-Bibliotecas/java/build.xml

    init:
        [mkdir] Created dir: /home/jose/Proyectos/DAW1-ED-Bibliotecas/java/build/classes
        [mkdir] Created dir: /home/jose/Proyectos/DAW1-ED-Bibliotecas/java/build/jar

    compile:
            [javac] Compiling 2 source files to /home/jose/Proyectos/DAW1-ED-Bibliotecas/java/build/classes

    jar:
        [jar] Building jar: /home/jose/Proyectos/DAW1-ED-Bibliotecas/java/build/jar/programa.jar

    BUILD SUCCESSFUL
    Total time: 2 seconds

    
  Entre otras, hemos declarado también las reglas para los objetivos siguientes:

    help: muestra un mensaje de ayuda
    clean: elimina los archivos resultantes de una construcción anterior
    run: ejecuta el ejecutable, el cual hace uso de la biblioteca
    
Para obtener dichos objetivos escribimos el comando ant seguido del objetivo como argumento.

Por ejemplo, para ver la ayuda escribimos:

    ant  help
    
Por ejemplo, para ejecutar escribimos:

    ant run
    

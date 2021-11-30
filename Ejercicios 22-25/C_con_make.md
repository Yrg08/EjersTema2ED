Si ejecutamos make sin argumentos, se ejecutará la regla por defecto y obtendremos la siguiente salida:

make

    gcc -O  -c  main.c
    gcc -O  -c  -fPIC  aritmetica.c
    gcc -O  -shared  -fPIC  -o  libaritmetica.so  aritmetica.o
    gcc -O  -Wl,-rpath=/usr/local/lib  main.o  libaritmetica.so  -o  programa
    
  Entre otras, hemos declarado también las reglas para los objetivos siguientes:

    help: muestra un mensaje de ayuda
    clean: elimina los archivos resultantes de una construcción anterior
    install: instala el ejecutable y la biblioteca en el sistema
    
Para obtener dichos objetivos escribimos el comando make seguido del objetivo como argumento.

Por ejemplo, para ver la ayuda escribimos:

    make  help
    
Por ejemplo, para instalar escribimos:

    make  install
    
> Nota: instalar archivos en el sistema requiere permisos de administrador. Por lo que la orden anterior suele ejecutarse como:

    sudo  make  install

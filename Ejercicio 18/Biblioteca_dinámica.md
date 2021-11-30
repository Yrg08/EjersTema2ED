# Crear biblioteca dinámica

+ Compilamos a código objeto dinámico

gcc  -c  -fPIC  aritmetica.c

> Se habrá generado un archivo aritmetica.o con código objeto dinámico.

+ Empaquetamos en biblioteca dinámica libaritmetica.so

gcc  -shared  -fPIC  -o  libaritmetica.so  aritmetica.o

+ Instalamos biblioteca en el sistema

> Para instalar dicha biblioteca en el sistema debemos copiar libaritmetica.so a algún directorio de sistema donde se alojan las librerias (p.ej: /lib o /usr/lib)

cp  libaritmetica.so  /lib

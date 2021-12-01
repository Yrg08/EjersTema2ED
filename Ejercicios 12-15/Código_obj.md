## 12. Obtener el código objeto a partir del código fuente de los 3 archivos siguientes: main.c, datos.c, suma.c
### Tras la creacción de estos archivos de código fuente en c.

0. Compilamos:

        gcc -c main.c datos.c suma.c
        
> Nota: En mi caso tuve que instalar el paquete gcc-9 de deb para que funcionara.

> Hecho esto, cambié el comando por:
> 
>  gcc -9 -c main.c datos.c suma.c


1. Deberíamos obtener lo siguiente:

        _main.o_   _datos.o_   _suma.o_

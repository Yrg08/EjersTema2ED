# 12. Obtener el código objeto a partir del código fuente de los 3 archivos siguientes: main.c, datos.c, suma.c

## Creación archivos

        //-------------
        // datos.c
        //-------------
        
        char *mensaje="Hola a todos y todas";
        int num1 = 8;
        int num2 = 10;
        
        
        //-------------
        // suma.c
        //-------------
        
        int suma (int a, int b) 
        {
                return a + b;
        }
        
        
        //-------------
        // main.c
        //-------------
        
        #include <stdio.h>
        
        int suma (int a, int b);
        extern char *mensaje;
        extern int num1, num2;
        
        int main()
        {
                printf("%s\n", mensaje);
                printf("%d\n", suma (num1, num2) );
                return 0;
        }

### Tras la creación de estos archivos de código fuente en c.

A. Compilamos:

        gcc -c main.c datos.c suma.c
        
> Nota: En mi caso tuve que instalar el paquete gcc-9 de deb para que funcionara.

> Hecho esto, cambié el comando por:
> 
>  gcc -9 -c main.c datos.c suma.c


B. Deberíamos obtener lo siguiente:

        _main.o_   _datos.o_   _suma.o_

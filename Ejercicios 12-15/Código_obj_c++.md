# 14. Obtener el código objeto a partir del código fuente de los 3 archivos siguientes: main.cpp, datos.cpp, suma.cpp

## Creación archivos

//-------------
// datos.cpp
//-------------

# include <string>
std::string mensaje = "Hola a todos y todas";
int num1 = 8;
int num2 = 10;
  

//-------------
// suma.cpp
//-------------
  
int suma (int a, int b) 
{
  return a + b;
}
  
  
//-------------
// main.cpp
//-------------
  
#include <iostream>
using namespace std;
int suma (int a, int b);
extern string mensaje;
extern int num1, num2;
int main()
{
  cout << mensaje << endl;
  cout << suma (num1, num2) << endl;
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

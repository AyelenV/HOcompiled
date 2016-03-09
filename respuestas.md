EJERCICIO 1

make processing = gcc -E calculator.c -o calculator.pp_c
corre el gcc hasta la instancia de pre-proceso del archivo calculator.c y se detiene.  Crea archivo calculator.pp_c 
 
Make assembler = gcc -masm=intel -S calculator.c -o calculator.asm  
Corre el gcc hasta la primera instancia de compilación. Crea el archivo calculator.asm

Make object = gcc -c calculator.c -o calculator.o
Corre gcc hasta la segunda instancia de compilación. Crea el archivo objeto calculator.o

make executable = gcc calculator.o -o calculator.e
Corre gcc para hacer el linqueo (busca las funciones que no estan definidas en calculator.o e indice en que librería esta y la version de la misma) y crear el archivo ejecutable caclulator.e

EJERCICIO 2

El preprocesador agregó a mi código en C original, el código de las funciones que fueron convocadas en INCLUDE generando un nuevo archivo calculator.pp_c.

EJERCICO 3

Las  funciones identificadas en calculator.asm son "add_numbers (que está definida) y printf. Son las funciones que assembler llama.

EJERCICIO 4
Los simbolos creados en el archivo objeto (calculator.o) son "T" y "U". "T" asignado a las funcione que reconoce como definidas que se pueden ver desde afuera (T de texto). "U" significa que la funcion no esta definida, por lo tanto se tiene que linkear al lugar donde este para terminar el proceso de compilación.
 
EJERCICIO 5

Aparece U printf@@GLIBC_2.2.5, donde si bien printf no esta definida en el sentido statico, aparece en forma concreta donde ir a buscarlo (GLIBC_2.2.5) dentro del procesador. Y además una lista mucho mas grande de funciones necesarias para poder hacer el linkeo.




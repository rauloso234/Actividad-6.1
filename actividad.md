# Actividad-6.1
### Raúl Fernández Turín
## ejercicio 1.
Recibir un número entero por teclado y decir si es positivo.
```sh
#!/bin/bash

echo "introduce un numero"
read num
if [ $num -ge 0 ]
then 
    echo "${num} es positivo"
else
    echo "${num} es negativo"
fi
```
## ejercicio 2.
Recibir un número entero por teclado y decir si es negativo.
```sh
#!/bin/bash

echo "introduce un numero"
read num
if [ 0 -gt $num ]
then 
    echo "${num} es negativo"
else
    echo "${num} es positivo"
fi
```
## ejercicio 3.
Recibir un número entero por teclado y decir si es igual a cero.
```sh
#!/bin/bash

echo "introduce un numero"
read num
if [ 0 -eq $num ]
then 
    echo "${num} es cero"
else
    echo "${num} no es cero"
fi
```
## ejercicio 4.
Recibir un numero entero por teclado y decir si es positivo, negativo o cero.
```sh
#!/bin/bash

echo "introduce un numero"
read num
if [ 0 -eq $num ]
then 
   echo "${num} es cero"
else
 if [ $num -gt 0 ]
    then
    echo "${num} el numero es positivo"
    else
    echo "${num} el numero es negativo"
    fi
fi
```
## ejercicio 5.
Comprobar si el número de parámetros introducido es igual a 3, en el caso de que sea otro número mostrará un mensaje de error por pantalla.
```sh
#!/bin/bash


if [ $# -eq 2 ]
then 
   echo "el numero $1 mas el numero $2 = $(($1+$2))"
else
    echo "Error: mas de dos parametros parametros introducidos"
fi
```
## ejercicio 6.
Recibir dos números por parámetros y lo suma. En caso de que el número de parámetros sea incorrecto mostrará un mensaje de error.
```sh
#!/bin/bash


if [ $# -eq 2 ]
then 
    echo "el numero $1 mas el numero $2 es $(($1+$2))"
else
    echo "se han introducido mas de dos parametros"
fi

```
## ejercicio7.
Recibir 3 parámetros. En el caso de que reciba un número diferente mostrará un mensaje de error. Los dos primeros serán dos números y el tercero será uno de los siguientes símbolos “+” “-“ “x” “/”, dependiendo del tercer parámetro introducido realizara la correspondiente operación. El en caso de que se introduzca un símbolo diferente, presentará un mensaje indicando cuales son las opciones correctas
```sh
#!/bin/bash


if [ $# -eq 3 ]
then 
   case $3 in
    "+")
    echo $(($1+$2))
    ;;
    "-")
    echo $(($1-$2))
    ;;
    "*")
    echo $(($1*$2))
    ;;
    "/")
    echo $(($1/$2))
    ;;
    *)
    echo "Error: introduce "+,-,*,/""
    esac
else
    echo "Error: fallo en la cantidad de parametros introducidos"
fi
```
## ejercicio 8.
Recibir la ruta de un fichero e indicar si existe
```sh
#!/bin/bash


echo "introduce una ruta de un archivo"
read ar

if [[ -e $ar ]]
then 
    echo "el archivo existe"
else
    echo "Error no es un archivo"
fi
```
## ejercicio 9.
Recibir la ruta de un fichero e indicar si es un directorio o un fichero.
```sh
#!/bin/bash


echo "introduce una ruta de un archivo"
read ar

if [[ -f $ar ]]
then 
    echo "el archivo existe"
else
    echo "esto es un directorio"
fi
```
## ejercicio 10.
Recibir la ruta de un fichero e indicar los permisos que tiene (escritura, lectura, ejecución)
```sh 
#!/bin/bash


echo "introduce una ruta de un archivo"
read ar

if [[ -r $ar ]]
then 
    echo "el archivo tiene permiso de lectura"
else
    echo "el archivo no tiene permisos de lectura"
fi

if [[ -w $ar ]]
then 
    echo "el archivo tiene permiso de escritura"
else
    echo "el archivo no tiene permisos de escritura"
fi

if [[ -x $ar ]]
then 
    echo "el archivo tiene permiso de ejecucion"
else
    echo "el archivo no tiene permisos de ejecucion"
fi
```
## ejercicio 11.
Imprimir por pantalla 50 veces la palabra hola.
```sh
#!/bin/bash


num=0

while [ $num != 50 ]
do
echo "Hola"
num=$(($num+1))
done
```
## ejercicio 12.
Leer una palabra por teclado y mostrarla por consola. Debe realizar esta operación 10 veces.
```sh
#!/bin/bash

read -p "Introduce una palabra: " palabra

for i in {1..10}
do
    echo $palabra
done
```
## ejercicio 13.
Recibir un número por parámetro. El programa imprimirá la palabra “hola” el número de veces indicado por parámetro.
```sh
#!/bin/bash

for (( i=0; i<$1; i++ ))
do 
    echo hola
done
```
## ejercicio 14.
Se debe pasar un número n por parámetro. El programa imprimirá los números del 0 al n por pantalla.
```sh
#!/bin/bash

for (( i=0; i<=$1; i++ ))
do 
    echo $i
done
```
## ejercicio 15.
Recibir un número n por parámetro. El programa tendrá que sumar todos los números entre 1 y n. Posteriormente mostrará el resultado de la suma por pantalla
```sh
#!/bin/bash

resultado=0;

for (( i=0; i<=$1; i++ ))
do 
    resultado=$(($resultado+$i))
done

echo $resultado
```
## ejercicio 16.
Recibir dos números por parámetro. El programa deberá hacer que el primer parámetro tome el valor del segundo parámetro y el segundo parámetro tome el valor del primero. Por ejemplo si se introduce el 2 y el 9, en un principio $1 es 1 y $2 es 9. Tras la ejecución del programa $1 valdrá 9 y $2 1.
```sh
#!/bin/bash

num1=$1
num2=$2

echo "El valor de num1 es $num1, el valor de num2 es $num2"

aux=$num1
num1=$num2
num2=$aux

echo "El valor de num1 es $num1, el valor de num2 es $num2"
```
## ejercicio 17.
Programa que lea palabras hasta que se escriba “:q”
```sh
#!/bin/bash

palabra="";

while [ "$palabra" != ":q" ]
do
    read -p "Introduzca una palabra: " palabra
done
```
## ejercicio 18.
Programa que lea palabras y las guarde en un fichero, hasta que se escriba “:q”
```sh 
#!/bin/bash

palabra="";
archivo=fichero18.txt

if [[ -f "$archivo" ]]
then
    rm "$archivo"
fi

while [ "$palabra" != ":q" ]
do
    read -p "Introduzca una palabra: " palabra
    if [[ "$palabra" != ":q" ]]
    then
        echo "$palabra" >> "$archivo"
    fi
done
```
## ejercicio 19.
Programa que lea palabras y las guarde en un fichero de forma ordenada, hasta que se escriba “:q”
```sh
#!/bin/bash

palabra="";
archivo=fichero18.txt

if [[ -f "$archivo" ]]
then
    rm "$archivo"
fi

while [ "$palabra" != ":q" ]
do
    read -p "Introduzca una palabra: " palabra
    if [[ "$palabra" != ":q" ]]
    then
        echo "$palabra" >> "$archivo"
    fi
done
```
## ejercicio 20.
Realiza un programa que solicite un número y compruebe si se encuentre en un archivo llamado números.txt
```sh
#!/bin/bash

archivo="numeros.txt"

read -p "Introduce un número: " num

if  grep -q "$num" "$archivo"
then
    echo "El número $num se encuentra en el $archivo"
else
    echo "El número $num no se encuentra en el $archivo"
fi

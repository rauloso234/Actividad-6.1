# Actividad-6.1
### Raúl Fernández Turín
## ejercicio 1.

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
```sh
#!/bin/bash

read -p "Introduce una palabra: " palabra

for i in {1..10}
do
    echo $palabra
done
```
## ejercicio 13.
```sh
#!/bin/bash

for (( i=0; i<$1; i++ ))
do 
    echo hola
done
```
## ejercicio 14.
```sh
#!/bin/bash

for (( i=0; i<=$1; i++ ))
do 
    echo $i
done
```
## ejercicio 15.
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
```sh
#!/bin/bash

palabra="";

while [ "$palabra" != ":q" ]
do
    read -p "Introduzca una palabra: " palabra
done
```
## ejercicio 18.
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

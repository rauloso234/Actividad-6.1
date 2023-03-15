### Actividad-6.1
# Raúl Fernández Turín
## ejercicio 1.

```sh
#!/bin/bash

echo "introduce un numero"
read num
if [ $num .ge 0 ]
then 
    echo "${num} es positivo"
else
    echo "${num} es negativo"
fi
```
##ejercicio 2.
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
##ejercicio 3.
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
##ejercicio 4.
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
##ejercicio 5.
```sh
#!/bin/bash


if [ $# -eq 2 ]
then 
   echo "el numero $1 mas el numero $2 = $(($1+$2))"
else
    echo "Error: mas de dos parametros parametros introducidos"
fi
```

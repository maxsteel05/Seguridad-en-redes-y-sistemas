# Reto

## Descripción

There's an interesting script in the user's home directory!

The work computer is running SSH. We've been given a script which performs some basic calculations, explore the script and find a flag.

```text
Hostname: saturn.picoctf.net
Username: picoplayer
Password: password
```

## Solución

### Solución 1

- Usando Linux y SSH.
- Primero nos conectamos al servidor utilizando las credenciales proporcionadas por picoCTF.
- Una vez dentro utilizamos `pwd` y `ls` para revisar el directorio.
- Encontramos un archivo llamado `useless`.
- Utilizamos `cat useless` para leer el código del script.
- Dentro del código encontramos el mensaje `Read the manual`.
- Esto nos indica que debemos utilizar `man useless`.
- Al revisar el manual del programa encontramos la flag.

```bash
picoplayer@challenge:~$ pwd
/home/picoplayer

picoplayer@challenge:~$ ls
useless

picoplayer@challenge:~$ cat useless
#!/bin/bash
# Basic mathematical operations via command-line arguments

if [ $# != 3 ]
then
    echo "Read the code first"
else
    if [[ "$1" == "add" ]]
    then
        sum=$(( $2 + $3 ))
        echo "The Sum is: $sum"

    elif [[ "$1" == "sub" ]]
    then
        sub=$(( $2 - $3 ))
        echo "The Substract is: $sub"

    elif [[ "$1" == "div" ]]
    then
        div=$(( $2 / $3 ))
        echo "The quotient is: $div"

    elif [[ "$1" == "mul" ]]
    then
        mul=$(( $2 * $3 ))
        echo "The product is: $mul"

    else
        echo "Read the manual"
    fi
fi
```

Después revisamos el manual:

```bash
picoplayer@challenge:~$ man useless
```

Dentro del manual encontramos:

```text
useless

    useless, -- This is a simple calculator script

SYNOPSIS

    useless, [add sub mul div] number1 number2

DESCRIPTION

    Use the useless macro to make simple calculations like addition,
    subtraction, multiplication and division.

Examples

    ./useless add 1 2
        This will add 1 and 2 and return 3

    ./useless mul 2 3
        This will return 6 as a product of 2 and 3

    ./useless div 6 3
        This will return 2 as a quotient of 6 and 3

    ./useless sub 6 5
        This will return 1 as a remainder of subtraction of 5 from 6

Authors

    This script was designed and developed by Cylab Africa

    picoCTF{us3l3ss_ch4ll3ng3_3xpl0it3d_6200}
```

## Flag

`picoCTF{us3l3ss_ch4ll3ng3_3xpl0it3d_6200}`

## Notas

- `SSH` permite conectarnos de forma remota a otra computadora.
- `pwd` muestra el directorio actual.
- `ls` muestra los archivos disponibles.
- `cat` permite leer el contenido de un archivo.
- `man` muestra el manual de un comando o programa.
- La pista principal estaba dentro del propio script con el mensaje `Read the manual`.
- Al ejecutar `man useless` encontramos directamente la flag.

## Referencias

- [OpenSSH](https://www.openssh.com/)
- [Linux man-pages](https://www.kernel.org/doc/man-pages/)
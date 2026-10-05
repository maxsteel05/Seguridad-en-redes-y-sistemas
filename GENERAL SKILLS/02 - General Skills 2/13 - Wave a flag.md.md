# Reto

## Descripción

Can you invoke help flags for a tool or binary? This program has extraordinarily helpful information...

## Solución

### Solución 1

- Usando Linux.
- Primero descargamos el archivo `warm`.
- Revisamos qué tipo de archivo es.
- Le damos permisos de ejecución con `chmod +x`.
- Al ejecutar el programa nos indica que utilicemos la opción `-h`.
- Finalmente ejecutamos `./warm -h` para mostrar la información de ayuda y obtener la flag.

```bash
maxsteel05-picoctf@webshell:~$ file warm
warm: ELF 64-bit LSB pie executable, x86-64

maxsteel05-picoctf@webshell:~$ chmod +x warm

maxsteel05-picoctf@webshell:~$ ./warm
Hello user! Pass me a -h to learn what I can do!

maxsteel05-picoctf@webshell:~$ ./warm -h
Oh, help? I actually don't do much, but I do have this flag here: picoCTF{b1scu1ts_4nd_gr4vy_ac5832c}
```

## Flag

`picoCTF{b1scu1ts_4nd_gr4vy_ac5832c}`

## Notas

- `chmod +x` agrega permisos de ejecución a un archivo.
- `./warm` ejecuta el programa desde el directorio actual.
- La opción `-h` normalmente se utiliza para mostrar la ayuda de un programa.
- En este reto, la flag se encontraba directamente dentro de la información de ayuda.

## Referencias

- [GNU Coreutils - chmod](https://www.gnu.org/software/coreutils/manual/html_node/chmod-invocation.html)
- [Linux man-pages](https://www.kernel.org/doc/man-pages/)
- 
# Reto

## Descripción

Can you find the flag in the file without running it?

## Solución

### Solución 1

- Usando Linux.
- Primero descargamos el archivo directamente en la terminal utilizando `wget`.
- Después verificamos el tipo de archivo con `file`.
- Finalmente utilizamos `strings` para extraer las cadenas de texto visibles del archivo y `grep` para buscar únicamente la que contiene `picoCTF`.

```bash
maxsteel05-picoctf@webshell:~$ wget https://challenge-files.picoctf.net/c_fickle_tempest/a35dc624cfda8588ed12a4bce57f832dad3b433ba

maxsteel05-picoctf@webshell:~$ file strings
strings: ELF 64-bit LSB pie executable, x86-64, version 1 (SYSV), dynamically linked

maxsteel05-picoctf@webshell:~$ strings strings | grep pico
picoCTF{5tRIng5_1T_60eA8fdA}
```

## Flag

`picoCTF{5tRIng5_1T_60eA8fdA}`

## Notas

- Tuve problemas porque no se encontraba el archivo hasta que utilicé `wget` para descargarlo directamente desde la terminal.
- `wget` permite descargar archivos desde Internet utilizando una URL.
- `file` permite identificar qué tipo de archivo estamos analizando.
- `strings` extrae las cadenas de texto legibles que se encuentran dentro de un archivo binario.
- `grep pico` filtra la salida y muestra solamente las líneas que contienen la palabra `pico`.
- No fue necesario ejecutar el archivo para encontrar la flag.

## Referencias

- [GNU Strings](https://sourceware.org/binutils/docs/binutils/strings.html)
- [GNU grep](https://www.gnu.org/software/grep/manual/grep.html)
- [GNU Wget](https://www.gnu.org/software/wget/)
- 
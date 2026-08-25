# Reto

## Descripción

Can you find the flag in the file? This would be really tedious to look through manually, something tells me there is a better way. The flag is in this file.

## Solución

### Solución 1

- Usando la consola de Linux.
- Descargamos el archivo con `wget`.
- Después utilizamos `grep` para buscar directamente la cadena `picoCTF`.

```bash
maxsteel05-picoctf@webshell:~$ wget https://challenge-files.picoctf.net/c_fickle_tempest/d0b2e96347614d19414d591c946a1789fa8bd

maxsteel05-picoctf@webshell:~$ cat file | grep 'picoCTF'
picoCTF{grep_is_good_to_find_things_e3c4b360}
```

### Solución 2

- Descargamos el archivo.
- Al abrirlo o revisarlo, utilizamos `grep` para localizar rápidamente la flag sin tener que buscar manualmente entre todo el contenido.

```bash
grep 'picoCTF' file
```

## Flag

`picoCTF{grep_is_good_to_find_things_e3c4b360}`

## Notas

- `wget` permite descargar archivos desde una URL utilizando la terminal.
- `cat` muestra el contenido de un archivo.
- `grep` permite buscar una palabra o cadena específica dentro del contenido.
- En este reto, `grep` evita tener que revisar manualmente todo el archivo.

## Referencias

- [GNU grep](https://www.gnu.org/software/grep/manual/grep.html)
- [GNU Wget](https://www.gnu.org/software/wget/)
-
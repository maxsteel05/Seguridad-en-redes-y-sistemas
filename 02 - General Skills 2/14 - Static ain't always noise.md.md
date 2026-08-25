# Reto

## Descripción

Can you look at the data in this binary? The bash script might help!

Archivos proporcionados:

- `static`
- `ltdis.sh`

## Solución

### Solución 1

- Usando Linux.
- Descargamos los archivos `static` y `ltdis.sh` proporcionados por el reto.
- Utilizamos `file` para identificar qué tipo de archivos son.
- Después damos permisos de ejecución al script `ltdis.sh`.
- Ejecutamos el script pasando `static` como argumento.
- Finalmente utilizamos `strings` y `grep` para buscar directamente la flag dentro del binario.

```bash
maxsteel05-picoctf@webshell:~$ file *
README.txt: ASCII text
ltdis.sh: Bourne-Again shell script, ASCII text executable
static: ELF 64-bit LSB pie executable, x86-64

maxsteel05-picoctf@webshell:~$ chmod +x ltdis.sh

maxsteel05-picoctf@webshell:~$ ./ltdis.sh
Attempting disassembly of ...
Disassembly failed!
Usage: ltdis.sh <program-file>
Bye!

maxsteel05-picoctf@webshell:~$ ./ltdis.sh static
Attempting disassembly of static ...
Disassembly successful! Available at: static.ltdis.x86_64.txt
Ripping strings from binary with file offsets...
Any strings found in static have been written to static.ltdis.strings.txt with file offset

maxsteel05-picoctf@webshell:~$ strings static | grep pico
picoCTF{d15a5m_t34s3r_20335c41}
```

## Flag

`picoCTF{d15a5m_t34s3r_20335c41}`

## Notas

- `file` permite identificar el tipo de un archivo.
- `chmod +x` permite darle permisos de ejecución a un script.
- El script `ltdis.sh` necesita recibir el nombre del archivo que queremos analizar como argumento.
- `strings` extrae las cadenas de texto legibles que existen dentro de un archivo binario.
- `grep pico` permite filtrar la salida para buscar únicamente la cadena relacionada con `picoCTF`.
- No fue necesario ejecutar directamente el binario para localizar la flag.

## Referencias

- [GNU Strings](https://sourceware.org/binutils/docs/binutils/strings.html)
- [GNU grep](https://www.gnu.org/software/grep/manual/grep.html)
- [GNU Coreutils - chmod](https://www.gnu.org/software/coreutils/manual/html_node/chmod-invocation.html)
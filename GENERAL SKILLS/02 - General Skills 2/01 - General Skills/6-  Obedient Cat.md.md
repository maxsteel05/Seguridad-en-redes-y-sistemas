# Reto

## Descripción

This file has a flag in plain sight (aka "in-the-clear").

## Solución

### Solución 1

- Usando la consola de Linux.
- Primero descargamos el archivo con `wget`.
- Después usamos `cat` para mostrar directamente el contenido del archivo llamado `flag`.

```bash
maxsteel05-picoctf@webshell:~$ wget https://challenge-files.picoctf.net/c_wily_courier/4acf636990e4540d6fc36684b1256e625c0617d
maxsteel05-picoctf@webshell:~$ cat flag
picoCTF{s4n1ty_v3r1f13d_9b8fa0bc}
```

## Flag

`picoCTF{s4n1ty_v3r1f13d_9b8fa0bc}`

## Notas

- `wget` permite descargar archivos de Internet directamente desde la consola.
- `cat` permite mostrar el contenido de un archivo en la terminal.
- En este reto la flag se encontraba directamente dentro del archivo, sin ningún tipo de codificación.

## Referencias

- [GNU Wget](https://www.gnu.org/software/wget/)
- [GNU Coreutils - cat](https://www.gnu.org/software/coreutils/manual/html_node/cat-invocation.html)
-
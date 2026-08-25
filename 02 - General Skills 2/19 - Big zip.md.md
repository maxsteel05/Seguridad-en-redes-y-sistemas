# Reto

## Descripción

Unzip this archive and find the flag.

- Download zip file

## Solución

### Solución 1

- Usando Linux.
- Primero descargamos el archivo `.zip` con `wget`.
- Después lo descomprimimos utilizando `unzip`.
- Entramos a la carpeta extraída.
- Finalmente usamos `grep -r pico` para buscar de forma recursiva la palabra `pico` dentro de todos los archivos y subdirectorios.

Primero descargamos y descomprimimos el archivo:

```bash
maxsteel05-picoctf@webshell:~$ wget https://artifacts.picoctf.net/c/503/big-zip-files.zip
maxsteel05-picoctf@webshell:~$ unzip big-zip-files.zip
```

Revisamos los archivos disponibles:

```bash
maxsteel05-picoctf@webshell:~$ ls
Addadshashanammu  big-zip-files.zip  static.ltdis.strings.txt
Addadshashanammu.zip  enc_flag  static.ltdis.x86_64.txt
README.txt  ltdis.sh
big-zip-files  static
```

Entramos a la carpeta descomprimida:

```bash
maxsteel05-picoctf@webshell:~$ cd big-zip-files/
```

Después buscamos recursivamente la palabra `pico`:

```bash
maxsteel05-picoctf@webshell:~/big-zip-files$ grep -r pico
folder_pmbymkjcya/folder_cawigcwv/folder_1tdayfmktry/folder_fnpfclfyee/whzxrpivpqld.txt:information on the record will last a lifetime
```

Al localizar el archivo correspondiente obtenemos la flag:

## Flag

`picoCTF{gr3p_15_m4g1c_ef8790dc}`

## Notas

- `wget` permite descargar archivos desde Internet directamente desde la terminal.
- `unzip` permite descomprimir archivos con extensión `.zip`.
- `cd` permite cambiar de directorio.
- `grep` permite buscar texto dentro de archivos.
- La opción `-r` significa **recursive**, por lo que `grep` busca también dentro de todas las subcarpetas.
- Este comando es muy útil cuando existen demasiados archivos y carpetas para revisarlos manualmente.

## Referencias

- [GNU grep](https://www.gnu.org/software/grep/manual/grep.html)
- [GNU Wget](https://www.gnu.org/software/wget/)
- [Info-ZIP](https://infozip.sourceforge.net/)
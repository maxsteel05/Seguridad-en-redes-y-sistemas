# Reto

## Descripción

Can you crack the password to get the flag?

Download the password checker and you'll need the encrypted flag and the hash in the same directory too.

There are 7 potential passwords with 1 being correct. You can find these by examining the password checker script.

## Solución

### Solución 1

- Usando Linux y Python.
- Primero descargamos los archivos `level3.py`, `level3.flag.txt.enc` y `level3.hash.bin`.
- Después abrimos `level3.py` con `vim` para revisar el código sin modificarlo.
- Dentro del programa encontramos una lista con 7 posibles contraseñas.
- Probamos las contraseñas una por una ejecutando el programa hasta encontrar la correcta.
- La contraseña correcta fue `2295`.
- Al ingresar la contraseña correcta, el programa mostró la flag.

Primero descargamos `level3.py`:

```bash
maxsteel05-picoctf@webshell:~$ wget https://artifacts.picoctf.net/c/18/level3.py
```

Después descargamos el archivo cifrado:

```bash
maxsteel05-picoctf@webshell:~$ wget https://artifacts.picoctf.net/c/18/level3.flag.txt.enc
```

Descargamos también el archivo que contiene el hash:

```bash
maxsteel05-picoctf@webshell:~$ wget https://artifacts.picoctf.net/c/18/level3.hash.bin
```

Abrimos el programa para revisar su contenido:

```bash
maxsteel05-picoctf@webshell:~$ vim level3.py
```

Después ejecutamos el programa y probamos las posibles contraseñas:

```bash
maxsteel05-picoctf@webshell:~$ python level3.py
Please enter correct password for flag:
That password is incorrect
```

Volvemos a ejecutar el programa con las diferentes opciones encontradas en el código hasta encontrar la contraseña correcta:

```bash
maxsteel05-picoctf@webshell:~$ python level3.py
Please enter correct password for flag: 2295
Welcome back... your flag, user:
picoCTF{m45h_fl1ng1ng_6f98a49f}
maxsteel05-picoctf@webshell:~$
```

## Flag

`picoCTF{m45h_fl1ng1ng_6f98a49f}`

## Notas

- `wget` permite descargar archivos desde Internet directamente en la terminal.
- Los tres archivos deben encontrarse en el mismo directorio para que el programa funcione correctamente.
- `vim` permite abrir y revisar el código del archivo `level3.py`.
- Dentro del código se encontraba una lista con 7 posibles contraseñas.
- Para no modificar el programa, revisé el contenido con `vim` y posteriormente probé las opciones proporcionadas.
- La contraseña correcta fue `2295`.
- El archivo `level3.hash.bin` contiene el hash utilizado por el programa para comprobar si la contraseña ingresada es correcta.

## Referencias

- [Python](https://www.python.org/)
- [Vim](https://www.vim.org/)
- [GNU Wget](https://www.gnu.org/software/wget/)
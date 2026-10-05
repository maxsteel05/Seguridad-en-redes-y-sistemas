# Reto

## Descripción

Can you crack the password to get the flag?

Download the password checker and you'll need the encrypted flag in the same directory too.

## Solución

### Solución 1

- Usando Linux y Python.
- Primero descargamos el archivo `level1.py`.
- Después descargamos el archivo cifrado `level1.flag.txt.enc`.
- Revisamos el código de `level1.py` con un editor de texto para encontrar la contraseña correcta.
- Finalmente ejecutamos el programa e ingresamos la contraseña encontrada para obtener la flag.

Descargamos el programa:

```bash
maxsteel05-picoctf@webshell:~$ wget -q https://artifacts.picoctf.net/c/10/level1.py
```

Descargamos el archivo cifrado:

```bash
maxsteel05-picoctf@webshell:~$ wget -q https://artifacts.picoctf.net/c/10/level1.flag.txt.enc
```

Comprobamos que ambos archivos estén disponibles:

```bash
maxsteel05-picoctf@webshell:~$ ls
README.txt  files  level1.flag.txt.enc  level1.py
```

Abrimos el programa para revisar su código:

```bash
maxsteel05-picoctf@webshell:~$ nano level1.py
```

Después ejecutamos el programa:

```bash
maxsteel05-picoctf@webshell:~$ python level1.py
Please enter correct password for flag:
That password is incorrect
```

Al revisar el código encontramos que la contraseña correcta es:

```text
691d
```

Volvemos a ejecutar el programa e ingresamos la contraseña:

```bash
maxsteel05-picoctf@webshell:~$ python level1.py
Please enter correct password for flag: 691d
Welcome back... your flag, user:
picoCTF{545h_r1ng1ng_56891419}
maxsteel05-picoctf@webshell:~$
```

## Flag

`picoCTF{545h_r1ng1ng_56891419}`

## Notas

- `wget -q` permite descargar archivos sin mostrar el progreso de la descarga.
- `ls` permite comprobar qué archivos se encuentran en el directorio actual.
- `nano` permite abrir y revisar el código de un archivo desde la terminal.
- Se revisó el archivo `level1.py` para encontrar la contraseña requerida por el programa.
- La contraseña encontrada fue `691d`.
- El archivo `level1.flag.txt.enc` debe encontrarse en el mismo directorio que `level1.py` para que el programa pueda obtener la flag.

## Referencias

- [Python](https://www.python.org/)
- [GNU Nano](https://www.nano-editor.org/)
- [GNU Wget](https://www.gnu.org/software/wget/)
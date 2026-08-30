# Reto

## Descripción

Can you crack the password to get the flag?

Download the password checker and you'll need the encrypted flag in the same directory too.

## Solución

### Solución 1

- Usando Linux y Python.
- Primero descargamos los archivos `level2.py` y `level2.flag.txt.enc`.
- Después revisamos el código de `level2.py` para encontrar la parte donde se construye la contraseña.
- Encontramos varios valores dentro de la función `chr()`.
- Utilizamos Python para convertir esos valores a caracteres.
- La contraseña obtenida fue `de76`.
- Finalmente ejecutamos `level2.py` e ingresamos la contraseña correcta para obtener la flag.

Primero descargamos el archivo `level2.py`:

```bash
maxsteel05-picoctf@webshell:~$ wget https://artifacts.picoctf.net/c/13/level2.py
```

Después descargamos el archivo cifrado:

```bash
maxsteel05-picoctf@webshell:~$ wget https://artifacts.picoctf.net/c/13/level2.flag.txt.enc
```

Abrimos el archivo para revisar el código:

```bash
maxsteel05-picoctf@webshell:~$ nano level2.py
```

También podemos utilizar `vim`:

```bash
maxsteel05-picoctf@webshell:~$ vim level2.py
```

Dentro del código encontramos una expresión formada por varias funciones `chr()`.

Entramos a Python:

```bash
maxsteel05-picoctf@webshell:~$ python
Python 3.10.12
>>>
```

Convertimos los valores a caracteres:

```python
>>> print(chr(0x64) + chr(0x65) + chr(0x37) + chr(0x36))
de76
```

La contraseña obtenida es:

```text
de76
```

Salimos de Python:

```python
>>> exit()
```

Finalmente ejecutamos el programa:

```bash
maxsteel05-picoctf@webshell:~$ python level2.py
Please enter correct password for flag: de76
Welcome back... your flag, user:
picoCTF{tr45h_51ng1ng_489dea9a}
maxsteel05-picoctf@webshell:~$
```

## Flag

`picoCTF{tr45h_51ng1ng_489dea9a}`

## Notas

- `wget` permite descargar los archivos directamente desde Internet.
- `nano` y `vim` son editores de texto que permiten revisar el código desde la terminal.
- `chr()` convierte un valor numérico en su carácter correspondiente.
- Los valores encontrados fueron `0x64`, `0x65`, `0x37` y `0x36`.
- Al convertirlos con Python obtenemos:

```text
0x64 → d
0x65 → e
0x37 → 7
0x36 → 6
```

- Al unir los caracteres obtenemos la contraseña `de76`.
- Después se ejecuta `python level2.py` y se introduce la contraseña para obtener la flag.

## Referencias

- [Python - chr()](https://docs.python.org/3/library/functions.html#chr)
- [GNU Nano](https://www.nano-editor.org/)
- [Vim](https://www.vim.org/)
- [GNU Wget](https://www.gnu.org/software/wget/)
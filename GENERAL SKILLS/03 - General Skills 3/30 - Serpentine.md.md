# Reto

## Descripción

Find the flag in the Python script!

Download the Python script `serpentine.py`, examine the source code and determine how to make the program print the flag.

## Solución

### Solución 1

- Usando Linux y Python.
- Primero descargamos el archivo `serpentine.py`.
- Después ejecutamos el programa para revisar su funcionamiento.
- Al seleccionar la opción `b) Print flag`, el programa indica que la función encargada de imprimir la flag no está siendo llamada correctamente.
- Revisamos el código fuente y encontramos que la función `print_flag()` sí existe.
- Modificamos la opción `b` para que llame directamente a `print_flag()`.
- Finalmente ejecutamos nuevamente el programa y seleccionamos la opción `b`.

Primero descargamos el archivo:

```bash
maxsteel05-picoctf@webshell:~$ wget -q https://artifacts.picoctf.net/c/74/serpentine.py
```

Ejecutamos el programa:

```bash
maxsteel05-picoctf@webshell:~$ python serpentine.py
```

El programa muestra un menú parecido al siguiente:

```text
Welcome to the serpentine encourager!

a) Print encouragement
b) Print flag
c) Quit

What would you like to do? (a/b/c) b

Oops! I must have misplaced the print_flag function! Check my source code!
```

Esto indica que la opción `b` no está llamando correctamente a la función que imprime la flag.

Abrimos el archivo para revisar el código:

```bash
maxsteel05-picoctf@webshell:~$ nano serpentine.py
```

También se puede descargar el archivo y abrirlo con Visual Studio Code.

Dentro del código encontramos algo parecido a:

```python
elif choice == 'b':
    print('\nOops! I must have misplaced the print_flag function! Check my source code!\n\n')
```

La función `print_flag()` ya existe dentro del programa, así que modificamos esa parte para llamarla directamente:

```python
elif choice == 'b':
    print_flag()
```

Guardamos los cambios y volvemos a ejecutar el programa:

```bash
maxsteel05-picoctf@webshell:~$ python serpentine.py
```

Seleccionamos:

```text
b
```

Y el programa muestra la flag:

```text
picoCTF{7h3_r04d_l355_7r4v3l3d_ae0b80bd}
```

## Flag

`picoCTF{7h3_r04d_l355_7r4v3l3d_ae0b80bd}`

## Notas

- Se modificó el código para que la opción `b` pudiera llamar a la función `print_flag()`.
- La función `print_flag()` ya existía dentro del programa, pero no era ejecutada cuando el usuario seleccionaba la opción para imprimir la flag.
- No fue necesario modificar el funcionamiento de la función `print_flag()`, solamente hacer que el menú la llamara correctamente.
- El archivo se puede editar utilizando `nano`, `vim` o Visual Studio Code.
- Después de modificar el programa, se vuelve a ejecutar y se selecciona la opción `b`.

## Referencias

- [Python](https://www.python.org/)
- [Python - Defining Functions](https://docs.python.org/3/tutorial/controlflow.html#defining-functions)
- [GNU Nano](https://www.nano-editor.org/)
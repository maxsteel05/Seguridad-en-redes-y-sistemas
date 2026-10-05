# Reto

## Descripción

Fix the syntax error in this Python script to print the flag.

- Download Python script

## Solución

### Solución 1

- Usando Linux y Python.
- Primero descargamos el archivo `fixme1.py` utilizando `wget`.
- Ejecutamos el programa con Python y observamos que aparece un error de indentación.
- Abrimos el archivo con `nano` para corregir el error.
- Eliminamos la indentación incorrecta de la línea indicada.
- Finalmente volvemos a ejecutar el programa para obtener la flag.

Descargamos el archivo:

```bash
maxsteel05-picoctf@webshell:~$ wget -q https://artifacts.picoctf.net/c/27/fixme1.py
```

Ejecutamos el programa:

```bash
maxsteel05-picoctf@webshell:~$ python fixme1.py
  File "/home/maxsteel05-picoctf/fixme1.py", line 20
    print("That is correct! Here's your flag: " + flag)
IndentationError: unexpected indent
```

El error indica que existe una indentación incorrecta en la línea 20. Abrimos el archivo con `nano`:

```bash
maxsteel05-picoctf@webshell:~$ nano fixme1.py
```

Corregimos la indentación de la línea:

```python
print("That is correct! Here's your flag: " + flag)
```

Guardamos el archivo y volvemos a ejecutarlo:

```bash
maxsteel05-picoctf@webshell:~$ python fixme1.py
That is correct! Here's your flag: picoCTF{1nd3nt1ty_cr1515_182342f7}
maxsteel05-picoctf@webshell:~$
```

## Flag

`picoCTF{1nd3nt1ty_cr1515_182342f7}`

## Notas

- `wget -q` permite descargar un archivo sin mostrar el progreso de la descarga.
- `python fixme1.py` ejecuta el archivo de Python desde la terminal.
- `IndentationError: unexpected indent` indica que existe una sangría o espacio adicional donde Python no lo espera.
- Python utiliza la indentación para determinar la estructura del código, por lo que una sangría incorrecta puede impedir que el programa se ejecute.
- `nano` es un editor de texto que permite modificar archivos directamente desde la terminal.
- Después de corregir la indentación, el programa se ejecutó correctamente y mostró la flag.

## Referencias

- [Python - Indentation](https://docs.python.org/3/reference/lexical_analysis.html#indentation)
- [GNU Nano](https://www.nano-editor.org/)
- [GNU Wget](https://www.gnu.org/software/wget/)
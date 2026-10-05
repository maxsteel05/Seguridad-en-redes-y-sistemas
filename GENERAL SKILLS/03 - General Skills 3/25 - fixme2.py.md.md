# Reto

## Descripción

Fix the syntax error in the Python script to print the flag.

## Solución

### Solución 1

- Usando Linux y Python.
- Primero descargamos el archivo `fixme2.py` utilizando `wget`.
- Después abrimos el archivo con `nano` para localizar y corregir el error de sintaxis.
- Una vez corregido, ejecutamos nuevamente el programa con Python.
- El script se ejecutó correctamente y mostró la flag.

Descargamos el archivo:

```bash
maxsteel05-picoctf@webshell:~$ wget -q https://artifacts.picoctf.net/c/5/fixme2.py
```

Comprobamos que el archivo se descargó:

```bash
maxsteel05-picoctf@webshell:~$ ls
fixme2.py
```

Abrimos el archivo para corregir el error:

```bash
maxsteel05-picoctf@webshell:~$ nano fixme2.py
```

Después de realizar la corrección, ejecutamos el programa:

```bash
maxsteel05-picoctf@webshell:~$ python fixme2.py
That is correct! Here's your flag: picoCTF{3qu4l1ty_n0t_4551gnm3nt_4863e11b}
maxsteel05-picoctf@webshell:~$
```

## Flag

`picoCTF{3qu4l1ty_n0t_4551gnm3nt_4863e11b}`

## Notas adicionales

- `wget -q` permite descargar el archivo sin mostrar el progreso de la descarga.
- `nano` permite editar archivos directamente desde la terminal.
- `python fixme2.py` ejecuta el script después de corregir el error.
- En Python es importante diferenciar entre el operador de asignación `=` y el operador de comparación `==`.
- Un error de sintaxis impide que Python ejecute correctamente el programa hasta que sea corregido.

## Referencias

- [Python - Comparisons](https://docs.python.org/3/reference/expressions.html#comparisons)
- [GNU Nano](https://www.nano-editor.org/)
- [GNU Wget](https://www.gnu.org/software/wget/)
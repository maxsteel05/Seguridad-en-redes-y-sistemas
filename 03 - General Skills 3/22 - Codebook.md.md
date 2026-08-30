# Reto

## Descripción

Run the Python script `code.py` in the same directory as `codebook.txt`.

- Download `code.py`
- Download `codebook.txt`

## Solución

### Solución 1

- Usando Linux y Python.
- Primero descargamos el archivo `code.py`.
- Después descargamos el archivo `codebook.txt`.
- Verificamos que ambos archivos se encuentren en el mismo directorio.
- Finalmente ejecutamos `code.py` con Python para obtener la flag.

Descargamos el archivo `code.py`:

```bash
maxsteel05-picoctf@webshell:~$ wget https://artifacts.picoctf.net/c/3/code.py
```

Después descargamos `codebook.txt`:

```bash
maxsteel05-picoctf@webshell:~$ wget https://artifacts.picoctf.net/c/3/codebook.txt
```

Comprobamos que ambos archivos estén en la misma carpeta:

```bash
maxsteel05-picoctf@webshell:~$ ls
README.txt  code.py  codebook.txt  files  files.zip
```

Finalmente ejecutamos el programa:

```bash
maxsteel05-picoctf@webshell:~$ python code.py
picoCTF{c0d3b00k_455157_197a982c}
```

## Flag

`picoCTF{c0d3b00k_455157_197a982c}`

## Notas

- `wget` permite descargar archivos directamente desde Internet utilizando la terminal.
- La opción `-q` de `wget` permite realizar la descarga en modo silencioso, evitando mostrar el progreso y gran parte de la información de la descarga.
- `ls` permite verificar qué archivos se encuentran en el directorio actual.
- Para que el programa funcione correctamente, `code.py` y `codebook.txt` deben estar en el mismo directorio.
- `python code.py` ejecuta el script de Python desde la terminal.

## Referencias

- [Python](https://www.python.org/)
- [GNU Wget](https://www.gnu.org/software/wget/)
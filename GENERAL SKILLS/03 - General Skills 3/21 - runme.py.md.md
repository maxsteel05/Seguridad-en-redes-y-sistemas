# Reto

## Descripción

Run the `runme.py` script to get the flag. Download the script with your browser or with `wget` in the webshell.

## Solución

### Solución 1

- Usando Linux y Python.
- Primero descargamos el archivo `runme.py` con `wget`.
- Después utilizamos `ls` para comprobar que el archivo fue descargado correctamente.
- Con `file` verificamos que se trata de un script de Python.
- Finalmente ejecutamos el archivo con `python runme.py` para obtener la flag.

```bash
maxsteel05-picoctf@webshell:~$ wget https://artifacts.picoctf.net/c/34/runme.py
Resolving artifacts.picoctf.net (artifacts.picoctf.net)...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.170.131.18|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 270 [application/octet-stream]
Saving to: 'runme.py'

runme.py                  100%[============================>] 270  --.-KB/s  in 0s

'runme.py' saved [270/270]

maxsteel05-picoctf@webshell:~$ ls
README.txt  file  flag  runme.py

maxsteel05-picoctf@webshell:~$ file runme.py
runme.py: Python script, ASCII text executable

maxsteel05-picoctf@webshell:~$ python runme.py
picoCTF{run_s4n1ty_run}

maxsteel05-picoctf@webshell:~$
```

## Flag

`picoCTF{run_s4n1ty_run}`

## Notas

- `wget` permite descargar archivos directamente desde Internet utilizando la terminal.
- `ls` permite visualizar los archivos que existen en el directorio actual.
- `file` permite identificar el tipo de archivo.
- `python` se utiliza para ejecutar archivos `.py` desde la terminal.
- En este reto solamente fue necesario descargar y ejecutar el script proporcionado.

## Referencias

- [Python](https://www.python.org/)
- [GNU Wget](https://www.gnu.org/software/wget/)
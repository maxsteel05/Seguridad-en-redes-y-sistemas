# Reto

## Descripción

Run the Python script and convert the given number from decimal to binary to get the flag.

- Download Python script

## Solución

### Solución 1

- Usando Linux y Python.
- Primero descargamos el archivo `convertme.py` utilizando `wget`.
- Después verificamos que el archivo se encuentre en el directorio.
- Ejecutamos el programa con Python.
- El programa nos proporciona un número decimal que debemos convertir a binario.
- Finalmente escribimos el valor binario correcto para obtener la flag.

Descargamos el archivo:

```bash
maxsteel05-picoctf@webshell:~$ wget -q https://artifacts.picoctf.net/c/23/convertme.py
```

Comprobamos los archivos disponibles:

```bash
maxsteel05-picoctf@webshell:~$ ls
README.txt  code.py.1  codebook.txt.1  file  runme.py
code.py     codebook.txt  convertme.py  flag
```

Ejecutamos el programa:

```bash
maxsteel05-picoctf@webshell:~$ python convertme.py
If 73 is in decimal base, what is it in binary base?
Answer: 00110111 00110011
That isn't a binary number. Binary numbers contain only 1's and 0's
```

Volvemos a ejecutar el programa:

```bash
maxsteel05-picoctf@webshell:~$ python convertme.py
If 52 is in decimal base, what is it in binary base?
Answer: 110100
That is correct! Here's your flag: picoCTF{4ll_y0ur_b4535_9c3b7d4d}
maxsteel05-picoctf@webshell:~$
```

### Solución 2

- Usando CyberChef.
- Introducimos el número decimal `52`.
- Utilizamos la operación `To Base`.
- Configuramos el `Radix` en `2` para convertir el número a binario.

[CyberChef - Decimal a Binario](https://gchq.github.io/CyberChef/#recipe=To_Base(2)&input=NTI)

```text
Decimal: 52
Binario: 110100
```

## Flag

`picoCTF{4ll_y0ur_b4535_9c3b7d4d}`

## Notas

- `wget -q` descarga el archivo en modo silencioso, evitando mostrar el progreso de la descarga.
- `python convertme.py` ejecuta el script desde la terminal.
- El sistema binario solamente utiliza los dígitos `0` y `1`.
- `52` en decimal equivale a `110100` en binario.
- En CyberChef se utiliza `To Base` con `Radix = 2` para realizar la conversión de decimal a binario.
- El número solicitado por el programa puede cambiar cada vez que se ejecuta, por lo que se debe convertir el valor que aparezca en ese momento.

## Referencias

- [Python](https://www.python.org/)
- [CyberChef](https://gchq.github.io/CyberChef/)
- [GNU Wget](https://www.gnu.org/software/wget/)
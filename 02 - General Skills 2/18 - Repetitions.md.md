# Reto

## Descripción

Can you make sense of this file? Download the file here.

## Solución

### Solución 1

- Usando Linux y CyberChef.
- Primero descargamos el archivo `enc_flag` utilizando `wget`.
- Después utilizamos `file` para identificar el tipo de archivo.
- Con `cat` mostramos la cadena codificada que contiene.
- La cadena estaba codificada varias veces en Base64, por lo que fue necesario decodificarla 6 veces.

Primero descargamos el archivo:

```bash
maxsteel05-picoctf@webshell:~$ wget https://artifacts.picoctf.net/c/471/enc_flag
```

Comprobamos qué tipo de archivo es:

```bash
maxsteel05-picoctf@webshell:~$ file enc_flag
enc_flag: ASCII text
```

Después mostramos su contenido:

```bash
maxsteel05-picoctf@webshell:~$ cat enc_flag
```

### Opción 1: CyberChef

- Abrimos [CyberChef](https://gchq.github.io/CyberChef/).
- Pegamos el contenido del archivo.
- Agregamos 6 veces la operación `From Base64`.
- Después de realizar todas las decodificaciones obtenemos la flag.

### Opción 2: Linux

También podemos realizar todas las decodificaciones directamente desde la terminal utilizando varios comandos `base64 -d` conectados mediante pipes:

```bash
maxsteel05-picoctf@webshell:~$ cat enc_flag | base64 -d | base64 -d | base64 -d | base64 -d | base64 -d | base64 -d
picoCTF{base64_n3st3d_dic0d!n8_d0wnl04d3d_9b59b35c}
maxsteel05-picoctf@webshell:~$
```

## Flag

`picoCTF{base64_n3st3d_dic0d!n8_d0wnl04d3d_9b59b35c}`

## Notas

- `wget` permite descargar archivos desde Internet directamente en la terminal.
- `file` permite identificar el tipo de archivo.
- `cat` muestra el contenido de un archivo.
- `base64 -d` permite decodificar información codificada en Base64.
- El símbolo `|` envía la salida de un comando como entrada del siguiente.
- En este reto fue necesario aplicar `base64 -d` 6 veces para llegar al texto original.

## Referencias

- [CyberChef](https://gchq.github.io/CyberChef/)
- [GNU Coreutils - Base64](https://www.gnu.org/software/coreutils/manual/html_node/base64-invocation.html)
- [GNU Wget](https://www.gnu.org/software/wget/)
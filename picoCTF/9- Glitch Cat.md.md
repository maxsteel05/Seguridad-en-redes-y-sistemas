# Reto

## Descripción

Our flag printing service has started glitching!

```bash
nc saturn.picoctf.net 49929
```

## Solución

### Solución 1

- Usando Linux y Python.
- Primero utilizamos `nc` para conectarnos al servidor y obtener la cadena que contiene varias funciones `chr()`.
- Después copiamos esa cadena y la ejecutamos en Python para convertir los valores hexadecimales en caracteres y obtener la flag completa.

```bash
maxsteel05-picoctf@webshell:~$ nc saturn.picoctf.net 49929
'picoCTF{gl17ch_m3_n07_' + chr(0x39) + chr(0x63) + chr(0x34) + chr(0x32) + chr(0x61) + chr(0x34) + chr(0x35) + chr(0x64) + '}'
```

Después entramos a Python y pegamos la cadena obtenida:

```python
>>> 'picoCTF{gl17ch_m3_n07_' + chr(0x39) + chr(0x63) + chr(0x34) + chr(0x32) + chr(0x61) + chr(0x34) + chr(0x35) + chr(0x64) + '}'
'picoCTF{gl17ch_m3_n07_9c42a45d}'
```

## Flag

`picoCTF{gl17ch_m3_n07_9c42a45d}`

## Notas

- Primero se ejecuta `nc` directamente en la consola de Linux.
- Después se copia la respuesta obtenida y se ejecuta dentro de Python.
- `chr()` convierte un número en el carácter correspondiente de acuerdo con su código Unicode.
- Los valores como `0x39`, `0x63` y `0x34` están escritos en hexadecimal.
- Al unir todos los caracteres se obtiene la flag completa.

## Referencias

- [Python - chr()](https://docs.python.org/3/library/functions.html#chr)
- [Netcat](https://en.wikipedia.org/wiki/Netcat)
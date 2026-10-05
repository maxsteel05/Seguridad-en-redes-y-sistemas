# Reto

## Descripción

Sometimes you need to handle process data outside of a file. Can you find a way to keep the output from this program and search for the flag?

Connect to `fickle-tempest.picoctf.net` at port `54095`.

## Solución

### Solución 1

- Usando Linux.
- Utilizamos `nc` para conectarnos al servidor de picoCTF.
- Con `|` enviamos la salida del comando `nc` directamente hacia `grep`.
- Finalmente, `grep pico` busca únicamente la línea que contiene la palabra `pico`, permitiendo encontrar rápidamente la flag.

```bash
maxsteel05-picoctf@webshell:~$ nc fickle-tempest.picoctf.net 54095 | grep pico
picoCTF{digital_plumb3r_8c8f3412}
```

## Flag

`picoCTF{digital_plumb3r_8c8f3412}`

## Notas

- `nc` o Netcat permite conectarse a un servidor mediante una dirección y un puerto.
- El símbolo `|` se conoce como *pipe* y permite enviar la salida de un comando como entrada de otro.
- `grep` permite buscar texto específico dentro de la información recibida.
- En este caso se utilizó `grep pico` para mostrar únicamente la línea que contenía la flag.

## Referencias

- [GNU grep](https://www.gnu.org/software/grep/manual/grep.html)
- [Netcat](https://en.wikipedia.org/wiki/Netcat)
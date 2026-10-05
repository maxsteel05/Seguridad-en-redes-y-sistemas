# Reto

## Descripción

To get truly 1337, you must understand different data encodings, such as hexadecimal or binary. Can you get the flag from this program to prove you are on the way to becoming 1337?

Connect with:

```bash
nc fickle-tempest.picoctf.net 64355
```

## Solución

### Solución 1

- Usando CyberChef.
- Se realizaron tres conversiones diferentes: binario, octal y hexadecimal.
- [CyberChef](https://gchq.github.io/CyberChef/)

#### Conversión de binario

- Recipe: `From Binary`
- Separador: `Space`

```text
01100011 01101111 01101101 01110000 01110101 01110100 01100101 01110010
```

Resultado:

```text
computer
```

#### Conversión de octal

- Primero se eliminó la letra `o` utilizando `Find / Replace`.
- Después se utilizó la receta `From Octal`.

```text
o141 o156 o151 o155 o141 o164 o151 o157 o156
```

Resultado:

```text
animation
```

#### Conversión de hexadecimal

- Recipe: `From Hex`

```text
616e696d6174696f6e
```

Resultado:

```text
animation
```

### Solución 2

- Usando Linux y CyberChef.
- Primero nos conectamos al servidor con `nc`.
- El programa proporciona datos codificados en distintos formatos.
- Convertimos cada valor en CyberChef y escribimos la palabra obtenida antes de que termine el tiempo.

```bash
maxsteel05-picoctf@webshell:~$ nc fickle-tempest.picoctf.net 56880
Let us see how data is stored
computer
Please give the 01100011 01101111 01101101 01110000 01110101 01110100 01100101 01110010 as a word.
...
you have 45 seconds......

Input:
computer
Please give me the o141 o156 o151 o155 o141 o164 o151 o157 o156 as a word.
Input:
animation
Please give me the 616e696d6174696f6e as a word.
Input:
animation
You've beaten the challenge
Flag: picoCTF{learning_about_converting_values_aeBEA593}
^C
maxsteel05-picoctf@webshell:~$
```

## Flag

`picoCTF{learning_about_converting_values_aeBEA593}`

## Notas

- Se usaron tres conversiones diferentes: binario, octal y hexadecimal.
- Para el primer valor se utilizó `From Binary`.
- Para el segundo valor se utilizó `Find / Replace` para quitar la letra `o` y después `From Octal`.
- Para el último valor se utilizó `From Hex`.
- El símbolo `o` delante de los números indica que los valores están representados en octal.
- En la captura, la conexión realizada utilizó el puerto `56880`, aunque la descripción del reto muestra el puerto `64355`. El puerto puede depender de la instancia activa del reto.

## Referencias

- [CyberChef](https://gchq.github.io/CyberChef/)
- [Netcat](https://en.wikipedia.org/wiki/Netcat)
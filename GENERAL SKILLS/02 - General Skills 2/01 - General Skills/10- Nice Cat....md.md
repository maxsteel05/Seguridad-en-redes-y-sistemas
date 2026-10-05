# Reto

## Descripción

There is a nice program that you can talk to by using this command in a shell:

```bash
nc wily-courier.picoctf.net 50505
```

But it doesn't speak English...

## Solución

### Solución 1

- Usando Linux y CyberChef.
- Primero nos conectamos al servidor utilizando `nc`.
- El servidor nos proporciona una serie de números en decimal.
- Copiamos esos números y los convertimos a texto utilizando CyberChef.
- En CyberChef seleccionamos la receta `From Decimal` y usamos espacio como separador.

```bash
maxsteel05-picoctf@webshell:~$ nc wily-courier.picoctf.net 50505
```

En CyberChef:

- Recipe: `From Decimal`
- Delimiter: `Space`
- Input: los números que nos proporcionó el servidor en Linux.

[CyberChef](https://gchq.github.io/CyberChef/)

## Flag

`picoCTF{g00d_k1tty_n1c3_k1tty!_a94e7}`

## Notas

- `nc` o Netcat permite conectarnos a un servidor mediante una dirección y un puerto.
- El servidor devuelve una serie de valores numéricos en decimal.
- La herramienta CyberChef permite convertir esos valores decimales a caracteres.
- La operación `From Decimal` interpreta cada número decimal y lo convierte en el carácter correspondiente.

## Referencias

- [CyberChef](https://gchq.github.io/CyberChef/)
- [Netcat](https://en.wikipedia.org/wiki/Netcat)
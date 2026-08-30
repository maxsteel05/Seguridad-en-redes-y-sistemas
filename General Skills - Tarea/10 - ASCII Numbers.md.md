# Reto

## Descripción

En este reto se debe convertir una cadena compuesta por valores ASCII escritos en hexadecimal a texto legible.

La descripción indica:

> Convert the following string of ASCII numbers into a readable string.

Se proporciona una secuencia de valores hexadecimales que representan caracteres ASCII.

### Pistas

1. **CyberChef** puede utilizarse para realizar conversiones y decodificaciones de diferentes formatos.
2. En CyberChef puede utilizarse la operación **From Hex** para transformar los valores hexadecimales a texto.

## Solución

### Solución 1

Primero copié la cadena hexadecimal proporcionada por el reto.

Después ingresé a CyberChef y coloqué la cadena dentro del apartado de entrada.

En la sección de operaciones busqué:

```text
From Hex
```

Agregué esa operación a la receta para que CyberChef interpretara cada par hexadecimal como un carácter ASCII.

Al realizar la conversión, la cadena hexadecimal se transformó directamente en texto legible.

El resultado obtenido fue:

```text
picoCTF{4ll_sp4c3_r3l4t3d_1n_4sc11_4c451a49}
```

## FLAG

```text
picoCTF{4ll_sp4c3_r3l4t3d_1n_4sc11_4c451a49}
```

## Notas

- ASCII asigna valores numéricos a letras, números y símbolos.
- Los valores proporcionados en el reto estaban escritos en hexadecimal.
- Cada par hexadecimal representa un carácter ASCII.
- Por ejemplo:

```text
70 = p
69 = i
63 = c
6f = o
```

- Al unir los caracteres convertidos se obtiene el texto completo.
- CyberChef facilita este proceso mediante la operación:

```text
From Hex
```

- También se podría realizar la conversión manualmente utilizando una tabla ASCII, aunque sería más tardado.

## Referencias

- https://picoctf.org/
- https://webshell.picoctf.org/
- https://gchq.github.io/CyberChef/
- https://en.wikipedia.org/wiki/ASCII
- https://en.wikipedia.org/wiki/Hexadecimal
# Reto

## Descripción

En este reto se practican **operaciones binarias básicas**. El servidor proporciona dos números binarios y solicita realizar diferentes operaciones entre ellos.

El objetivo es responder correctamente una serie de preguntas y, al finalizar, convertir el resultado de la última operación a hexadecimal.

La descripción del reto indica:

> How well can you perform basic binary operations?

Para comenzar se proporciona una conexión mediante `nc` al servidor de picoCTF.

## Solución

### Solución 1

Primero me conecté al servidor utilizando el comando proporcionado por el reto:

```bash
maxsteel05-academy@webshell:~$ nc titan.picoctf.net 64919
```

Al iniciar el reto aparecieron dos números binarios:

```text
Binary Number 1: 11010111
Binary Number 2: 00101001
```

El programa solicita realizar 6 operaciones diferentes.

### Pregunta 1

La primera operación fue:

```text
Operation 1: >>
Perform a right shift of Binary Number 2 by 2 bits.
```

El número utilizado fue:

```text
00101001
```

Al desplazarlo dos posiciones hacia la derecha:

```text
00101001 >> 2 = 00001010
```

Ingresé:

```text
00001010
```

Y el servidor respondió:

```text
Correct!
```

### Pregunta 2

La siguiente operación fue XOR:

```text
Operation 2: ^
Perform the operation on Binary Number 1 and Binary Number 2.
```

La operación fue:

```text
11010111
00101001
--------
11111110
```

Ingresé:

```text
11111110
```

Respuesta:

```text
Correct!
```

### Pregunta 3

Después apareció la operación de multiplicación:

```text
Operation 3: *
Perform the operation on Binary Number 1 and Binary Number 2.
```

El resultado ingresado fue:

```text
10001000
```

Y fue aceptado:

```text
Correct!
```

### Pregunta 4

La cuarta operación solicitó desplazar el primer número un bit hacia la izquierda:

```text
Operation 4: <<
Perform a left shift of Binary Number 1 by 1 bits.
```

El resultado fue:

```text
110101110
```

Ingresé:

```text
110101110
```

Respuesta:

```text
Correct!
```

### Pregunta 5

Después se solicitó realizar una operación OR:

```text
Operation 5: |
Perform the operation on Binary Number 1 and Binary Number 2.
```

La operación fue:

```text
11010111
00101001
--------
11111111
```

Ingresé:

```text
11111111
```

Respuesta:

```text
Correct!
```

### Pregunta 6

La última operación también utilizó los números binarios proporcionados:

```text
Operation 6: |
Perform the operation on Binary Number 1 and Binary Number 2.
```

El resultado ingresado fue:

```text
11111111
```

El servidor confirmó:

```text
Correct!
```

Después de responder correctamente las seis preguntas, el programa solicitó convertir el resultado de la última operación a hexadecimal:

```text
Enter the results of the last operation in hexadecimal:
```

El resultado binario era:

```text
11111111
```

Para convertirlo a hexadecimal se divide en dos grupos de 4 bits:

```text
1111 1111
```

Cada grupo `1111` equivale a:

```text
F
```

Por lo tanto:

```text
11111111 = FF
```

Ingresé:

```text
FF
```

El servidor respondió:

```text
Correct answer!
```

Finalmente mostró la flag del reto.

## FLAG

```text
picoCTF{b1tw^3se_0p3r@tI0n_su33essFuL_d6fb0b7e}
```

## Notas

- Los operadores binarios utilizados en el reto incluyen desplazamientos y operaciones lógicas.
- `>>` realiza un desplazamiento hacia la derecha.
- `<<` realiza un desplazamiento hacia la izquierda.
- `^` representa la operación XOR.
- `|` representa la operación OR.
- En una operación XOR el resultado es `1` cuando los bits son diferentes.
- En una operación OR el resultado es `1` cuando al menos uno de los bits es `1`.
- Un desplazamiento a la izquierda por un bit equivale, en términos generales, a multiplicar el número por 2.
- Un desplazamiento a la derecha por un bit equivale a dividir entre 2 descartando el residuo.
- Para convertir binario a hexadecimal se pueden separar los bits en grupos de cuatro.
- El grupo binario `1111` corresponde al valor hexadecimal `F`.
- Por esa razón:

```text
11111111 = FF
```

- Las operaciones y los números pueden cambiar al iniciar una nueva instancia del reto, por lo que los resultados también pueden variar.

## Referencias

- https://picoctf.org/
- https://webshell.picoctf.org/
- https://primer.picoctf.org/
- https://en.wikipedia.org/wiki/Bitwise_operation
- https://en.wikipedia.org/wiki/Hexadecimal
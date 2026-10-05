# Reto

## Descripción

En este reto se utiliza el concepto de **búsqueda binaria** para encontrar un número secreto dentro de un rango.

El programa piensa en un número entre `1` y `1000`, y solamente permite realizar **10 intentos**. Después de cada intento indica si el número correcto es mayor o menor que el valor ingresado.

La idea es reducir el rango de búsqueda aproximadamente a la mitad en cada intento hasta encontrar el número correcto.

La conexión proporcionada por el reto es:

```bash
ssh -p 52964 ctf-player@atlas.picoctf.net
```

### Pistas

1. La búsqueda binaria funciona de manera parecida al juego de "frío o caliente".
2. Como solamente existen 10 intentos, conviene realizar saltos grandes entre los números.
3. El número cambia cada vez que se inicia una nueva conexión, por lo que el proceso debe comenzar nuevamente.
4. Un buen punto de inicio es aproximadamente `500`, ya que se encuentra a la mitad del intervalo entre `1` y `1000`.

## Solución

### Solución 1

Primero inicié la conexión SSH con el servidor del reto:

```bash
maxsteel05-academy@webshell:~$ ssh -p 52964 ctf-player@atlas.picoctf.net
```

Al aparecer el mensaje de autenticidad del servidor confirmé la conexión escribiendo:

```text
yes
```

Después ingresé la contraseña proporcionada por picoCTF.

Al conectarme apareció el siguiente mensaje:

```text
Welcome to the Binary Search Game!
I'm thinking of a number between 1 and 1000.
```

En el primer intento comencé aproximadamente por la mitad del rango:

```text
Enter your guess: 250
Higher! Try again.
```

Después continué ajustando los valores dependiendo de las respuestas `Higher` y `Lower`.

En esa primera ronda realicé demasiados intentos, por lo que el programa terminó mostrando:

```text
Sorry, you've exceeded the maximum number of guesses.
Connection to atlas.picoctf.net closed.
```

Como el número cambia al iniciar una nueva sesión, me conecté nuevamente:

```bash
maxsteel05-academy@webshell:~$ ssh -p 52964 ctf-player@atlas.picoctf.net
```

En esta nueva ronda utilicé una estrategia más cercana a una búsqueda binaria.

Los intentos fueron:

```text
Enter your guess: 500
Lower! Try again.

Enter your guess: 250
Lower! Try again.

Enter your guess: 100
Lower! Try again.

Enter your guess: 50
Higher! Try again.

Enter your guess: 60
Higher! Try again.

Enter your guess: 70
Lower! Try again.

Enter your guess: 65
Higher! Try again.

Enter your guess: 68
Lower! Try again.

Enter your guess: 66
Higher! Try again.

Enter your guess: 67
```

Finalmente el programa confirmó que el número correcto era:

```text
Congratulations! You guessed the correct number: 67
```

Después de encontrar el valor correcto, el servidor mostró automáticamente la flag del reto.

## FLAG

```text
picoCTF{g00d_gu355_2af3fd11}
```

## Notas

- El reto utiliza el algoritmo de **búsqueda binaria**.
- El rango inicial contiene `1000` posibles números.
- Se permiten solamente `10` intentos.
- Después de cada número ingresado, el programa responde:

```text
Higher! Try again.
```

si el número secreto es mayor, o:

```text
Lower! Try again.
```

si el número secreto es menor.

- La estrategia consiste en reducir progresivamente el intervalo posible.
- Por ejemplo, si sabemos que el número se encuentra entre `60` y `70`, podemos probar aproximadamente el valor medio.
- En la segunda ronda el intervalo final se redujo de esta manera:

```text
50 < número < 100
60 < número < 70
65 < número < 70
65 < número < 68
66 < número < 68
```

Por lo tanto, el único valor restante era:

```text
67
```

- Si se superan los 10 intentos, la conexión se cierra.
- Al iniciar una nueva conexión, el servidor puede generar un número secreto diferente.
- El objetivo principal del reto es comprender cómo la búsqueda binaria permite reducir rápidamente una gran cantidad de posibilidades.

## Referencias

- https://picoctf.org/
- https://webshell.picoctf.org/
- https://primer.picoctf.org/
- https://en.wikipedia.org/wiki/Binary_search_algorithm
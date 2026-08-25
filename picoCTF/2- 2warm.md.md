# Reto

## Descripción

Can you convert the number 42 (base 10) to binary (base 2)?

## Solución

### Solución 1

- Usando CyberChef.
- [CyberChef](https://gchq.github.io/CyberChef/#recipe=To_Base(2)&input=NDI)
- Recipe: `To Base: 2`
- Input: `42`

### Solución 2

- Usando Python.

```bash
maxsteel05-picoctf@webshell:~$ python
>>> bin(42)
'0b101010'
```

## Flag

`picoCTF{101010}`

## Notas

- `bin()` se utiliza en Python para convertir un número entero a binario.
- El prefijo `0b` indica que el número está representado en binario.
- `42` en decimal equivale a `101010` en binario.

## Referencias

- [CyberChef](https://gchq.github.io/CyberChef/)
- [Python](https://www.python.org/)
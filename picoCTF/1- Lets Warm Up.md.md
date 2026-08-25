# Reto

## Descripción

If I told you a word started with 0x70 in hexadecimal, what would it start with in ASCII?

## Solución

### Solución 1

- Usando CyberChef.
- [CyberChef](https://gchq.github.io/CyberChef/#recipe=From_Hex('0x')&input=MHg3MA)

### Solución 2

- Usando Python.

```bash
maxsteel05-picoctf@webshell:~$ python
>>> int(0x70)
112
>>> chr(112)
'p'
>>>
```

## Flag

`picoCTF{p}`

## Notas

- `0x70` es un valor hexadecimal.
- `0x70` equivale a `112` en decimal.
- El valor `112` corresponde al carácter `p` en ASCII.

## Referencias

- [CyberChef](https://gchq.github.io/CyberChef/)
- [Python](https://www.python.org/)
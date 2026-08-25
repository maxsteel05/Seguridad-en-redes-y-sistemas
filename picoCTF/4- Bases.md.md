# Reto

## Descripción

What does this `bDNhcm5fdGgzX3IwcDM1` mean? I think it has something to do with bases.

## Solución

### Solución 1

- Usando CyberChef.
- [CyberChef](https://gchq.github.io/CyberChef/#recipe=From_Base64('A-Za-z0-9%2B%2F%3D',true,false)&input=YkROaGNtNWZkR2d6WDNJd2NETTE)
- Recipe: `From Base64`
- Input: `bDNhcm5fdGgzX3IwcDM1`

### Solución 2

- Usando Python.

```bash
maxsteel05-picoctf@webshell:~$ python
>>> import base64
>>> base64.b64decode('bDNhcm5fdGgzX3IwcDM1')
b'l3arn_th3_r0p35'
>>>
```

### Solución 3

- Usando Linux.

```bash
maxsteel05-picoctf@webshell:~$ echo 'bDNhcm5fdGgzX3IwcDM1' | base64 -d
l3arn_th3_r0p35
maxsteel05-picoctf@webshell:~$
```

## Flag

`picoCTF{l3arn_th3_r0p35}`

## Notas

- La cadena está codificada en Base64.
- En Python se puede decodificar usando el módulo `base64`.
- En Linux se puede utilizar el comando `base64 -d` para decodificarla.
- Se usó la consola de Linux para resolverlo.

## Referencias

- [CyberChef](https://gchq.github.io/CyberChef/)
- [Python - base64](https://docs.python.org/3/library/base64.html)
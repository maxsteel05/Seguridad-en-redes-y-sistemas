# Reto

## Descripción

Using netcat (nc) is going to be pretty important. Can you connect to fickle-tempest.picoctf.net at port 51188 to get the flag?

## Solución

### Solución 1

- Usando Linux.
- Utilizamos `nc` para conectarnos al servidor de picoCTF mediante el puerto `51188`.
- Al establecer la conexión, el servidor nos muestra directamente la flag.

```bash
maxsteel05-picoctf@webshell:~$ nc fickle-tempest.picoctf.net 51188
picoCTF{nEtCat_Mast3ry_5BBB6400}
```

## Flag

`picoCTF{nEtCat_Mast3ry_5BBB6400}`

## Notas

- `nc` significa Netcat.
- Netcat permite realizar conexiones de red mediante TCP o UDP.
- Para conectarnos utilizamos primero el nombre del servidor y después el número de puerto.
- En este reto el servidor entrega directamente la flag después de establecer la conexión.

## Referencias

- [Netcat](https://en.wikipedia.org/wiki/Netcat)
# Reto

## Descripción

Using a Secure Shell (SSH) is going to be pretty important.

Can you `ssh` as `ctf-player` to `titan.picoctf.net` at port `57717` to get the flag?

You'll also need the password:

```text
6dd28e9b
```

If asked, accept the fingerprint with `yes`.

## Solución

### Solución 1

- Usando Linux y SSH.
- Primero realizamos una conexión remota al servidor proporcionado por picoCTF.
- Utilizamos `ssh` con el usuario `ctf-player`.
- La opción `-p` permite indicar el puerto al que queremos conectarnos.
- Cuando el sistema pregunta si queremos continuar con la conexión, escribimos `yes`.
- Después ingresamos la contraseña proporcionada por el reto.
- Al conectarnos correctamente, el servidor muestra directamente la flag.

```bash
maxsteel05-picoctf@webshell:~$ ssh ctf-player@titan.picoctf.net -p 57717
The authenticity of host '[titan.picoctf.net]:57717' can't be established.
ED25519 key fingerprint is SHA256:4S9EbTSSRZm32I+cdM5TyztphQryv5kudRP9PIKT7XQ.
This host key is known by the following other names/addresses:
    ~/.ssh/known_hosts:1: [hashed name]
    ~/.ssh/known_hosts:2: [hashed name]
    ~/.ssh/known_hosts:3: [hashed name]
    ~/.ssh/known_hosts:4: [hashed name]
    ~/.ssh/known_hosts:5: [hashed name]
    ~/.ssh/known_hosts:6: [hashed name]
    ~/.ssh/known_hosts:7: [hashed name]
    ~/.ssh/known_hosts:8: [hashed name]

Are you sure you want to continue connecting (yes/no/[fingerprint])? yes
Warning: Permanently added '[titan.picoctf.net]:57717' (ED25519) to the list of known hosts.
ctf-player@titan.picoctf.net's password:
Welcome ctf-player, here's your flag: picoCTF{s3cur3_c0nn3ct10n_5d09a462}
Connection to titan.picoctf.net closed.
maxsteel05-picoctf@webshell:~$
```

## Flag

`picoCTF{s3cur3_c0nn3ct10n_5d09a462}`

## Notas

- `ssh` significa Secure Shell y permite conectarnos de manera remota y segura a otro equipo.
- La opción `-p` sirve para especificar el número de puerto que se utilizará para la conexión.
- En este caso el puerto utilizado fue `57717`.
- `ctf-player` es el usuario proporcionado por picoCTF.
- Cuando aparece la pregunta sobre el fingerprint, escribir `yes` permite guardar y aceptar la clave del servidor.
- Después de ingresar correctamente la contraseña, el servidor entrega directamente la flag.

## Referencias

- [OpenSSH](https://www.openssh.com/)
- [SSH Manual](https://man.openbsd.org/ssh)
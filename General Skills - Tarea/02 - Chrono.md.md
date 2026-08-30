# Reto

## Descripción

How to automate tasks to run at intervals on linux servers?

Use ssh to connect to this server:

Server: `saturn.picoctf.net`  
Port: `60689`  
Username: `picoplayer`  
Password: `ENAFb6zfxn`

## Solución

### Solución 1

- Usando Linux y una conexión mediante SSH.
- Primero nos conectamos al servidor proporcionado por picoCTF.
- Después revisamos los archivos disponibles dentro del directorio del usuario.
- Utilizamos `ls -la` para visualizar también los archivos ocultos.
- Como el reto pregunta sobre la automatización de tareas en intervalos dentro de Linux, revisamos la configuración relacionada con `cron`.
- Consultamos el archivo `/etc/crontab`.
- Dentro de este archivo encontramos la flag del reto.

Primero realizamos la conexión SSH al servidor:

```bash
maxsteel05-academy@webshell:~$ ssh -p 60689 picoplayer@saturn.picoctf.net
```

El servidor solicita confirmar la conexión:

```text
The authenticity of host '[saturn.picoctf.net]:60689' can't be established.
ED25519 key fingerprint is SHA256:dNfcRrUiUW7uMu5eGMcKd0fZKqLzkLfNhssNnNQ.
This key is not known by any other names
Are you sure you want to continue connecting (yes/no/[fingerprint])? yes
Warning: Permanently added '[saturn.picoctf.net]:60689' (ED25519) to the list of known hosts.
picoplayer@saturn.picoctf.net's password:
```

Después de ingresar correctamente la contraseña obtenemos acceso al servidor:

```text
Welcome to Ubuntu 20.04.5 LTS (GNU/Linux 6.17.0-1019-aws x86_64)
```

Revisamos los archivos disponibles en el directorio actual:

```bash
picoplayer@challenge:~$ ls
```

Después utilizamos `ls -la` para mostrar información más detallada y los archivos ocultos:

```bash
picoplayer@challenge:~$ ls -la
```

La terminal muestra:

```text
total 12
drwxr-xr-x 1 picoplayer picoplayer   20 Aug 30 03:56 .
drwxr-xr-x 1 root       root         24 Aug  4  2023 ..
-rw-r--r-- 1 picoplayer picoplayer  220 Feb 25  2020 .bash_logout
-rw-r--r-- 1 picoplayer picoplayer 3771 Feb 25  2020 .bashrc
drwx------ 2 picoplayer picoplayer   34 Aug 30 03:56 .cache
-rw-r--r-- 1 picoplayer picoplayer  807 Feb 25  2020 .profile
```

Como el reto menciona la ejecución automática de tareas en determinados intervalos, revisamos el archivo relacionado con las tareas programadas de Linux:

```bash
picoplayer@challenge:~$ cat /etc/crontab
```

Dentro del archivo encontramos la flag:

```text
# picoCTF{Sch3DUL7NG_T45K3_L1NUX_1d781160}
```

## Flag

`picoCTF{Sch3DUL7NG_T45K3_L1NUX_1d781160}`

## Notas

- `ssh` significa Secure Shell y permite conectarnos de manera remota y segura a otro equipo.
- La opción `-p` sirve para especificar el número de puerto que se utilizará para la conexión.
- En este caso el puerto utilizado fue `60689`.
- `picoplayer` es el usuario proporcionado por picoCTF para ingresar al servidor.
- Cuando aparece la pregunta sobre el fingerprint, escribir `yes` permite aceptar y guardar la clave del servidor.
- El comando `ls` permite visualizar los archivos disponibles en el directorio actual.
- El comando `ls -la` también muestra archivos ocultos, permisos, propietarios y otros detalles.
- `cron` es un servicio de Linux que permite programar tareas para que se ejecuten automáticamente en determinados momentos o intervalos.
- El archivo `/etc/crontab` contiene configuraciones relacionadas con las tareas programadas del sistema.
- No fue necesario modificar ningún archivo, solamente consultar el contenido de `/etc/crontab`.
- La flag se encontraba directamente dentro del archivo `crontab`.

## Referencias

- [OpenSSH](https://www.openssh.com/)
- [SSH Manual](https://man7.org/linux/man-pages/man1/ssh.1.html)
- [Cron](https://man7.org/linux/man-pages/man8/cron.8.html)
- [Crontab](https://man7.org/linux/man-pages/man5/crontab.5.html)
# Reto

## Descripción

Do you know how to move between directories and read files in the shell? Start the container, `ssh` to it, and then `ls` once connected to begin.

## Solución

### Solución 1

- Usando Linux y SSH.
- Primero nos conectamos al servidor mediante `ssh`.
- Después utilizamos `ls`, `cat` y `cd` para movernos entre directorios y encontrar las tres partes de la flag.
- Cada archivo contiene una parte de la flag y una indicación para encontrar la siguiente.

```bash
maxsteel05-picoctf@webshell:~$ ssh ctf-player@wily-courier.picoctf.net -p <PUERTO>
```

Una vez conectados, revisamos los archivos disponibles:

```bash
ctf-player@picoctf:~$ ls
1of3.flag.txt  instructions-to-2of3.txt
```

Leemos la primera parte de la flag:

```bash
ctf-player@picoctf:~$ cat 1of3.flag.txt
picoCTF{xxsh_
```

Después leemos las instrucciones:

```bash
ctf-player@picoctf:~$ cat instructions-to-2of3.txt
Next, go to the root of all things, more succinctly `/`
```

Nos movemos al directorio raíz:

```bash
ctf-player@picoctf:~$ cd /
ctf-player@picoctf:/$ ls
```

Buscamos y leemos la segunda parte:

```bash
ctf-player@picoctf:/$ cat 2of3.flag.txt
0ut_0f_//4t3r_
```

Después revisamos las instrucciones para encontrar la última parte:

```bash
ctf-player@picoctf:/$ cat instructions-to-3of3.txt
Lastly, ctf-player, go home... more succinctly `~`
```

Regresamos al directorio personal:

```bash
ctf-player@picoctf:/$ cd ~
ctf-player@picoctf:~$ ls
```

Finalmente leemos la tercera parte:

```bash
ctf-player@picoctf:~$ cat 3of3.flag.txt
0b24fc4f}
```

Juntamos las tres partes:

```text
picoCTF{xxsh_
0ut_0f_//4t3r_
0b24fc4f}
```

## Flag

`picoCTF{xxsh_0ut_0f_//4t3r_0b24fc4f}`

## Notas

- `ssh` permite conectarse de forma remota a otra computadora.
- `ls` muestra los archivos y carpetas del directorio actual.
- `cat` permite mostrar el contenido de un archivo.
- `cd` permite cambiar de directorio.
- `/` representa el directorio raíz del sistema.
- `~` representa el directorio personal del usuario.
- En este reto fue necesario encontrar tres archivos diferentes y concatenar su contenido para formar la flag completa.

## Referencias

- [OpenSSH](https://www.openssh.com/)
- [GNU Coreutils - ls](https://www.gnu.org/software/coreutils/manual/html_node/ls-invocation.html)
- [GNU Coreutils - cat](https://www.gnu.org/software/coreutils/manual/html_node/cat-invocation.html)
# Reto

## Descripción

En este reto de picoCTF se trabaja con **Git y control de versiones**. El archivo que contenía información importante fue modificado, pero gracias al historial de Git es posible consultar versiones anteriores y recuperar el contenido eliminado.

La descripción del reto indica:

> I accidentally wrote the flag down. Good thing I deleted it!

El archivo proporcionado para comenzar es:

```text
challenge.zip
```

### Pistas

1. El control de versiones puede ayudar a recuperar archivos que fueron modificados o eliminados.
2. Se recomienda revisar el apartado de Git del picoPrimer.
3. Los commits anteriores pueden ser inspeccionados para observar el contenido que existía antes.

## Solución

### Solución 1

Primero descargué el archivo del reto desde la terminal:

```bash
maxsteel05-academy@webshell:~$ wget https://artifacts.picoctf.net/c_titan/77/challenge.zip
```

Una vez terminada la descarga, descomprimí el archivo:

```bash
maxsteel05-academy@webshell:~$ unzip challenge.zip
```

Esto generó un directorio llamado `drop-in`, el cual contenía varios archivos internos pertenecientes a un repositorio Git.

Después entré al directorio:

```bash
maxsteel05-academy@webshell:~$ cd drop-in
```

Para revisar también los archivos ocultos utilicé:

```bash
maxsteel05-academy@webshell:~/drop-in$ ls -la
```

Entre los elementos encontrados apareció:

```text
.git
message.txt
```

La presencia del directorio `.git` indica que la carpeta conserva un historial de versiones.

Antes de revisar los commits consulté el archivo actual:

```bash
maxsteel05-academy@webshell:~/drop-in$ cat message.txt
```

El contenido actual era:

```text
TOP SECRET
```

Como la flag ya no se encontraba directamente en el archivo, revisé el historial de commits de Git:

```bash
maxsteel05-academy@webshell:~/drop-in$ git --no-pager log --oneline
```

En el historial aparecen dos cambios importantes:

```text
remove sensitive info
create flag
```

El commit llamado `remove sensitive info` corresponde a la versión donde se eliminó la información importante, mientras que `create flag` corresponde a una versión anterior donde todavía se encontraba la flag.

Para revisar el contenido de ese commit se puede utilizar:

```bash
maxsteel05-academy@webshell:~/drop-in$ git show 3d5ec8a26ee7b092a1760fea18f384c35e435139
```

Otra forma de hacerlo es cambiar directamente a la versión anterior:

```bash
maxsteel05-academy@webshell:~/drop-in$ git checkout 3d5ec8a26ee7b092a1760fea18f384c35e435139
```

Después se consulta nuevamente el archivo:

```bash
maxsteel05-academy@webshell:~/drop-in$ cat message.txt
```

De esta manera se recupera el contenido que había sido eliminado del archivo.

## FLAG

```text
picoCTF{s@n1t1z3_30e86d36}
```

## Notas

- Git conserva un historial de los cambios realizados dentro de un repositorio.
- El directorio oculto `.git` contiene la información necesaria para consultar versiones anteriores.
- `git log` permite revisar los commits realizados.
- La opción `--oneline` muestra cada commit de una manera más compacta.
- `git show` permite observar los cambios realizados en un commit específico.
- `git checkout` permite desplazarse a una versión anterior del repositorio.
- Aunque el contenido actual de `message.txt` era `TOP SECRET`, la flag todavía podía recuperarse desde el historial.
- Este reto demuestra que eliminar información de la versión actual de un proyecto no necesariamente la elimina del historial de Git.

## Referencias

- https://picoctf.org/
- https://webshell.picoctf.org/
- https://primer.picoctf.org/#_git_version_control
- https://git-scm.com/docs/git-log
- https://git-scm.com/docs/git-show
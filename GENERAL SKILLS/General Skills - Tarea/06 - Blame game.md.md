# Reto

## Descripción

En este reto se trabaja nuevamente con **Git**, pero ahora el objetivo es identificar quién realizó un cambio que provocó que un programa dejara de funcionar correctamente.

La descripción del reto indica:

> Someone's commits seems to be preventing the program from working. Who is it?

El archivo proporcionado para comenzar es:

```text
challenge.zip
```

### Pistas

1. En proyectos colaborativos muchos usuarios pueden realizar cambios. Es necesario encontrar una manera de consultar los cambios realizados específicamente sobre un archivo.
2. Se recomienda revisar el apartado de Git incluido en picoPrimer.
3. Se puede ejecutar el archivo con `python3 <archivo>.py` para comprobar su funcionamiento, aunque no es obligatorio para resolver el reto.

## Solución

### Solución 1

Primero descargué el archivo proporcionado por picoCTF utilizando `wget`:

```bash
maxsteel05-academy@webshell:~$ wget https://artifacts.picoctf.net/c_titan/57/challenge.zip
```

Después de finalizar la descarga, descomprimí el archivo:

```bash
maxsteel05-academy@webshell:~$ unzip challenge.zip
```

Al extraerlo se creó un directorio llamado:

```text
drop-in
```

Dentro de este directorio se encontraban los archivos del repositorio Git, incluyendo una gran cantidad de objetos pertenecientes al historial de versiones.

Después entré al directorio del reto:

```bash
maxsteel05-academy@webshell:~$ cd drop-in/
```

Para revisar el archivo de Python utilicé:

```bash
maxsteel05-academy@webshell:~/drop-in$ cat message.py
```

El contenido mostrado fue:

```python
print("Hello, World!"
```

Se puede observar que el programa tiene un error, ya que falta cerrar correctamente el paréntesis.

Como la descripción menciona que uno de los commits provocó el problema, revisé el historial correspondiente únicamente a `message.py`:

```bash
maxsteel05-academy@webshell:~/drop-in$ git log message.py
```

Este comando permite filtrar el historial de Git y mostrar únicamente los commits que realizaron cambios sobre `message.py`.

Al revisar los commits se puede identificar al usuario responsable del cambio que dañó el programa.

Otra opción especialmente útil para este reto es utilizar:

```bash
maxsteel05-academy@webshell:~/drop-in$ git blame message.py
```

`git blame` permite observar qué commit y qué autor modificaron cada línea de un archivo. Esto facilita localizar directamente quién realizó el cambio que produjo el error.

Al encontrar el commit responsable, el nombre del autor contiene la flag correspondiente al reto.

## FLAG

La flag se encuentra en la información del autor del commit responsable y tiene un formato similar a:

```text
picoCTF{@sk_th3_1nt3rn_XXXXXXXX}
```

No se deben sustituir los últimos caracteres por los de otra instancia del reto, ya que pueden ser diferentes. Para obtener la flag exacta se debe revisar la salida de:

```bash
git log message.py
```

o:

```bash
git blame message.py
```

## Notas

- El reto utiliza un repositorio Git con una gran cantidad de commits.
- El archivo principal que se debe analizar es `message.py`.
- El código encontrado contiene un error:

```python
print("Hello, World!"
```

- El problema está relacionado con uno de los cambios realizados anteriormente en el repositorio.
- `git log message.py` permite consultar solamente los commits relacionados con ese archivo.
- `git blame message.py` permite identificar quién modificó cada línea del archivo.
- El nombre del autor responsable del cambio contiene la flag.
- No es necesario revisar manualmente todos los archivos almacenados dentro de `.git`.
- Tampoco es necesario ejecutar todos los commits uno por uno.
- La gran cantidad de archivos mostrados al utilizar `unzip` pertenece principalmente al historial interno de Git.

## Referencias

- https://picoctf.org/
- https://webshell.picoctf.org/
- https://primer.picoctf.org/#_git_version_control
- https://git-scm.com/docs/git-log
- https://git-scm.com/docs/git-blame
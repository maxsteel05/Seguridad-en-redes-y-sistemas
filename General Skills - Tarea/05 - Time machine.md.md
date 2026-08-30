# Reto

## Descripción

En este reto se trabaja con **Git y el historial de commits**. La descripción menciona que se había escrito una nota para recordar en qué se estaba trabajando anteriormente.

La descripción del reto indica:

> What was I last working on? I remember writing a note to help me remember...

El archivo proporcionado para realizar el reto es:

```text
challenge.zip
```

### Pistas

1. El comando `cat` permite leer un archivo, pero en este caso eso por sí solo no será suficiente.
2. Se recomienda revisar el capítulo relacionado con Git en picoPrimer.
3. Al realizar un commit en Git se puede agregar un mensaje, y dicho mensaje puede contener información importante.

## Solución

### Solución 1

Primero descargué el archivo proporcionado por picoCTF utilizando `wget`:

```bash
maxsteel05-academy@webshell:~$ wget https://artifacts.picoctf.net/c_titan/67/challenge.zip
```

Una vez finalizada la descarga verifiqué que el archivo estuviera disponible:

```bash
maxsteel05-academy@webshell:~$ ls
```

Entre los archivos apareció:

```text
challenge.zip
```

Posteriormente descomprimí el archivo:

```bash
maxsteel05-academy@webshell:~$ unzip challenge.zip
```

El contenido se extrajo dentro de una carpeta llamada:

```text
drop-in
```

Además de `message.txt`, dentro de la carpeta también se encontraba el directorio oculto `.git`, lo cual indicaba que se trataba de un repositorio Git.

Primero intenté consultar directamente el archivo `message.txt`:

```bash
maxsteel05-academy@webshell:~$ cat drop-in/message.txt
```

La terminal mostró:

```text
This is what I was working on, but I'd need to look at my commit history to know why...
```

Este mensaje daba una pista directa de que era necesario revisar el historial de commits.

Después entré en el directorio del repositorio:

```bash
maxsteel05-academy@webshell:~$ cd drop-in
```

Una vez dentro utilicé el comando:

```bash
maxsteel05-academy@webshell:~/drop-in$ git log
```

El historial mostró un commit similar al siguiente:

```text
commit b92bdd8ec17b021ba45c77bc7bead8a4f231fafd (HEAD -> master)
Author: picoCTF <ops@picoctf.com>
Date:   Sat Mar 9 21:10:29 2024 +0000
```

Debajo de la información del commit apareció el mensaje utilizado al guardar esa versión del repositorio.

En este caso, el mensaje del commit contenía directamente la flag:

```text
picoCTF{t1m3m@ch1n3_5cde9075}
```

Por lo tanto, no era necesario recuperar versiones anteriores ni modificar los archivos, ya que la información buscada estaba almacenada en el propio mensaje del commit.

## FLAG

```text
picoCTF{t1m3m@ch1n3_5cde9075}
```

## Notas

- Un repositorio Git guarda información sobre los cambios realizados en un proyecto.
- La carpeta `.git` indica que el directorio pertenece a un repositorio de Git.
- `cat` permitió leer `message.txt`, pero la flag no estaba directamente dentro de ese archivo.
- El propio mensaje de `message.txt` indicaba que debía revisarse el historial de commits.
- El comando `git log` muestra los commits realizados en el repositorio.
- Cada commit puede incluir información como:
  - Hash del commit.
  - Autor.
  - Fecha.
  - Mensaje del commit.
- En este reto la flag estaba escrita directamente como el mensaje de un commit.
- Este reto demuestra que los mensajes de los commits también forman parte del historial de Git y pueden contener información útil.

## Referencias

- https://picoctf.org/
- https://webshell.picoctf.org/
- https://primer.picoctf.org/#_git_version_control
- https://git-scm.com/docs/git-log
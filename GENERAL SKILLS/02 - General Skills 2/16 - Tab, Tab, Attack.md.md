# Reto

## Descripción

Using tabcomplete in the Terminal will add years to your life, esp. when dealing with long rambling directory structures and filenames: `Addadshashanammu.zip`

## Solución

### Solución 1

- Usando Linux.
- Primero descargamos y descomprimimos el archivo `.zip`.
- Después utilizamos la tecla `Tab` para autocompletar los nombres de las carpetas y avanzar por la estructura de directorios.
- Al llegar al último archivo, comprobamos qué tipo de archivo es y finalmente lo ejecutamos para obtener la flag.

Primero descargamos el archivo:

```bash
maxsteel05-picoctf@webshell:~$ wget <URL_DEL_ARCHIVO>
```

Después descomprimimos el archivo:

```bash
maxsteel05-picoctf@webshell:~$ unzip Addadshashanammu.zip
```

Entramos a la carpeta:

```bash
maxsteel05-picoctf@webshell:~$ cd Addadshashanammu
```

Utilizamos `ls`, `cd` y la tecla `Tab` para avanzar por las carpetas:

```bash
maxsteel05-picoctf@webshell:~/Addadshashanammu$ ls
Almurbalarammi

maxsteel05-picoctf@webshell:~/Addadshashanammu$ cd Almurbalarammi/
maxsteel05-picoctf@webshell:~/Addadshashanammu/Almurbalarammi$ ls
Ashalmimilkala
```

Continuamos utilizando `Tab` hasta llegar al último archivo:

```text
Addadshashanammu/
└── Almurbalarammi/
    └── Ashalmimilkala/
        └── Assurnabitashpi/
            └── Maelkashishi/
                └── Onnissiralis/
                    └── Ularradallaku/
                        └── fang-of-haynekhtnamet
```

Comprobamos el tipo de archivo:

```bash
maxsteel05-picoctf@webshell:~$ file fang-of-haynekhtnamet
fang-of-haynekhtnamet: ELF 64-bit LSB pie executable, x86-64
```

Finalmente ejecutamos el archivo:

```bash
maxsteel05-picoctf@webshell:~$ ./fang-of-haynekhtnamet
*ZAP!* picoCTF{l3v3l_up!_t4k3_4_r35t!_fc58427}
```

## Flag

`picoCTF{l3v3l_up!_t4k3_4_r35t!_fc58427}`

## Notas

- La tecla `Tab` permite autocompletar nombres de archivos y carpetas en la terminal.
- Esto es especialmente útil cuando los nombres de las carpetas son muy largos.
- `unzip` permite descomprimir archivos `.zip`.
- `ls` muestra el contenido de una carpeta.
- `cd` permite cambiar de directorio.
- `file` permite identificar el tipo de un archivo.
- `./` permite ejecutar un archivo que se encuentra en el directorio actual.

## Referencias

- [GNU Bash](https://www.gnu.org/software/bash/)
- [Info-ZIP](https://infozip.sourceforge.net/)
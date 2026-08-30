# Reto

## Descripción

En este reto se trabaja con **ramas de Git**. El programa encargado de imprimir la flag fue desarrollado de manera colaborativa, por lo que distintas partes del código quedaron distribuidas en varias ramas del repositorio.

La descripción del reto indica:

> My team has been working very hard on new features for our flag printing program! I wonder how they'll work together?

El archivo proporcionado para comenzar es:

```text
challenge.zip
```

### Pistas

1. El comando `git branch -a` permite observar todas las ramas disponibles dentro de un repositorio.
2. Los cambios realizados en diferentes ramas pueden integrarse utilizando `git merge`.
3. Los conflictos de Git pueden resolverse manualmente utilizando un editor de texto.

## Solución

### Solución 1

Primero descargué el archivo del reto utilizando PowerShell:

```powershell
PS C:\Users\max> wget https://artifacts.picoctf.net/c_titan/71/challenge.zip
```

Debido a que PowerShell utiliza `wget` como alias de `Invoke-WebRequest`, posteriormente descargué el archivo especificando directamente el nombre de salida:

```powershell
PS C:\Users\max> Invoke-WebRequest -Uri "https://artifacts.picoctf.net/c_titan/71/challenge.zip" -OutFile "challenge.zip"
```

Después verifiqué que el archivo estuviera correctamente descargado:

```powershell
PS C:\Users\max> dir challenge.zip
```

Luego descomprimí el archivo:

```powershell
PS C:\Users\max> Expand-Archive -Path .\challenge.zip -DestinationPath .\challenge
```

Entré en la carpeta generada:

```powershell
PS C:\Users\max> cd .\challenge
```

Dentro se encontraba el directorio:

```text
drop-in
```

Ingresé al repositorio:

```powershell
PS C:\Users\max\challenge> cd .\drop-in
```

Para revisar el estado actual de Git ejecuté:

```powershell
PS C:\Users\max\challenge\drop-in> git status
```

La salida indicó que me encontraba en la rama:

```text
main
```

Después utilicé el siguiente comando para visualizar todas las ramas disponibles:

```powershell
PS C:\Users\max\challenge\drop-in> git branch -a
```

Se mostraron las siguientes ramas:

```text
feature/part-1
feature/part-2
feature/part-3
main
```

Esto indicó que el programa había sido dividido en tres ramas diferentes.

En lugar de cambiar de rama una por una, utilicé `git show` para consultar directamente el contenido del archivo `flag.py` en cada rama.

Primero revisé la rama `feature/part-1`:

```powershell
PS C:\Users\max\challenge\drop-in> git show feature/part-1:flag.py
```

La salida mostró:

```python
print("Printing the flag...")
print("picoCTF{t3@mw0rk_", end='')
```

Esta era la primera parte de la flag:

```text
picoCTF{t3@mw0rk_
```

Después consulté la segunda rama:

```powershell
PS C:\Users\max\challenge\drop-in> git show feature/part-2:flag.py
```

La salida fue:

```python
print("Printing the flag...")
print("m@k3s_th3_dr3@m_", end='')
```

La segunda parte era:

```text
m@k3s_th3_dr3@m_
```

Finalmente revisé la tercera rama:

```powershell
PS C:\Users\max\challenge\drop-in> git show feature/part-3:flag.py
```

La salida mostró:

```python
print("Printing the flag...")
print("w0rk_4c24302f}")
```

La última parte era:

```text
w0rk_4c24302f}
```

Finalmente uní las tres partes encontradas:

```text
picoCTF{t3@mw0rk_
m@k3s_th3_dr3@m_
w0rk_4c24302f}
```

Al concatenarlas se obtiene la flag completa.

## FLAG

```text
picoCTF{t3@mw0rk_m@k3s_th3_dr3@m_w0rk_4c24302f}
```

## Notas

- Git permite trabajar con diferentes versiones de un proyecto utilizando ramas.
- `git branch -a` muestra las ramas locales y remotas disponibles.
- En este reto existían tres ramas importantes:

```text
feature/part-1
feature/part-2
feature/part-3
```

- Cada una de estas ramas contenía una sección diferente de la flag.
- No fue necesario cambiar constantemente entre las ramas.
- La sintaxis:

```bash
git show rama:archivo
```

permite consultar directamente el contenido de un archivo que se encuentra en otra rama.

- En este caso se utilizó:

```bash
git show feature/part-1:flag.py
git show feature/part-2:flag.py
git show feature/part-3:flag.py
```

- Después únicamente fue necesario unir las tres cadenas en el orden correcto.
- Este reto demuestra cómo distintas partes de un proyecto pueden desarrollarse simultáneamente utilizando ramas de Git.

## Referencias

- https://picoctf.org/
- https://webshell.picoctf.org/
- https://primer.picoctf.org/#_git_version_control
- https://git-scm.com/docs/git-branch
- https://git-scm.com/docs/git-show
- https://git-scm.com/docs/git-merge
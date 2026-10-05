## Descripción

## Solución

```
┌──(kali㉿kali)-[~]
└─$ ls
Desktop    fixme1         hash     pico_img.png  shell          Templates
Documents  fixme1.tar.gz  Music    Pictures      shell.php      Videos
Downloads  garden.jpg     picoctf  Public        shell.png.php
   
┌──(kali㉿kali)-[~]
└─$ string garden.jpg |grep pico
Command 'string' not found, did you mean:
  command 'spring' from deb ruby-spring
  command 'strings' from deb binutils
Try: sudo apt install <deb name>
      
┌──(kali㉿kali)-[~]
└─$ strings garden.jpg \         
> 
> ={~5
h--@3
cZi-
M(.I
]hWP&
jc#k
=7g&
mjx/
s\]|."Ue
\qZf
Here is a flag: picoCTF{more_than_m33ts_the_3y339140129}
   
┌──(kali㉿kali)-[~]
└─$ 

```

picoCTF{more_than_m33ts_the_3y339140129}

## Notas
`strings` extrae cualquier secuencia de caracteres que parezca texto.

## Referencias

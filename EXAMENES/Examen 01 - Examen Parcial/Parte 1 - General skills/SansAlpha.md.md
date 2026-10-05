## Descripción

[](https://github.com/neylar-11/notas-hacking-EneJun26/blob/main/picoCTF/Examen1/General%20Skills/9%20-%20SansAlpha.md#descripci%C3%B3n)

The Multiverse is within your grasp! Unfortunately, the server that contains the secrets of the multiverse is in a universe where keyboards only have numbers and (most) symbols.`ssh -p 49854 ctf-player@mimas.picoctf.net`Use password: `6dd28e9b`

## Solución

[](https://github.com/neylar-11/notas-hacking-EneJun26/blob/main/picoCTF/Examen1/General%20Skills/9%20-%20SansAlpha.md#soluci%C3%B3n)

### Solucion

[](https://github.com/neylar-11/notas-hacking-EneJun26/blob/main/picoCTF/Examen1/General%20Skills/9%20-%20SansAlpha.md#solucion)

```
┌──(kali㉿kali)-[~/picoctf/examen1/SansAlpha]
└─$ ssh -p 49854 ctf-player@mimas.picoctf.net
** WARNING: connection is not using a post-quantum key exchange algorithm.
** This session may be vulnerable to "store now, decrypt later" attacks.
** The server may need to be upgraded. See https://openssh.com/pq.html
ctf-player@mimas.picoctf.net's password: 
Welcome to Ubuntu 20.04.3 LTS (GNU/Linux 6.5.0-1016-aws x86_64)

 * Documentation:  https://help.ubuntu.com
 * Management:     https://landscape.canonical.com
 * Support:        https://ubuntu.com/advantage

This system has been minimized by removing packages and content that are
not required on a system that users do not log into.

To restore this content, you can run the 'unminimize' command.
Last login: Sat Mar 14 01:53:26 2026 from 127.0.0.1
SansAlpha$ ./*
bash: ./blargh: Is a directory

SansAlpha$ ./*/*
bash: ./blargh/flag.txt: Permission denied

SansAlpha$ /?????
bash: /lib32: Is a directory

SansAlpha$ /???/??????
/bin/base32: extra operand '/bin/base64'
Try '/bin/base32 --help' for more information.

SansAlpha$ /???/???[!_]64 /????/??????????/??????/????????
cmV0dXJuIDAgcGljb0NURns3aDE1X211MTcxdjNyNTNfMTVfbTRkbjM1NV8xNDUyNTZlY30=

SansAlpha$ NURns3aDE1X211MTcxdjNyNTNfMTVfbTRkbjM1NV8xNDUyNTZlY30=
SansAlpha: Unknown character detected
SansAlpha$ 
zsh: corrupt history file /home/kali/.zsh_history
┌──(kali㉿kali)-[~/picoctf/examen1/SansAlpha]
└─$ echo "cmV0dXJuIDAgcGljb0NURns3aDE1X211MTcxdjNyNTNfMTVfbTRkbjM1NV8xNDUyNTZlY30=" | base64 -d
return 0 picoCTF{7h15_mu171v3r53_15_m4dn355_145256ec}                                                                                   
┌──(kali㉿kali)-[~/picoctf/examen1/SansAlpha]
└─$ 

```

picoCTF{7h15_mu171v3r53_15_m4dn355_145256ec}

## Notas

[](https://github.com/neylar-11/notas-hacking-EneJun26/blob/main/picoCTF/Examen1/General%20Skills/9%20-%20SansAlpha.md#notas)

## Referencias
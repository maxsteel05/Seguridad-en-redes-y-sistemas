## Descripción
There's something in the [building](https://challenge-files.cylabacademy.net/library/5235bfccd8f3cc2d059ee828f774846542f28f7ec66cb4f0c6ceb536c38026d4/buildings.png). Can you retrieve the flag?
1.- There is data encoded somewhere... there might be an online decoder.
## Solución

```
┌──(kali㉿kali)-[~/picoctf/forensic]
└─$ cd whatlies

┌──(kali㉿kali)-[~/picoctf/forensic/whatlies]
└─$ wget https://challenge-files.picoctf.net/c_fickle_tempest/c0eec6af0f04316e2bdc4a9f095afd0e2d0121f5e543dbc4a65bb0038d72a993/buildings.png
--2026-03-09 10:57:22--  https://challenge-files.picoctf.net/c_fickle_tempest/c0eec6af0f04316e2bdc4a9f095afd0e2d0121f5e543dbc4a65bb0038d72a993/buildings.png
Resolving challenge-files.picoctf.net (challenge-files.picoctf.net)... 18.154.206.118, 18.154.206.121, 18.154.206.27, ...
Connecting to challenge-files.picoctf.net (challenge-files.picoctf.net)|18.154.206.118|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 625219 (611K) [application/octet-stream]
Saving to: ‘buildings.png’

buildings.png                                              100%[===========================================================================================================

2026-03-09 10:57:24 (606 KB/s) - ‘buildings.png’ saved [625219/625219]

┌──(kali㉿kali)-[~/picoct
```

picoCTF{h1d1ng_1n_th3_b1t5}

## Notas

![[Pasted image 20260309090038.png]]

## Referencias
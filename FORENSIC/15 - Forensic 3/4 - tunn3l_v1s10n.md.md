## Descripción

We found this file. Recover the flag.[tunn3l_v1s10n](https://challenge-files.picoctf.net/c_wily_courier/626df9feed926c1e1280804f5d87fde5576e266ff250a819a5528b0471b0f3f7/tunn3l_v1s10n)

### Solucion

```
┌──(kali㉿kali)-[~/picoctf/forensic3/tunn3l]
└─$ wget https://challenge-files.picoctf.net/c_wily_courier/626df9feed926c1e1280804f5d87fde5576e266ff250a819a5528b0471b0f3f7/tunn3l_v1s10n
--2026-03-18 10:42:25--  https://challenge-files.picoctf.net/c_wily_courier/626df9feed926c1e1280804f5d87fde5576e266ff250a819a5528b0471b0f3f7/tunn3l_v1s10n
Resolving challenge-files.picoctf.net (challenge-files.picoctf.net)... 18.154.206.118, 18.154.206.121, 18.154.206.27, ...
Connecting to challenge-files.picoctf.net (challenge-files.picoctf.net)|18.154.206.118|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 2893454 (2.8M) [application/octet-stream]
Saving to: ‘tunn3l_v1s10n’

tunn3l_v1s10n                             100%[=====================================================================================>]   2.76M  1.59MB/s    in 1.7s    

2026-03-18 10:42:28 (1.59 MB/s) - ‘tunn3l_v1s10n’ saved [2893454/2893454]

┌──(kali㉿kali)-[~/picoctf/forensic3/tunn3l]
└─$ ls
tunn3l_v1s10n

┌──(kali㉿kali)-[~/picoctf/forensic3/tunn3l]
└─$ open tunn3l_v1s10n      
       
┌──(kali㉿kali)-[~/picoctf/forensic3/tunn3l]
└─$ hexeditor tunn3l_v1s10n             

┌──(kali㉿kali)-[~/picoctf/forensic3/tunn3l]
└─$ picoCTF{qu1t3_a_v13w_2020}

```

picoCTF{qu1t3_a_v13w_2020}

## Notas

## Referencias
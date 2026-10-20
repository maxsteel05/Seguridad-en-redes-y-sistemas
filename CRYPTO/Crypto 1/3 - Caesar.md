## Descripción
Decrypt this message.Message: [message](https://challenge-files.picoctf.net/c_fickle_tempest/bfd7c036228a50ff9e76dfc29ac6cec116f209f0db26506497997f0aca083105/data.enc)

## Solución

```
┌──(kali㉿kali)-[~/picoctf/crypto/caesar]
└─$ wget https://challenge-files.picoctf.net/c_fickle_tempest/bfd7c036228a50ff9e76dfc29ac6cec116f209f0db26506497997f0aca083105/data.enc
--2026-04-13 15:46:53--  https://challenge-files.picoctf.net/c_fickle_tempest/bfd7c036228a50ff9e76dfc29ac6cec116f209f0db26506497997f0aca083105/data.enc
Resolving challenge-files.picoctf.net (challenge-files.picoctf.net)... 3.174.207.125, 3.174.207.109, 3.174.207.96, ...
Connecting to challenge-files.picoctf.net (challenge-files.picoctf.net)|3.174.207.125|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 36 [application/octet-stream]
Saving to: ‘data.enc’

data.enc                                  100%[=====================================================================================>]      36  --.-KB/s    in 0.001s  

2026-04-13 15:46:54 (40.1 KB/s) - ‘data.enc’ saved [36/36]



┌──(kali㉿kali)-[~/picoctf/crypto/caesar]
└─$ cat data.enc
picoCTF{dspttjohuifsvcjdpohatwvibg}

```

- cyberchef: [https://gchq.github.io/CyberChef/#recipe=ROT13(true,true,false,25)&input=ZHNwdHRqb2h1aWZzdmNqZHBvaGF0d3ZpYmc](https://gchq.github.io/CyberChef/#recipe=ROT13\(true,true,false,25\)&input=ZHNwdHRqb2h1aWZzdmNqZHBvaGF0d3ZpYmc) picoCTF{crossingtherubicongzsvuhaf}

## Notas

## Referencias
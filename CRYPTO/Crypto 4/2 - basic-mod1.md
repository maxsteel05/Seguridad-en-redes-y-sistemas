## Descripción

We found this weird message being passed around on the servers, we think we have a working decryption scheme.Download the message [here](https://artifacts.picoctf.net/c/127/message.txt).Take each number mod 37 and map it to the following character set: 0-25 is the alphabet (uppercase), 26-35 are the decimal digits, and 36 is an underscore.Wrap your decrypted message in the picoCTF flag format (i.e. `picoCTF{decrypted_message}`)

## Solución

```
┌──(kali㉿kali)-[~/picoctf/cripto4/basic-mod1]
└─$ wget https://artifacts.picoctf.net/c/127/message.txt                                                                                   
--2026-04-22 15:26:11--  https://artifacts.picoctf.net/c/127/message.txt
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.161.55.100, 3.161.55.61, 3.161.55.26, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.161.55.100|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 85 [application/octet-stream]
Saving to: ‘message.txt’

message.txt                               100%[===================================================================================>]      85  --.-KB/s    in 0s      

2026-04-22 15:26:11 (2.58 MB/s) - ‘message.txt’ saved [85/85]

                                                                                                                                                                      
┌──(kali㉿kali)-[~/picoctf/cripto4/basic-mod1]
└─$ ls
message.txt
                                                                                                                                                                      
┌──(kali㉿kali)-[~/picoctf/cripto4/basic-mod1]
└─$ cat message.txt
128 322 353 235 336 73 198 332 202 285 57 87 262 221 218 405 335 101 256 227 112 140                                                                                                                                                                       
┌──(kali㉿kali)-[~/picoctf/cripto4/basic-mod1]
└─$ nano exp.py
                                                                                                                                                                      
┌──(kali㉿kali)-[~/picoctf/cripto4/basic-mod1]
└─$ python3 exp.py
  File "/home/kali/picoctf/cripto4/basic-mod1/exp.py", line 1
    datos - open( message. txt') . read( ) . split( )
                              ^
SyntaxError: unterminated string literal (detected at line 1)
                                                                                                                                                                      
┌──(kali㉿kali)-[~/picoctf/cripto4/basic-mod1]
└─$ nano exp.py   
                                                                                                                                                                      
┌──(kali㉿kali)-[~/picoctf/cripto4/basic-mod1]
└─$ python3 exp.py
  File "/home/kali/picoctf/cripto4/basic-mod1/exp.py", line 6
        if c ≥ 0 and c ≤ 25:
             ^
SyntaxError: invalid character '≥' (U+2265)
                                                                                                                                                                      
┌──(kali㉿kali)-[~/picoctf/cripto4/basic-mod1]
└─$ nano exp.py   
                                                                                                                                                                      
┌──(kali㉿kali)-[~/picoctf/cripto4/basic-mod1]
└─$ python3 exp.py
  File "/home/kali/picoctf/cripto4/basic-mod1/exp.py", line 6
        if c > 0 and c ≤ 25:
                       ^
SyntaxError: invalid character '≤' (U+2264)
                                                                                                                                                                      
┌──(kali㉿kali)-[~/picoctf/cripto4/basic-mod1]
└─$ nano exp.py   
                                                                                                                                                                      
┌──(kali㉿kali)-[~/picoctf/cripto4/basic-mod1]
└─$ python3 exp.py
Traceback (most recent call last):
  File "/home/kali/picoctf/cripto4/basic-mod1/exp.py", line 1, in <module>
    datos - open('message. txt') . read( ) . split( )
    ^^^^^
NameError: name 'datos' is not defined
                                                                                                                                                                      
┌──(kali㉿kali)-[~/picoctf/cripto4/basic-mod1]
└─$ nano exp.py   
                                                                                                                                                                      
┌──(kali㉿kali)-[~/picoctf/cripto4/basic-mod1]
└─$ nano exp.py
                                                                                                                                                                      
┌──(kali㉿kali)-[~/picoctf/cripto4/basic-mod1]
└─$ python3 exp.py
Traceback (most recent call last):
  File "/home/kali/picoctf/cripto4/basic-mod1/exp.py", line 1, in <module>
    datos = open('message. txt') . read( ) . split( )
            ~~~~^^^^^^^^^^^^^^^^
FileNotFoundError: [Errno 2] No such file or directory: 'message. txt'
                                                                                                                                                                      
┌──(kali㉿kali)-[~/picoctf/cripto4/basic-mod1]
└─$ nano exp.py   
                                                                                                                                                                      
┌──(kali㉿kali)-[~/picoctf/cripto4/basic-mod1]
└─$ python3 exp.py
['128', '322', '353', '235', '336', '73', '198', '332', '202', '285', '57', '87', '262', '221', '218', '405', '335', '101', '256', '227', '112', '140']
Traceback (most recent call last):
  File "/home/kali/picoctf/cripto4/basic-mod1/exp.py", line 12, in <module>
    flag += s
    ^^^^
NameError: name 'flag' is not defined. Did you mean: 'float'?
                                                                                                                                                                      
┌──(kali㉿kali)-[~/picoctf/cripto4/basic-mod1]
└─$ nano exp.py   
                                                                                                                                                                      
┌──(kali㉿kali)-[~/picoctf/cripto4/basic-mod1]
└─$ nano exp.py
                                                                                                                                                                      
┌──(kali㉿kali)-[~/picoctf/cripto4/basic-mod1]
└─$ python3 exp.py
['128', '322', '353', '235', '336', '73', '198', '332', '202', '285', '57', '87', '262', '221', '218', '405', '335', '101', '256', '227', '112', '140']
picoCTF{R0UND_N_R0UND_79C18FB3}

```

picoCTF{R0UND_N_R0UND_79C18FB3}

## Notas

## Referencias
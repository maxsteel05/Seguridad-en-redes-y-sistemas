## Descripción
I stopped using YellowPages and moved onto WhitePages... but [the page they gave me](https://challenge-files.picoctf.net/c_fickle_tempest/bdd421d396847b0b8c86a2bc0c86331a18e2f9191b961b162f7c6379a4ca94be/whitepages.txt) is all blank!

## Solución

```
┌──(kali㉿kali)-[~/picoctf/forensic2/WhitePages]
└─$ wget https://challenge-files.picoctf.net/c_fickle_tempest/bdd421d396847b0b8c86a2bc0c86331a18e2f9191b961b162f7c6379a4ca94be/whitepages.txt
--2026-03-11 19:07:46--  https://challenge-files.picoctf.net/c_fickle_tempest/bdd421d396847b0b8c86a2bc0c86331a18e2f9191b961b162f7c6379a4ca94be/whitepages.txt
Resolving challenge-files.picoctf.net (challenge-files.picoctf.net)... 3.161.44.61, 3.161.44.103, 3.161.44.22, ...
Connecting to challenge-files.picoctf.net (challenge-files.picoctf.net)|3.161.44.61|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 2774 (2.7K) [application/octet-stream]
Saving to: ‘whitepages.txt’

whitepages.txt                             100%[=======================================================================================>]   2.71K  --.-KB/s    in 0s      

2026-03-11 19:07:47 (22.5 MB/s) - ‘whitepages.txt’ saved [2774/2774]

┌──(kali㉿kali)-[~/picoctf/forensic2/WhitePages]
└─$ ls -al
total 12
drwxrwxr-x 2 kali kali 4096 Mar 11 19:07 .
drwxrwxr-x 4 kali kali 4096 Mar 11 19:07 ..
-rw-rw-r-- 1 kali kali 2774 Nov 14 14:58 whitepages.txt

┌──(kali㉿kali)-[~/picoctf/forensic2/WhitePages]
└─$ file whitepages.txt
whitepages.txt: Unicode text, UTF-8 text, with very long lines (1296), with no line terminators

┌──(kali㉿kali)-[~/picoctf/forensic2/WhitePages]
└─$ xxd whitepages | head
xxd: whitepages: No such file or directory

┌──(kali㉿kali)-[~/picoctf/forensic2/WhitePages]
└─$ xxd whitepages |head 
xxd: whitepages: No such file or directory

┌──(kali㉿kali)-[~/picoctf/forensic2/WhitePages]
└─$ xxd whitepages.txt |head
00000000: e280 83e2 8083 e280 83e2 8083 20e2 8083  ............ ...
00000010: 20e2 8083 e280 8320 2020 e280 83e2 8083   ......   ......
00000020: e280 83e2 8083 e280 8320 20e2 8083 20e2  .........  ... .
00000030: 8083 e280 8320 e280 8320 20e2 8083 e280  ..... ...  .....
00000040: 83e2 8083 2020 e280 8320 20e2 8083 2020  ....  ...  ...  
00000050: 2020 e280 8320 e280 83e2 8083 e280 83e2    ... ..........
00000060: 8083 2020 e280 8320 e280 8320 e280 8320  ..  ... ... ... 
00000070: e280 83e2 8083 e280 8320 e280 83e2 8083  ......... ......
00000080: e280 8320 20e2 8083 e280 83e2 8083 e280  ...  ...........
00000090: 83e2 8083 20e2 8083 20e2 8083 e280 83e2  .... ... .......

┌──(kali㉿kali)-[~/picoctf/forensic2/WhitePages]
└─$ python3 -c 'import pwntools'
Traceback (most recent call last):
  File "<string>", line 1, in <module>
    import pwntools
ModuleNotFoundError: No module named 'pwntools'

┌──(kali㉿kali)-[~/picoctf/forensic2/WhitePages]
└─$ python3 -m pip install pwntools
error: externally-managed-environment

× This environment is externally managed
╰─> To install Python packages system-wide, try apt install
    python3-xyz, where xyz is the package you are trying to
    install.
    
    If you wish to install a non-Kali-packaged Python package,
    create a virtual environment using python3 -m venv path/to/venv.
    Then use path/to/venv/bin/python and path/to/venv/bin/pip. Make
    sure you have pypy3-venv installed.
    
    If you wish to install a non-Kali-packaged Python application,
    it may be easiest to use pipx install xyz, which will manage a
    virtual environment for you. Make sure you have pipx installed.
    
    For more information, refer to the following:
    * https://www.kali.org/docs/general-use/python3-external-packages/
    * /usr/share/doc/python3.13/README.venv

note: If you believe this is a mistake, please contact your Python installation or OS distribution provider. You can override this, at the risk of breaking your Python installation or OS, by passing --break-system-packages.
hint: See PEP 668 for the detailed specification.

┌──(kali㉿kali)-[~/picoctf/forensic2/WhitePages]
└─$ sudo apt install python3-pwntools
[sudo] password for kali: 
The following package was automatically installed and is no longer required:
  libcrypt-dev
Use 'sudo apt autoremove' to remove it.

┌──(kali㉿kali)-[~/picoctf/forensic2/WhitePages]
└─$ python3 -c 'import pwntools'   
Traceback (most recent call last):
  File "<string>", line 1, in <module>
    import pwntools
ModuleNotFoundError: No module named 'pwntools'

┌──(kali㉿kali)-[~/picoctf/forensic2/WhitePages]
└─$ python3                     
Python 3.13.9 (main, Oct 15 2025, 14:56:22) [GCC 15.2.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> from pwn import *
>>> 
>>> zsh: suspended (signal)  python3

┌──(kali㉿kali)-[~/picoctf/forensic2/WhitePages]
└─$ nano exp.py                        

┌──(kali㉿kali)-[~/picoctf/forensic2/WhitePages]
└─$ python3 exp.py              
b'\npicoCTF\n\nSEE PUBLIC RECORDS & BACKGROUND REPORT\n5000 Forbes Ave, Pittsburgh, PA 15213\npicoCTF{not_all_spaces_are_created_equal_aa90f80c1cebc20be3564d2f96a9726c}\n'
  
```

picoCTF{not_all_spaces_are_created_equal_aa90f80c1cebc20be3564d2f96a9726c}

## Notas

## Referencias
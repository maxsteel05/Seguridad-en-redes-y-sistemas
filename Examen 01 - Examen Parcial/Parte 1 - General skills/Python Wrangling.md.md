## Descripción

[](https://github.com/neylar-11/notas-hacking-EneJun26/blob/main/picoCTF/Examen1/General%20Skills/8%20-%20Python%20Wrangling.md#descripci%C3%B3n)

Python scripts are invoked kind of like programs in the Terminal...Can you run [ende.py](https://challenge-files.picoctf.net/c_wily_courier/a4c97b512a4e6de24045ab3e8294651bcfc241ce571daa8afdad3c35885ffa60/ende.py) using [password.txt](https://challenge-files.picoctf.net/c_wily_courier/a4c97b512a4e6de24045ab3e8294651bcfc241ce571daa8afdad3c35885ffa60/password.txt) to get [flag.txt.en](https://challenge-files.picoctf.net/c_wily_courier/a4c97b512a4e6de24045ab3e8294651bcfc241ce571daa8afdad3c35885ffa60/flag.txt.en)?

## Solución

[](https://github.com/neylar-11/notas-hacking-EneJun26/blob/main/picoCTF/Examen1/General%20Skills/8%20-%20Python%20Wrangling.md#soluci%C3%B3n)

### Solucion

[](https://github.com/neylar-11/notas-hacking-EneJun26/blob/main/picoCTF/Examen1/General%20Skills/8%20-%20Python%20Wrangling.md#solucion)

```
┌──(kali㉿kali)-[~/picoctf/examen1/Python_Wrangling]
└─$ wget https://challenge-files.picoctf.net/c_wily_courier/a4c97b512a4e6de24045ab3e8294651bcfc241ce571daa8afdad3c35885ffa60/flag.txt.en 
--2026-03-13 21:41:35--  https://challenge-files.picoctf.net/c_wily_courier/a4c97b512a4e6de24045ab3e8294651bcfc241ce571daa8afdad3c35885ffa60/flag.txt.en
Resolving challenge-files.picoctf.net (challenge-files.picoctf.net)... 18.154.206.27, 18.154.206.14, 18.154.206.118, ...
Connecting to challenge-files.picoctf.net (challenge-files.picoctf.net)|18.154.206.27|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 140 [application/octet-stream]
Saving to: ‘flag.txt.en’

flag.txt.en                               100%[=====================================================================================>]     140  --.-KB/s    in 0s      

2026-03-13 21:41:35 (53.8 MB/s) - ‘flag.txt.en’ saved [140/140]
   
┌──(kali㉿kali)-[~/picoctf/examen1/Python_Wrangling]
└─$ ls             
ende.py  flag.txt.en  password.txt

┌──(kali㉿kali)-[~/picoctf/examen1/Python_Wrangling]
└─$ file ende.py   
ende.py: Python script, ASCII text executable

┌──(kali㉿kali)-[~/picoctf/examen1/Python_Wrangling]
└─$ cat ende.py          

import sys
import base64
from cryptography.fernet import Fernet



usage_msg = "Usage: "+ sys.argv[0] +" (-e/-d) [file]"
help_msg = usage_msg + "\n" +\
        "Examples:\n" +\
        "  To decrypt a file named 'pole.txt', do: " +\
        "'$ python "+ sys.argv[0] +" -d pole.txt'\n"



if len(sys.argv) < 2 or len(sys.argv) > 4:
    print(usage_msg)
    sys.exit(1)



if sys.argv[1] == "-e":
    if len(sys.argv) < 4:
        sim_sala_bim = input("Please enter the password:")
    else:
        sim_sala_bim = sys.argv[3]

    ssb_b64 = base64.b64encode(sim_sala_bim.encode())
    c = Fernet(ssb_b64)

    with open(sys.argv[2], "rb") as f:
        data = f.read()
        data_c = c.encrypt(data)
        sys.stdout.write(data_c.decode())


elif sys.argv[1] == "-d":
    if len(sys.argv) < 4:
        sim_sala_bim = input("Please enter the password:")
    else:
        sim_sala_bim = sys.argv[3]

    ssb_b64 = base64.b64encode(sim_sala_bim.encode())
    c = Fernet(ssb_b64)

    with open(sys.argv[2], "r") as f:
        data = f.read()
        data_c = c.decrypt(data.encode())
        sys.stdout.buffer.write(data_c)


elif sys.argv[1] == "-h" or sys.argv[1] == "--help":
    print(help_msg)
    sys.exit(1)


else:
    print("Unrecognized first argument: "+ sys.argv[1])
    print("Please use '-e', '-d', or '-h'.")
   
┌──(kali㉿kali)-[~/picoctf/examen1/Python_Wrangling]
└─$ ls
ende.py  flag.txt.en  password.txt
     
┌──(kali㉿kali)-[~/picoctf/examen1/Python_Wrangling]
└─$ cp flag.txt.en pole.txt && l
ende.py  flag.txt.en  password.txt  pole.txt
    
┌──(kali㉿kali)-[~/picoctf/examen1/Python_Wrangling]
└─$ cat password.txt            
720b6ad346f84cd483c60c7464dd95d4

┌──(kali㉿kali)-[~/picoctf/examen1/Python_Wrangling]
└─$ python3 ende.py -d pole.txt
Please enter the password:python3 ende.py -d pole.txt^Z
zsh: suspended  python3 ende.py -d pole.txt

┌──(kali㉿kali)-[~/picoctf/examen1/Python_Wrangling]
└─$ python3 ende.py -d pole.txt
Please enter the password:720b6ad346f84cd483c60c7464dd95d4
picoCTF{4p0110_1n_7h3_h0us3_9c5f9bcf}

┌──(kali㉿kali)-[~/picoctf/examen1/Python_Wrangling]
└─$ 

```

picoCTF{4p0110_1n_7h3_h0us3_9c5f9bcf}

## Notas

[](https://github.com/neylar-11/notas-hacking-EneJun26/blob/main/picoCTF/Examen1/General%20Skills/8%20-%20Python%20Wrangling.md#notas)

- cp cambia el nombre y lo hicimos para hacer una copia

## Referencias
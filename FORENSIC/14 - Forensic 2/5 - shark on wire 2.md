## Descripción

We found this [packet capture](https://challenge-files.picoctf.net/c_fickle_tempest/da02deeb6a0b3cd4fa866b6d1b30190e358240a2cd734c8da5d5a048f87fa038/capture.pcap). Recover the flag

## Solución

```
┌──(kali㉿kali)-[~/picoctf/forensic2]
└─$ cd sharkonwire2

┌──(kali㉿kali)-[~/picoctf/forensic2/sharkonwire2]
└─$ wget https://challenge-files.picoctf.net/c_fickle_tempest/da02deeb6a0b3cd4fa866b6d1b30190e358240a2cd734c8da5d5a048f87fa038/capture.pcap
--2026-03-12 01:21:32--  https://challenge-files.picoctf.net/c_fickle_tempest/da02deeb6a0b3cd4fa866b6d1b30190e358240a2cd734c8da5d5a048f87fa038/capture.pcap
Resolving challenge-files.picoctf.net (challenge-files.picoctf.net)... 3.161.44.103, 3.161.44.61, 3.161.44.22, ...
Connecting to challenge-files.picoctf.net (challenge-files.picoctf.net)|3.161.44.103|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 112318 (110K) [application/octet-stream]
Saving to: ‘capture.pcap’

capture.pcap                               100%[=====================================================================================>] 109.69K  --.-KB/s    in 0.09s   

2026-03-12 01:21:32 (1.16 MB/s) - ‘capture.pcap’ saved [112318/112318]

┌──(kali㉿kali)-[~/picoctf/forensic2/sharkonwire2]
└─$ file capture.pcap                           
capture.pcap: pcap capture file, microsecond ts (little-endian) - version 2.4 (Ethernet, capture length 262144)

┌──(kali㉿kali)-[~/picoctf/forensic2/sharkonwire2]
└─$ wireshark capture.pcap &                                                                                                               
[2] 63346

┌──(kali㉿kali)-[~/picoctf/forensic2/sharkonwire2]
┌──(kali㉿kali)-[~/picoctf/forensic2/sharkonwire2]
└─$ python3            
Python 3.13.9 (main, Oct 15 2025, 14:56:22) [GCC 15.2.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> chr(105)
'i'
>>> chr(99)
'c'

┌──(kali㉿kali)-[~/picoctf/forensic2/sharkonwire2]
└─$ sudo apt install python3-scapy
The following package was automatically installed and is no longer required:
  libcrypt-dev
Use 'sudo apt autoremove' to remove it.
┌──(kali㉿kali)-[~/picoctf/forensic2/sharkonwire2]
└─$ nano exp.py   

┌──(kali㉿kali)-[~/picoctf/forensic2/sharkonwire2]
└─$ python3 exp.py
picoCTF{p1LLf3r3d_data_v1a_st3g0}

```

picoCTF{p1LLf3r3d_data_v1a_st3g0}

## Notas

## Referencias
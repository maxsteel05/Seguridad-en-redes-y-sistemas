## Descripción

Download the disk image and use `mmls` on it to find the size of the Linux partition. Connect to the remote checker service to check your answer and get the flag.Note: if you are using the webshell, download and extract the disk image into `/tmp` not your home directory.[Download disk image](https://artifacts.picoctf.net/c/164/disk.img.gz)Access checker program: `nc saturn.picoctf.net 58367`

## Solución

```
┌──(kali㉿kali)-[~/picoctf/forensic4/sleuthkit]
└─$ wget https://artifacts.picoctf.net/c/164/disk.img.gz                                                                                   
--2026-03-23 10:45:09--  https://artifacts.picoctf.net/c/164/disk.img.gz
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 13.249.182.58, 13.249.182.81, 13.249.182.55, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|13.249.182.58|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 29714372 (28M) [application/octet-stream]
Saving to: ‘disk.img.gz’

disk.img.gz                               100%[=====================================================================================>]  28.34M  3.26MB/s    in 22s     

2026-03-23 10:45:33 (1.31 MB/s) - ‘disk.img.gz’ saved [29714372/29714372]

                                                                                                                                                                        
┌──(kali㉿kali)-[~/picoctf/forensic4/sleuthkit]
└─$ gunzip disk.img.gz   
                                                                                                                                                                        
┌──(kali㉿kali)-[~/picoctf/forensic4/sleuthkit]
└─$ ls
disk.img
                                                                                                                                                                        
┌──(kali㉿kali)-[~/picoctf/forensic4/sleuthkit]
└─$ mmls dds1-alpine.flag.img
Error stat(ing) image file (raw_open: image "dds1-alpine.flag.img" - No such file or directory)
                                                                                                                                                                        
┌──(kali㉿kali)-[~/picoctf/forensic4/sleuthkit]
└─$ mmls disk.img
DOS Partition Table
Offset Sector: 0
Units are in 512-byte sectors

      Slot      Start        End          Length       Description
000:  Meta      0000000000   0000000000   0000000001   Primary Table (#0)
001:  -------   0000000000   0000002047   0000002048   Unallocated
002:  000:000   0000002048   0000204799   0000202752   Linux (0x83)
                                                                                                                                                                        
┌──(kali㉿kali)-[~/picoctf/forensic4/sleuthkit]
└─$  nc saturn.picoctf.net 61995
What is the size of the Linux partition in the given disk image?
Length in sectors: 260096
260096
That is not correct. Feel free to try again.
                                                                                                                                                                        
┌──(kali㉿kali)-[~/picoctf/forensic4/sleuthkit]
└─$ nc saturn.picoctf.net 61995                        
What is the size of the Linux partition in the given disk image?
Length in sectors: 202752
202752
Great work!
picoCTF{mm15_f7w!}

```

picoCTF{mm15_f7w!}

## Notas

## Referencias
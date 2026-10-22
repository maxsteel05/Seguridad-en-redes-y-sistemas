## Descripción

Download this disk image and find the flag.Note: if you are using the webshell, download and extract the disk image into `/tmp` not your home directory.

- [Download compressed disk image](https://artifacts.picoctf.net/c/138/disk.flag.img.gz)

## Solución

```
┌──(kali㉿kali)-[~/picoctf/forensic4/SleuthkitApprentice]
└─$ wget https://artifacts.picoctf.net/c/138/disk.flag.img.gz
--2026-03-23 10:52:40--  https://artifacts.picoctf.net/c/138/disk.flag.img.gz
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 13.225.222.28, 13.225.222.120, 13.225.222.105, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|13.225.222.28|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 47534528 (45M) [application/octet-stream]
Saving to: ‘disk.flag.img.gz’

disk.flag.img.gz                          100%[=====================================================================================>]  45.33M  4.09MB/s    in 15s     

2026-03-23 10:52:55 (3.10 MB/s) - ‘disk.flag.img.gz’ saved [47534528/47534528]

                                                                                                                                                                        
┌──(kali㉿kali)-[~/picoctf/forensic4/SleuthkitApprentice]
└─$ gzip -d disk.flag.img.gz
                                                                                                                                                                        
┌──(kali㉿kali)-[~/picoctf/forensic4/SleuthkitApprentice]
└─$ ls                       
disk.flag.img
                                                                                                                                                                        
┌──(kali㉿kali)-[~/picoctf/forensic4/SleuthkitApprentice]
└─$ mmls disk.fla.img        
Error stat(ing) image file (raw_open: image "disk.fla.img" - No such file or directory)
                                                                                                                                                                        
┌──(kali㉿kali)-[~/picoctf/forensic4/SleuthkitApprentice]
└─$ mmls disk.flag.img
DOS Partition Table
Offset Sector: 0
Units are in 512-byte sectors

      Slot      Start        End          Length       Description
000:  Meta      0000000000   0000000000   0000000001   Primary Table (#0)
001:  -------   0000000000   0000002047   0000002048   Unallocated
002:  000:000   0000002048   0000206847   0000204800   Linux (0x83)
003:  000:001   0000206848   0000360447   0000153600   Linux Swap / Solaris x86 (0x82)
004:  000:002   0000360448   0000614399   0000253952   Linux (0x83)
                                                                                                                                                                        
┌──(kali㉿kali)-[~/picoctf/forensic4/SleuthkitApprentice]
└─$ fsstat -o 2048 disk.flag.img
FILE SYSTEM INFORMATION
--------------------------------------------
File System Type: Ext4
Volume Name: 
Volume ID: 8e023955b4e7dab7e04b7643076ccf0f


Group: 12:
  Inode Range: 23617 - 25584
  Block Range: 98305 - 102399
  Layout:
    Data bitmap: 271 - 271
    Inode bitmap: 284 - 284
    Inode Table: 6189 - 6680
    Data Blocks: 6681 - 102399
  Free Inodes: 1968 (100%)
  Free Blocks: 4095 (99%)
  Total Directories: 0
                                                                                                                                                                        
┌──(kali㉿kali)-[~/picoctf/forensic4/SleuthkitApprentice]
└─$ fls -i raw -f ext4 -o 2048 -r disk.flag.img
d/d 11: lost+found
r/r 12: ldlinux.sys
r/r 13: ldlinux.c32
r/r 15: config-virt
r/r 16: vmlinuz-virt
r/r 17: initramfs-virt
l/l 18: boot
r/r 20: libutil.c32
r/r 19: extlinux.conf
r/r 21: libcom32.c32
r/r 22: mboot.c32
r/r 23: menu.c32
r/r 14: System.map-virt
r/r 24: vesamenu.c32
V/V 25585:      $OrphanFiles
                                                                                                                                                                        
┌──(kali㉿kali)-[~/picoctf/forensic4/SleuthkitApprentice]
└─$ icat -i raw -f ext4 -o 360448 disk.flag.img 2371
picoCTF{by73_5urf3r_2f22df38}

```

picoCTF{by73_5urf3r_2f22df38}

## Notas

## Referencias
## Descripción
Matryoshka dolls are a set of wooden dolls of decreasing size placed one inside another. What's the final one?Image: [dolls.jpg](https://challenge-files.picoctf.net/c_wily_courier/9bf118825bda566d4622b19d243e75877e2c17db745281bc5b0d11efd2278161/dolls.jpg)

### Solucion

```
┌──(kali㉿kali)-[~/picoctf/forensic3/Matryoshka]
└─$ wget https://challenge-files.picoctf.net/c_wily_courier/9bf118825bda566d4622b19d243e75877e2c17db745281bc5b0d11efd2278161/dolls.jpg     
--2026-03-18 10:25:08--  https://challenge-files.picoctf.net/c_wily_courier/9bf118825bda566d4622b19d243e75877e2c17db745281bc5b0d11efd2278161/dolls.jpg
Resolving challenge-files.picoctf.net (challenge-files.picoctf.net)... 18.154.206.118, 18.154.206.14, 18.154.206.27, ...
Connecting to challenge-files.picoctf.net (challenge-files.picoctf.net)|18.154.206.118|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 651613 (636K) [application/octet-stream]
Saving to: ‘dolls.jpg’

dolls.jpg                                 100%[=====================================================================================>] 636.34K   589KB/s    in 1.1s    

2026-03-18 10:25:10 (589 KB/s) - ‘dolls.jpg’ saved [651613/651613]


┌──(kali㉿kali)-[~/picoctf/forensic3/Matryoshka]
└─$ ls
dolls.jpg

┌──(kali㉿kali)-[~/picoctf/forensic3/Matryoshka]
└─$ open dolls.jpg

┌──(kali㉿kali)-[~/picoctf/forensic3/Matryoshka]
└─$ sudo apt insatall binwalk                                 
[sudo] password for kali: 
Error: Invalid operation insatall
   
┌──(kali㉿kali)-[~/picoctf/forensic3/Matryoshka]
└─$ sudo apt install binwalk 
binwalk is already the newest version (2.4.3+dfsg1-2).
binwalk set to manually installed.
The following package was automatically installed and is no longer required:
  libcrypt-dev
Use 'sudo apt autoremove' to remove it.

Summary:
  Upgrading: 0, Installing: 0, Removing: 0, Not Upgrading: 1685

┌──(kali㉿kali)-[~/picoctf/forensic3/Matryoshka]
└─$ binwalk dolls.jpg

DECIMAL       HEXADECIMAL     DESCRIPTION
--------------------------------------------------------------------------------
0             0x0             PNG image, 594 x 1104, 8-bit/color RGBA, non-interlaced
3226          0xC9A           TIFF image data, big-endian, offset of first image directory: 8
272492        0x4286C         Zip archive data, at least v2.0 to extract, compressed size: 378933, uncompressed size: 383920, name: base_images/2_c.jpg
651591        0x9F147         End of Zip archive, footer length: 22


┌──(kali㉿kali)-[~/picoctf/forensic3/Matryoshka]
└─$ unzip dolls.jpg
Archive:  dolls.jpg
warning [dolls.jpg]:  272492 extra bytes at beginning or within zipfile
  (attempting to process anyway)
  inflating: base_images/2_c.jpg     

┌──(kali㉿kali)-[~/picoctf/forensic3/Matryoshka]
└─$ ls
base_images  dolls.jpg

┌──(kali㉿kali)-[~/picoctf/forensic3/Matryoshka]
└─$ cd base_images   

┌──(kali㉿kali)-[~/picoctf/forensic3/Matryoshka/base_images]
└─$ ls                      
2_c.jpg

┌──(kali㉿kali)-[~/picoctf/forensic3/Matryoshka/base_images]
└─$ unzip 2_c.jpg  
Archive:  2_c.jpg
warning [2_c.jpg]:  187707 extra bytes at beginning or within zipfile
  (attempting to process anyway)
  inflating: base_images/3_c.jpg     

┌──(kali㉿kali)-[~/picoctf/forensic3/Matryoshka/base_images]
└─$ ls
2_c.jpg  base_images

┌──(kali㉿kali)-[~/picoctf/forensic3/Matryoshka/base_images]
└─$ cd base_images

┌──(kali㉿kali)-[~/…/forensic3/Matryoshka/base_images/base_images]
└─$ ls
3_c.jpg

┌──(kali㉿kali)-[~/…/forensic3/Matryoshka/base_images/base_images]
└─$ unzip 2_c.jpg
unzip:  cannot find or open 2_c.jpg, 2_c.jpg.zip or 2_c.jpg.ZIP.

┌──(kali㉿kali)-[~/…/forensic3/Matryoshka/base_images/base_images]
└─$ unzip 3_c.jpg
Archive:  3_c.jpg
warning [3_c.jpg]:  123606 extra bytes at beginning or within zipfile
  (attempting to process anyway)
  inflating: base_images/4_c.jpg     

┌──(kali㉿kali)-[~/…/forensic3/Matryoshka/base_images/base_images]
└─$ ls
3_c.jpg  base_images

┌──(kali㉿kali)-[~/…/forensic3/Matryoshka/base_images/base_images]
└─$ cd base_images

┌──(kali㉿kali)-[~/…/Matryoshka/base_images/base_images/base_images]
└─$ ls
4_c.jpg

┌──(kali㉿kali)-[~/…/Matryoshka/base_images/base_images/base_images]
└─$ unzip 4_c.jpg
Archive:  4_c.jpg
warning [4_c.jpg]:  79578 extra bytes at beginning or within zipfile
  (attempting to process anyway)
 extracting: flag.txt                

┌──(kali㉿kali)-[~/…/Matryoshka/base_images/base_images/base_images]
└─$ cat flag.txt    
picoCTF{LL9lb1dR4QbGe4l4iWCvGq9pdtwt7392}

```

picoCTF{LL9lb1dR4QbGe4l4iWCvGq9pdtwt7392}

## Notas

## Referencias
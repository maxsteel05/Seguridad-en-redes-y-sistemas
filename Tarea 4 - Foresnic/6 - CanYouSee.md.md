## Descripción
How about some hide and seek?Download this file [here](https://artifacts.picoctf.net/c_titan/6/unknown.zip).
## Solución
```
┌──(kali㉿kali)-[~/picoctf/t4forensic/CanYouSee]
└─$ wget https://artifacts.picoctf.net/c_titan/6/unknown.zip                                               
--2026-03-24 22:17:15--  https://artifacts.picoctf.net/c_titan/6/unknown.zip
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.161.55.26, 3.161.55.61, 3.161.55.100, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.161.55.26|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 2252298 (2.1M) [application/octet-stream]
Saving to: ‘unknown.zip’

unknown.zip                               100%[=====================================================================================>]   2.15M  5.92MB/s    in 0.4s    

2026-03-24 22:17:16 (5.92 MB/s) - ‘unknown.zip’ saved [2252298/2252298]

┌──(kali㉿kali)-[~/picoctf/t4forensic/CanYouSee]
└─$ gunzip unknown.zip   
gzip: unknown.zip: unknown suffix -- ignored

┌──(kali㉿kali)-[~/picoctf/t4forensic/CanYouSee]
└─$ gzip unknown.zip 

┌──(kali㉿kali)-[~/picoctf/t4forensic/CanYouSee]
└─$ ls
unknown.zip.gz

┌──(kali㉿kali)-[~/picoctf/t4forensic/CanYouSee]
└─$ gzip unknown.zip.gz
gzip: unknown.zip.gz already has .gz suffix -- unchanged

┌──(kali㉿kali)-[~/picoctf/t4forensic/CanYouSee]
└─$ gzip unknown.zip.gz
gzip: unknown.zip.gz already has .gz suffix -- unchanged

┌──(kali㉿kali)-[~/picoctf/t4forensic/CanYouSee]
└─$ gunzip unknown.zip.gz

┌──(kali㉿kali)-[~/picoctf/t4forensic/CanYouSee]
└─$ ls
unknown.zip

┌──(kali㉿kali)-[~/picoctf/t4forensic/CanYouSee]
└─$ exiftool ukn_reality.jpg
Error: File not found - ukn_reality.jpg

┌──(kali㉿kali)-[~/picoctf/t4forensic/CanYouSee]
└─$ cd unknown.zip
cd: not a directory: unknown.zip

┌──(kali㉿kali)-[~/picoctf/t4forensic/CanYouSee]
└─$ unzip unknown.zip       
Archive:  unknown.zip
  inflating: ukn_reality.jpg         

┌──(kali㉿kali)-[~/picoctf/t4forensic/CanYouSee]
└─$ exiftool ukn_reality.jpg
ExifTool Version Number         : 13.36
File Name                       : ukn_reality.jpg
Directory                       : .
File Size                       : 2.3 MB
File Modification Date/Time     : 2024:02:15 17:40:21-05:00
File Access Date/Time           : 2024:02:15 17:40:21-05:00
File Inode Change Date/Time     : 2026:03:24 22:26:44-04:00
File Permissions                : -rw-r--r--
File Type                       : JPEG
File Type Extension             : jpg
MIME Type                       : image/jpeg
JFIF Version                    : 1.01
Resolution Unit                 : inches
X Resolution                    : 72
Y Resolution                    : 72
XMP Toolkit                     : Image::ExifTool 11.88
Attribution URL                 : cGljb0NURntNRTc0RDQ3QV9ISUREM05fYTZkZjhkYjh9Cg==
Image Width                     : 4308
Image Height                    : 2875
Encoding Process                : Baseline DCT, Huffman coding
Bits Per Sample                 : 8
Color Components                : 3
Y Cb Cr Sub Sampling            : YCbCr4:2:0 (2 2)
Image Size                      : 4308x2875
Megapixels                      : 12.4

┌──(kali㉿kali)-[~/picoctf/t4forensic/CanYouSee]
└─$ echo -n cGljb0NURntNRTc0RDQ3QV9ISUREM05fYjMyMDQwYjh9Cg== | base64 -d
picoCTF{ME74D47A_HIDD3N_b32040b8}

```

picoCTF{ME74D47A_HIDD3N_a6df8db8}

## Notas

## Referencias
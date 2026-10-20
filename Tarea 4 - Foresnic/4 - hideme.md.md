## Descripción
Every file gets a flag.The SOC analyst saw one image been sent back and forth between two people. They decided to investigate and found out that there was more than what meets the eye [here](https://artifacts.picoctf.net/c/257/flag.png).
## Solución
```
┌──(kali㉿kali)-[~/picoctf/t4forensic/hideme]
└─$ wget https://artifacts.picoctf.net/c/257/flag.png                                                                                      
--2026-03-24 21:57:02--  https://artifacts.picoctf.net/c/257/flag.png
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.161.55.64, 3.161.55.100, 3.161.55.26, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.161.55.64|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 43020 (42K) [application/octet-stream]
Saving to: ‘flag.png’

flag.png                                  100%[=====================================================================================>]  42.01K  --.-KB/s    in 0.06s   

2026-03-24 21:57:02 (731 KB/s) - ‘flag.png’ saved [43020/43020]



┌──(kali㉿kali)-[~/picoctf/t4forensic/hideme]
└─$ file flag.png    
flag.png: PNG image data, 512 x 504, 8-bit/color RGBA, non-interlaced



┌──(kali㉿kali)-[~/picoctf/t4forensic/hideme]
└─$ xxd flag.png | tail
0000a770: 0700 1800 0000 0000 0000 1000 ed41 0000  .............A..
0000a780: 0000 7365 6372 6574 2f55 5405 0003 8b78  ..secret/UT....x
0000a790: 1264 7578 0b00 0104 0000 0000 0400 0000  .dux............
0000a7a0: 0050 4b01 021e 0314 0000 0008 0038 1070  .PK..........8.p
0000a7b0: 56f5 230b f88f 0b00 0024 0c00 000f 0018  V.#......$......
0000a7c0: 0000 0000 0000 0000 00a4 8141 0000 0073  ...........A...s
0000a7d0: 6563 7265 742f 666c 6167 2e70 6e67 5554  ecret/flag.pngUT
0000a7e0: 0500 038b 7812 6475 780b 0001 0400 0000  ....x.dux.......
0000a7f0: 0004 0000 0000 504b 0506 0000 0000 0200  ......PK........
0000a800: 0200 a200 0000 190c 0000 0000            ............


    
┌──(kali㉿kali)-[~/picoctf/t4forensic/hideme]
└─$ binwalk -e flag.png

DECIMAL       HEXADECIMAL     DESCRIPTION
--------------------------------------------------------------------------------
41            0x29            Zlib compressed data, compressed
39739         0x9B3B          Zip archive data, at least v1.0 to extract, name: secret/
39804         0x9B7C          Zip archive data, at least v2.0 to extract, compressed size: 2959, uncompressed size: 3108, name: secret/flag.png

WARNING: One or more files failed to extract: either no utility was found or it's unimplemented


┌──(kali㉿kali)-[~/picoctf/t4forensic/hideme]
└─$ tree           
.
├── flag.png
└── _flag.png.extracted
    ├── 29
    ├── 29.zlib
    ├── 9B3B.zip
    └── secret
        └── flag.png

3 directories, 5 files

```

picoCTF{Hiddinng_An_imag3_within_@n_ima9e_dc2ab58f}

## Notas

### 1️ `xxd flag.png`

`xxd` convierte un archivo binario a **hexadecimal + ASCII**.  
Por ejemplo, muestra algo así:

00000000: 8950 4e47 0d0a 1a0a ...

Eso permite **analizar archivos binarios** como imágenes, ejecutables, etc.

### 2️ `|` (pipe)

El `|` envía la salida del primer comando al siguiente.

### 3️ `tail`

`tail` muestra **las últimas líneas de la salida**.

ya solo abri la imagen

## Referencias
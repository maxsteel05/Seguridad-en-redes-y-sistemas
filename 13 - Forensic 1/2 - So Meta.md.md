## Descripción

Find the flag in this [picture](https://challenge-files.picoctf.net/c_fickle_tempest/d534c920bd33d42b413e67d21cacbf7aa232c4823ce29872eca285471558f00a/pico_img.png).
## Solución

```
┌──(kali㉿kali)-[~]
└─$ wget https://challenge-files.picoctf.net/c_fickle_tempest/d534c920bd33d42b413e67d21cacbf7aa232c4823ce29872eca285471558f00a/pico_img.png
--2026-03-09 10:12:50--  https://challenge-files.picoctf.net/c_fickle_tempest/d534c920bd33d42b413e67d21cacbf7aa232c4823ce29872eca285471558f00a/pico_img.png
Resolving challenge-files.picoctf.net (challenge-files.picoctf.net)... 18.238.132.49, 18.238.132.115, 18.238.132.26, ...
Connecting to challenge-files.picoctf.net (challenge-files.picoctf.net)|18.238.132.49|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 108795 (106K) [application/octet-stream]
Saving to: ‘pico_img.png’

pico_img.png       100%[===============>] 106.25K  --.-KB/s    in 0.1s    

2026-03-09 10:12:51 (931 KB/s) - ‘pico_img.png’ saved [108795/108795]
   
┌──(kali㉿kali)-[~]
└─$ open pico_img.png
   
┌──(kali㉿kali)-[~]
└─$ sudo apt install exiftool
[sudo] password for kali: 
Note, selecting 'libimage-exiftool-perl' instead of 'exiftool'
Upgrading:                  
  libimage-exiftool-perl
  
Summary:
  Upgrading: 1, Installing: 0, Removing: 0, Not Upgrading: 1700
  Download size: 5,960 kB
  Space needed: 317 kB / 60.4 GB available

Err:1 http://http.kali.org/kali kali-rolling/main amd64 libimage-exiftool-perl all 13.50+dfsg-1
  403  Forbidden [IP: 54.39.128.230 80]
Error: Failed to fetch http://http.kali.org/kali/pool/main/libi/libimage-exiftool-perl/libimage-exiftool-perl_13.50%2bdfsg-1_all.deb  403  Forbidden [IP: 54.39.128.230 80]
Error: Unable to fetch some archives, maybe run apt update or try with --fix-missing?
  
┌──(kali㉿kali)-[~]
└─$ sudo apt install exiftool
Note, selecting 'libimage-exiftool-perl' instead of 'exiftool'
Upgrading:                  
  libimage-exiftool-perl
      
Summary:
  Upgrading: 1, Installing: 0, Removing: 0, Not Upgrading: 1700
  Download size: 5,960 kB
  Space needed: 317 kB / 60.4 GB available

Err:1 http://http.kali.org/kali kali-rolling/main amd64 libimage-exiftool-perl all 13.50+dfsg-1
  403  Forbidden [IP: 54.39.128.230 80]
Error: Failed to fetch http://http.kali.org/kali/pool/main/libi/libimage-exiftool-perl/libimage-exiftool-perl_13.50%2bdfsg-1_all.deb  403  Forbidden [IP: 54.39.128.230 80]
Error: Unable to fetch some archives, maybe run apt update or try with --fix-missing?

┌──(kali㉿kali)-[~]
└─$ exiftool pico_img.png
ExifTool Version Number         : 13.36
File Name                       : pico_img.png
Directory                       : .
File Size                       : 109 kB
File Modification Date/Time     : 2025:11:21 14:11:04-05:00
File Access Date/Time           : 2026:03:09 10:13:13-04:00
File Inode Change Date/Time     : 2026:03:09 10:12:51-04:00
File Permissions                : -rw-rw-r--
File Type                       : PNG
File Type Extension             : png
MIME Type                       : image/png
Image Width                     : 600
Image Height                    : 600
Bit Depth                       : 8
Color Type                      : RGB
Compression                     : Deflate/Inflate
Filter                          : Adaptive
Interlace                       : Noninterlaced
Software                        : Adobe ImageReady
XMP Toolkit                     : Adobe XMP Core 5.3-c011 66.145661, 2012/02/06-14:56:27
Creator Tool                    : Adobe Photoshop CS6 (Windows)
Instance ID                     : xmp.iid:A5566E73B2B811E8BC7F9A4303DF1F9B
Document ID                     : xmp.did:A5566E74B2B811E8BC7F9A4303DF1F9B
Derived From Instance ID        : xmp.iid:A5566E71B2B811E8BC7F9A4303DF1F9B
Derived From Document ID        : xmp.did:A5566E72B2B811E8BC7F9A4303DF1F9B
Artist                          : picoCTF{s0_m3ta_74af23ab}
Image Size                      : 600x600
Megapixels                      : 0.360
      
```

picoCTF{s0_m3ta_74af23ab}

## Notas
`exiftool` sirve para **ver metadatos de archivos**.

Los metadatos son **información oculta dentro de archivos**, por ejemplo:

- quién creó el archivo
    
- con qué programa
    
- fecha
    
- GPS
    
- comentarios
    
- autor
    

## Referencias
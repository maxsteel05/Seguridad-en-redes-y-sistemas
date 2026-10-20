## Descripción

Files can always be changed in a secret way. Can you find the flag?[cat.jpg](https://challenge-files.picoctf.net/c_wily_courier/76e95e3e6ee69b4f82b3cea25051f5a9a5918b57809a1f90b29b06b776c73bc7/cat.jpg)
## Solución
```
┌──(kali㉿kali)-[~/picoctf/t4forensic/information]
└─$ wget https://challenge-files.picoctf.net/c_wily_courier/76e95e3e6ee69b4f82b3cea25051f5a9a5918b57809a1f90b29b06b776c73bc7/cat.jpg       
--2026-03-24 21:38:50--  https://challenge-files.picoctf.net/c_wily_courier/76e95e3e6ee69b4f82b3cea25051f5a9a5918b57809a1f90b29b06b776c73bc7/cat.jpg
Resolving challenge-files.picoctf.net (challenge-files.picoctf.net)... 3.161.44.84, 3.161.44.22, 3.161.44.103, ...
Connecting to challenge-files.picoctf.net (challenge-files.picoctf.net)|3.161.44.84|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 878136 (858K) [application/octet-stream]
Saving to: ‘cat.jpg’

cat.jpg                                   100%[=====================================================================================>] 857.55K  2.97MB/s    in 0.3s    

2026-03-24 21:38:51 (2.97 MB/s) - ‘cat.jpg’ saved [878136/878136]



┌──(kali㉿kali)-[~/picoctf/t4forensic/information]
└─$ file cat.jpg     
cat.jpg: JPEG image data, JFIF standard 1.02, aspect ratio, density 1x1, segment length 16, baseline, precision 8, 2560x1598, components 3



┌──(kali㉿kali)-[~/picoctf/t4forensic/information]
└─$ binwalk cat.jpg

DECIMAL       HEXADECIMAL     DESCRIPTION
--------------------------------------------------------------------------------
0             0x0             JPEG image data, JFIF standard 1.02
49661         0xC1FD          JBOOT STAG header, image id: 14, timestamp 0x37E26150, image size: 562276742 bytes, image JBOOT checksum: 0xC9A6, header JBOOT checksum: 0x40D4



┌──(kali㉿kali)-[~/picoctf/t4forensic/information]
└─$ echo cGljb0NURnt0aGVfbTN0YWRhdGFfMXNfbW9kaWZpZWR9 | base64 -d
picoCTF{the_m3tadata_1s_modified}
```

picoCTF{the_m3tadata_1s_modified}

## Notas

## Referencias
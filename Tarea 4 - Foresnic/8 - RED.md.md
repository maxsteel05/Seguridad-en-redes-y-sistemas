## Descripción
RED, RED, RED, REDDownload the image: [red.png](https://challenge-files.picoctf.net/c_verbal_sleep/831307718b34193b288dde31e557484876fb84978b5818e2627e453a54aa9ba6/red.png)

## Solución

### Solucion


```
┌──(kali㉿kali)-[~/picoctf/t4forensic/RED]
└─$ wget https://challenge-files.picoctf.net/c_verbal_sleep/831307718b34193b288dde31e557484876fb84978b5818e2627e453a54aa9ba6/red.png
--2026-03-24 22:42:23--  https://challenge-files.picoctf.net/c_verbal_sleep/831307718b34193b288dde31e557484876fb84978b5818e2627e453a54aa9ba6/red.png
Resolving challenge-files.picoctf.net (challenge-files.picoctf.net)... 3.161.44.22, 3.161.44.84, 3.161.44.61, ...
Connecting to challenge-files.picoctf.net (challenge-files.picoctf.net)|3.161.44.22|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 796 [application/octet-stream]
Saving to: ‘red.png’

red.png                                   100%[=====================================================================================>]     796  --.-KB/s    in 0s      

2026-03-24 22:42:23 (5.40 MB/s) - ‘red.png’ saved [796/796]


┌──(kali㉿kali)-[~/picoctf/t4forensic/RED]
└─$ open red.png   

┌──(kali㉿kali)-[~/picoctf/t4forensic/RED]
└─$ zsteg -a red.png
meta Poem           .. text: "Crimson heart, vibrant and bold,\nHearts flutter at your sight.\nEvenings glow softly red,\nCherries burst with sweet life.\nKisses linger with your warmth.\nLove deep as merlot.\nScarlet leaves falling softly,\nBold in every stroke."                                                                        
chunk:0:IHDR        .. file: Adobe Photoshop Color swatch, version 0, 128 colors; 1st RGB space (0), w 0x80, x 0x806, y 0, z 0; 2nd HSB space (1), w 0x100, x 0, y 0xff01, z 0xff                                                                                                                                                               
b1,rgba,lsb,xy      .. text: "cGljb0NURntyM2RfMXNfdGgzX3VsdDFtNHQzX2N1cjNfZjByXzU0ZG4zNTVffQ==cGljb0NURntyM2RfMXNfdGgzX3VsdDFtNHQzX2N1cjNfZjByXzU0ZG4zNTVffQ==cGljb0NURntyM2RfMXNfdGgzX3VsdDFtNHQzX2N1cjNfZjByXzU0ZG4zNTVffQ==cGljb0NURntyM2RfMXNfdGgzX3VsdDFtNHQzX2N1cjNfZjByXzU0ZG4zNTVffQ=="  
b6p,abgr,msb,YX,prime.. text: ["?" repeated 31 times]
b7,rgb,lsb,YX,prime .. file: structured file
b7,rgba,lsb,YX,prime.. file: structured file
b7p,r,msb,YX,prime  .. text: ["?" repeated 11 times]
b7p,a,msb,YX,prime  .. text: ["?" repeated 43 times]
b7p,rgb,msb,YX,prime.. text: ["?" repeated 23 times]
b7p,bgr,msb,YX,prime.. text: ["@" repeated 23 times]
b7p,abgr,msb,YX,prime.. file: RDI Acoustic Doppler Current Profiler (ADCP)
b8,bgr,lsb,YX,prime .. file: raw G3 (Group 3) FAX, byte-padded

┌──(kali㉿kali)-[~/picoctf/t4forensic/RED]
└─$ echo -n cGljb0NURntyM2RfMXNfdGgzX3VsdDFtNHQzX2N1cjNfZjByXzU0ZG4zNTVffQ==cGljb0NURntyM2RfMXNfdGgzX3VsdDFtNHQzX2N1cjNfZjByXzU0ZG4zNTVffQ==cGljb0NURntyM2RfMXNfdGgzX3VsdDFtNHQzX2N1cjNfZjByXzU0ZG4zNTVffQ==cGljb0NURntyM2RfMXNfdGgzX3VsdDFtNHQzX2N1cjNfZjByXzU0ZG4zNTVffQ== | base64 -d
picoCTF{r3d_1s_th3_ult1m4t3_cur3_f0r_54dn355_}picoCTF{r3d_1s_th3_ult1m4t3_cur3_f0r_54dn355_}picoCTF{r3d_1s_th3_ult1m4t3_cur3_f0r_54dn355_}picoCTF{r3d_1s_th3_ult1m4t3_cur3_f0r_54dn355_} 
```

picoCTF{r3d_1s_th3_ult1m4t3_cur3_f0r_54dn355_}

## Notas

## Referencias
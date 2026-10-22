## Descripción

I have these 2 images, can you make a flag out of them?[scrambled1.png](https://challenge-files.picoctf.net/c_wily_courier/d1577440e9a1f6f9ff3eacd6ec6a4b40722de3970b527f0e07e5a4a6f1c3c3e8/scrambled1.png) [scrambled2.png](https://challenge-files.picoctf.net/c_wily_courier/d1577440e9a1f6f9ff3eacd6ec6a4b40722de3970b527f0e07e5a4a6f1c3c3e8/scrambled2.png)

## Solución

```
┌──(kali㉿kali)-[~/picoctf/cripto4/Pixelated]
└─$ wget https://challenge-files.picoctf.net/c_wily_courier/d1577440e9a1f6f9ff3eacd6ec6a4b40722de3970b527f0e07e5a4a6f1c3c3e8/scrambled1.png
--2026-04-22 15:15:37--  https://challenge-files.picoctf.net/c_wily_courier/d1577440e9a1f6f9ff3eacd6ec6a4b40722de3970b527f0e07e5a4a6f1c3c3e8/scrambled1.png
Resolving challenge-files.picoctf.net (challenge-files.picoctf.net)... 3.174.207.121, 3.174.207.96, 3.174.207.109, ...
Connecting to challenge-files.picoctf.net (challenge-files.picoctf.net)|3.174.207.121|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 197174 (193K) [application/octet-stream]
Saving to: ‘scrambled1.png’

scrambled1.png                            100%[===================================================================================>] 192.55K  1.16MB/s    in 0.2s    

2026-04-22 15:15:37 (1.16 MB/s) - ‘scrambled1.png’ saved [197174/197174]

                                                                                                                                                                      
┌──(kali㉿kali)-[~/picoctf/cripto4/Pixelated]
└─$ wget https://challenge-files.picoctf.net/c_wily_courier/d1577440e9a1f6f9ff3eacd6ec6a4b40722de3970b527f0e07e5a4a6f1c3c3e8/scrambled2.png
--2026-04-22 15:16:02--  https://challenge-files.picoctf.net/c_wily_courier/d1577440e9a1f6f9ff3eacd6ec6a4b40722de3970b527f0e07e5a4a6f1c3c3e8/scrambled2.png
Resolving challenge-files.picoctf.net (challenge-files.picoctf.net)... 3.174.207.125, 3.174.207.109, 3.174.207.96, ...
Connecting to challenge-files.picoctf.net (challenge-files.picoctf.net)|3.174.207.125|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 197173 (193K) [application/octet-stream]
Saving to: ‘scrambled2.png’

scrambled2.png                            100%[===================================================================================>] 192.55K  1.21MB/s    in 0.2s    

2026-04-22 15:16:03 (1.21 MB/s) - ‘scrambled2.png’ saved [197173/197173]

                                                                                                                                                                      
┌──(kali㉿kali)-[~/picoctf/cripto4/Pixelated]
└─$ sudo wget http://www.caesum.com/handbook/Stegsolve.jar -O stegsolve.jar
[sudo] password for kali: 
--2026-04-22 15:17:04--  http://www.caesum.com/handbook/Stegsolve.jar
Resolving www.caesum.com (www.caesum.com)... 216.234.165.33
Connecting to www.caesum.com (www.caesum.com)|216.234.165.33|:80... connected.
HTTP request sent, awaiting response... 200 OK
Length: 312271 (305K) [application/x-java-archive]
Saving to: ‘stegsolve.jar’

stegsolve.jar                             100%[===================================================================================>] 304.95K   310KB/s    in 1.0s    

2026-04-22 15:17:05 (310 KB/s) - ‘stegsolve.jar’ saved [312271/312271]

                                                                                                                                                                      
┌──(kali㉿kali)-[~/picoctf/cripto4/Pixelated]
└─$ sudo chmod +x stegsolve.jar                                            
                                                                                                                                                                      
┌──(kali㉿kali)-[~/picoctf/cripto4/Pixelated]
└─$ nano exp.py                        
                                                                                                                                                                      
┌──(kali㉿kali)-[~/picoctf/cripto4/Pixelated]
└─$ python3 exp.py
  File "/home/kali/picoctf/cripto4/Pixelated/exp.py", line 12
    nueva = Image. fromarray(datos[
                                  ^
SyntaxError: '[' was never closed
                                                                                                                                                                      
┌──(kali㉿kali)-[~/picoctf/cripto4/Pixelated]
└─$ nano exp.py   
                                                                                                                                                                      
┌──(kali㉿kali)-[~/picoctf/cripto4/Pixelated]
└─$ python3 exp.py
Traceback (most recent call last):
  File "/home/kali/picoctf/cripto4/Pixelated/exp.py", line 4, in <module>
    imagen1 - np.asarray( Image.open('scrambled1.png') )
    ^^^^^^^
NameError: name 'imagen1' is not defined. Did you mean: 'Image'?
                                                                                                                                                                      
┌──(kali㉿kali)-[~/picoctf/cripto4/Pixelated]
└─$ nano exp.py   
                                                                                                                                                                      
┌──(kali㉿kali)-[~/picoctf/cripto4/Pixelated]
└─$ python3 exp.py
[[[188 202 127]
  [115 151  44]
  [  8 197  79]
  ...
  [ 46  63 139]
  [148  28  11]
  [107 155  95]]

 [[ 55 200  68]
  [250 112 131]
  [ 45 129 153]
  ...
  [ 85 139 177]
  [ 37 169  98]
  [221 131 162]]

 [[ 13  15 133]
  [172 130 136]
  [  5 205  70]
  ...
  [ 32 230 196]
  [ 94 170 180]
  [251  82 213]]

 ...

 [[133  73   7]
  [254  53 223]
  [254 248 168]
  ...
  [  1 198  92]
  [182 244 153]
  [ 46 224 189]]

 [[ 70 114 210]
  [246   4 194]
  [124  25  14]
  ...
  [174 190   1]
  [208  60 170]
  [168  30  60]]

 [[126 138 224]
  [ 17 223  87]
  [122 204 156]
  ...
  [187 103   4]
  [163 128  85]
  [173 254 114]]]
[[[ 67  53 128]
  [140 104 211]
  [247  58 176]
  ...
  [209 192 116]
  [107 227 244]
  [148 100 160]]

 [[200  55 187]
  [  5 143 124]
  [210 126 102]
  ...
  [170 116  78]
  [218  86 157]
  [ 34 124  93]]

 [[242 240 122]
  [ 83 125 119]
  [250  50 185]
  ...
  [223  25  59]
  [161  85  75]
  [  4 173  42]]

 ...

 [[122 182 248]
  [  1 202  32]
  [  1   7  87]
  ...
  [254  57 163]
  [ 73  11 102]
  [209  31  66]]

 [[185 141  45]
  [  9 251  61]
  [131 230 241]
  ...
  [ 81  65 254]
  [ 47 195  85]
  [ 87 225 195]]

 [[129 117  31]
  [238  32 168]
  [133  51  99]
  ...
  [ 68 152 251]
  [ 92 127 170]
  [ 82   1 141]]]
                                                                                                                                                                      
┌──(kali㉿kali)-[~/picoctf/cripto4/Pixelated]
└─$ ls
exp.py  nueva.png  scrambled1.png  scrambled2.png  stegsolve.jar
                                                                                                                                                                      
┌──(kali㉿kali)-[~/picoctf/cripto4/Pixelated]
└─$ open nueva.png

```

picoCTF{8cdf93c3}

## Notas

## Referencias
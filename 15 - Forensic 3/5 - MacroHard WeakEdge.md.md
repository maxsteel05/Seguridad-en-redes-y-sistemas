## Descripción
I've hidden a flag in this file. Can you find it?[Forensics_is_fun.pptm](https://challenge-files.picoctf.net/c_wily_courier/d78815176c19ddc85a1388233268d2f4c459fcbbaab197b4a29ebafc88294c54/Forensics_is_fun.pptm)

## Solución

```
┌──(kali㉿kali)-[~/picoctf/forensic3/macrohard]
└─$ python3 -m venv venv
  
┌──(kali㉿kali)-[~/picoctf/forensic3/macrohard]
└─$ source venv/bin/activate

┌──(venv)─(kali㉿kali)-[~/picoctf/forensic3/macrohard]
└─$ pip install oletools
Collecting oletools
  Downloading oletools-0.60.2-py2.py3-none-any.whl.metadata (16 kB)
Collecting pyparsing<4,>=2.1.0 (from oletools)
  Downloading pyparsing-3.3.2-py3-none-any.whl.metadata (5.8 kB)
Collecting olefile>=0.46 (from oletools)
  Downloading olefile-0.47-py2.py3-none-any.whl.metadata (9.7 kB)
Collecting easygui (from oletools)
  Downloading easygui-0.98.3-py2.py3-none-any.whl.metadata (8.4 kB)
Collecting colorclass (from oletools)
  Downloading colorclass-2.2.2-py2.py3-none-any.whl.metadata (5.2 kB)
Collecting pcodedmp>=1.2.5 (from oletools)
  Downloading pcodedmp-1.2.6-py2.py3-none-any.whl.metadata (11 kB)
Collecting msoffcrypto-tool (from oletools)
  Downloading msoffcrypto_tool-6.0.0-py3-none-any.whl.metadata (10 kB)
Collecting cryptography>=39.0 (from msoffcrypto-tool->oletools)
  Downloading cryptography-46.0.5-cp311-abi3-manylinux_2_34_x86_64.whl.metadata (5.7 kB)
Collecting cffi>=2.0.0 (from cryptography>=39.0->msoffcrypto-tool->oletools)
  Downloading cffi-2.0.0-cp313-cp313-manylinux2014_x86_64.manylinux_2_17_x86_64.whl.metadata (2.6 kB)
Collecting pycparser (from cffi>=2.0.0->cryptography>=39.0->msoffcrypto-tool->oletools)
  Downloading pycparser-3.0-py3-none-any.whl.metadata (8.2 kB)
Downloading oletools-0.60.2-py2.py3-none-any.whl (989 kB)
   ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 989.4/989.4 kB 103.6 kB/s  0:00:10
Downloading pyparsing-3.3.2-py3-none-any.whl (122 kB)
Downloading olefile-0.47-py2.py3-none-any.whl (114 kB)
Downloading pcodedmp-1.2.6-py2.py3-none-any.whl (30 kB)
Downloading colorclass-2.2.2-py2.py3-none-any.whl (18 kB)
Downloading easygui-0.98.3-py2.py3-none-any.whl (92 kB)
Downloading msoffcrypto_tool-6.0.0-py3-none-any.whl (48 kB)
Downloading cryptography-46.0.5-cp311-abi3-manylinux_2_34_x86_64.whl (4.5 MB)
   ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 4.5/4.5 MB 136.6 kB/s  0:00:34
Downloading cffi-2.0.0-cp313-cp313-manylinux2014_x86_64.manylinux_2_17_x86_64.whl (219 kB)
Downloading pycparser-3.0-py3-none-any.whl (48 kB)
Installing collected packages: easygui, pyparsing, pycparser, olefile, colorclass, cffi, cryptography, msoffcrypto-tool, pcodedmp, oletools
Successfully installed cffi-2.0.0 colorclass-2.2.2 cryptography-46.0.5 easygui-0.98.3 msoffcrypto-tool-6.0.0 olefile-0.47 oletools-0.60.2 pcodedmp-1.2.6 pycparser-3.0 pyparsing-3.3.2

┌──(venv)─(kali㉿kali)-[~/picoctf/forensic3/macrohard]
└─$ source venv/bin/activate

┌──(venv)─(kali㉿kali)-[~/picoctf/forensic3/macrohard]
└─$ unzip Forensics_is_fun.pptm -d unzipped
Archive:  Forensics_is_fun.pptm
  inflating: unzipped/[Content_Types].xml  
  inflating: unzipped/_rels/.rels
  
┌──(venv)─(kali㉿kali)-[~/picoctf/forensic3/macrohard]
└─$ ls
Forensics_is_fun.pptm  unzipped  venv

┌──(venv)─(kali㉿kali)-[~/picoctf/forensic3/macrohard]
└─$ cd unzipped 

┌──(venv)─(kali㉿kali)-[~/picoctf/forensic3/macrohard/unzipped]
└─$ ls
'[Content_Types].xml'   docProps   ppt   _rels

┌──(venv)─(kali㉿kali)-[~/picoctf/forensic3/macrohard/unzipped]
└─$ cd ppt     

┌──(venv)─(kali㉿kali)-[~/…/forensic3/macrohard/unzipped/ppt]
└─$ ls
presentation.xml  presProps.xml  _rels  slideLayouts  slideMasters  slides  tableStyles.xml  theme  vbaProject.bin  viewProps.xml

┌──(venv)─(kali㉿kali)-[~/…/forensic3/macrohard/unzipped/ppt]
└─$ cd slideMasters

┌──(venv)─(kali㉿kali)-[~/…/macrohard/unzipped/ppt/slideMasters]
└─$ ls
hidden  _rels  slideMaster1.xml

┌──(venv)─(kali㉿kali)-[~/…/macrohard/unzipped/ppt/slideMasters]
└─$ cat hidden 
    
Z m x h Z z o g c G l j b 0 N U R n t E M W R f d V 9 r b j B 3 X 3 B w d H N f c l 9 6 M X A 1 f Q                                                                                                                                                                        
┌──(venv)─(kali㉿kali)-[~/…/macrohard/unzipped/ppt/slideMasters]
└─$ cat hidden | tr -d ' ' | base64 -d
flag: picoCTF{D1d_u_kn0w_ppts_r_z1p5}
```

picoCTF{D1d_u_kn0w_ppts_r_z1p5}

## Notas

## Referencias
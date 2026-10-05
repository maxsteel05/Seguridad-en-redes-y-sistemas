## Descripción
Decode this [message](https://challenge-files.picoctf.net/c_fickle_tempest/678ff56c639c7645276578f3a9767ec2feaed1450045dd982c525b5795f7f589/message.wav) from the moon.
## Solución

```
┌──(kali㉿kali)-[~/picoctf/forensic2/m00nwalk]
└─$ sudo git clone https://github.com/colaclanth/sstv.git
[sudo] password for kali: 
Cloning into 'sstv'...
remote: Enumerating objects: 221, done.
remote: Counting objects: 100% (59/59), done.
remote: Compressing objects: 100% (10/10), done.
remote: Total 221 (delta 51), reused 49 (delta 49), pack-reused 162 (from 1)
Receiving objects: 100% (221/221), 1.01 MiB | 724.00 KiB/s, done.
Resolving deltas: 100% (139/139), done.

┌──(kali㉿kali)-[~/picoctf/forensic2/m00nwalk]
└─$ cd sstv

┌──(kali㉿kali)-[~/picoctf/forensic2/m00nwalk/sstv]
└─$ sudo python3 setup.py install
/usr/lib/python3/dist-packages/setuptools/dist.py:759: SetuptoolsDeprecationWarning: License classifiers are deprecated.
!!

┌──(kali㉿kali)-[~/picoctf/forensic2/m00nwalk/sstv]
└─$ sstv -d ../message.wav -o result.png
[sstv] Searching for calibration header... Found!    
[sstv] Detected SSTV mode Scottie 1
[sstv] Decoding image...                                        [####################################################################################################] 100%
[sstv] Drawing image data...
[sstv] ...Done!
Traceback (most recent call last):
  File "/usr/local/bin/sstv", line 33, in <module>
    sys.exit(load_entry_point('sstv==0.1', 'console_scripts', 'sstv')())
             ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~^^
  File "/usr/local/lib/python3.13/dist-packages/sstv-0.1-py3.13.egg/sstv/__main__.py", line 18, in main
    prog.start()
    ~~~~~~~~~~^^
  File "/usr/local/lib/python3.13/dist-packages/sstv-0.1-py3.13.egg/sstv/command.py", line 114, in start
    img.save(self._output_file)
    ~~~~~~~~^^^^^^^^^^^^^^^^^^^
  File "/usr/lib/python3/dist-packages/PIL/Image.py", line 2583, in save
    fp = builtins.open(filename, "w+b")
PermissionError: [Errno 13] Permission denied: 'result.png'

┌──(kali㉿kali)-[~/picoctf/forensic2/m00nwalk/sstv]
└─$ sstv -d ../message.wav -o result.png
[sstv] Searching for calibration header... Found!    
[sstv] Detected SSTV mode Scottie 1
[sstv] Decoding image...                                        [####################################################################################################] 100%
[sstv] Drawing image data...
[sstv] ...Done!
Traceback (most recent call last):
  File "/usr/local/bin/sstv", line 33, in <module>
    sys.exit(load_entry_point('sstv==0.1', 'console_scripts', 'sstv')())
             ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~^^
  File "/usr/local/lib/python3.13/dist-packages/sstv-0.1-py3.13.egg/sstv/__main__.py", line 18, in main
    prog.start()
    ~~~~~~~~~~^^
  File "/usr/local/lib/python3.13/dist-packages/sstv-0.1-py3.13.egg/sstv/command.py", line 114, in start
    img.save(self._output_file)
    ~~~~~~~~^^^^^^^^^^^^^^^^^^^
  File "/usr/lib/python3/dist-packages/PIL/Image.py", line 2583, in save
    fp = builtins.open(filename, "w+b")
PermissionError: [Errno 13] Permission denied: 'result.png'

┌──(kali㉿kali)-[~/picoctf/forensic2/m00nwalk/sstv]
└─$ sstv -d ../message.wav -o ../result.png

[sstv] Searching for calibration header... Found!    
[sstv] Detected SSTV mode Scottie 1
[sstv] Decoding image...                                        [####################################################################################################] 100%
[sstv] Drawing image data...
[sstv] ...Done!

┌──(kali㉿kali)-[~/picoctf/forensic2/m00nwalk/sstv]
└─$ 

┌──(kali㉿kali)-[~/picoctf/forensic2/m00nwalk/sstv]
└─$ opne result.png   
opne: command not found

┌──(kali㉿kali)-[~/picoctf/forensic2/m00nwalk/sstv]
└─$ open result.png

┌──(kali㉿kali)-[~/picoctf/forensic2/m00nwalk/sstv]
└─$ 

┌──(kali㉿kali)-[~/picoctf/forensic2/m00nwalk/sstv]
└─$ 

```

picoCTF{beep_boop_im_in_space}

## Notas
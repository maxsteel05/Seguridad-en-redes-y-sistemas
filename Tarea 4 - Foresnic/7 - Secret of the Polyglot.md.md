## Descripción

The Network Operations Center (NOC) of your local institution picked up a suspicious file, they're getting conflicting information on what type of file it is. They've brought you in as an external expert to examine the file. Can you extract all the information from this strange file?Download the suspicious file [here](https://artifacts.picoctf.net/c_titan/99/flag2of2-final.pdf).

## Solución



┌──(kali㉿kali)-[~/picoctf/t4forensic/SecretofthePolyglot]
└─$ pdftotext flag2of2-final.pdf

┌──(kali㉿kali)-[~/picoctf/t4forensic/SecretofthePolyglot]
└─$ cat flag2of2-final.txt        
1n_pn9_&_pdf_2a6a1ea8}

┌──(kali㉿kali)-[~/picoctf/t4forensic/SecretofthePolyglot]
└─$ ^[[200~# Description
zsh: bad pattern: ^[[200~#]

┌──(kali㉿kali)-[~/picoctf/t4forensic/SecretofthePolyglot]
└─$ 
  
┌──(kali㉿kali)-[~/picoctf/t4forensic/SecretofthePolyglot]
└─$ The Network Operations Center (NOC) of your local <br>
zsh: parse error near `\n'
 
┌──(kali㉿kali)-[~/picoctf/t4forensic/SecretofthePolyglot]
└─$ institution picked up a suspicious file, they're getting<br>
quote> conflicting information on what type of file it is. They've <br>
zsh: parse error near `\n'

┌──(kali㉿kali)-[~/picoctf/t4forensic/SecretofthePolyglot]
└─$ brought you in as an external expert to examine the <br>
zsh: parse error near `\n'
  
┌──(kali㉿kali)-[~/picoctf/t4forensic/SecretofthePolyglot]
└─$ file. Can you extract all the information from this <br>
zsh: parse error near `\n'

┌──(kali㉿kali)-[~/picoctf/t4forensic/SecretofthePolyglot]
└─$ strange file? <br>
zsh: parse error near `\n'

┌──(kali㉿kali)-[~/picoctf/t4forensic/SecretofthePolyglot]
└─$ Download the suspicious file here.
Download: command not found

┌──(kali㉿kali)-[~/picoctf/t4forensic/SecretofthePolyglot]
└─$ 

┌──(kali㉿kali)-[~/picoctf/t4forensic/SecretofthePolyglot]
└─$ # Solution

┌──(kali㉿kali)-[~/picoctf/t4forensic/SecretofthePolyglot]
└─$ 

┌──(kali㉿kali)-[~/picoctf/t4forensic/SecretofthePolyglot]
└─$ Here is a better formatted version of this writeup on [picoCTF Solutions website](https://picoctfsolutions.com/picoctf-2024-secret-of-the-polyglot).
zsh: bad pattern: [picoCTF

┌──(kali㉿kali)-[~/picoctf/t4forensic/SecretofthePolyglot]
└─$ 

┌──(kali㉿kali)-[~/picoctf/t4forensic/SecretofthePolyglot]
└─$ To get the file: `wget https://artifacts.picoctf.net/c_titan/9/flag2of2-final.pdf`
--2026-03-24 22:37:09--  https://artifacts.picoctf.net/c_titan/9/flag2of2-final.pdf
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.161.55.26, 3.161.55.64, 3.161.55.100, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.161.55.26|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 3362 (3.3K) [application/octet-stream]
Saving to: ‘flag2of2-final.pdf.1’

flag2of2-final.pdf.1                      100%[=====================================================================================>]   3.28K  --.-KB/s    in 0s      

2026-03-24 22:37:10 (72.2 MB/s) - ‘flag2of2-final.pdf.1’ saved [3362/3362]

To: command not found
 
┌──(kali㉿kali)-[~/picoctf/t4forensic/SecretofthePolyglot]
└─$ 

┌──(kali㉿kali)-[~/picoctf/t4forensic/SecretofthePolyglot]
└─$ First, open it as a pdf to get the 2nd part of the flag. Through the command line, it could be done with `pdftotext` command.
pdftotext version 25.03.0
Copyright 2005-2025 The Poppler Developers - http://poppler.freedesktop.org
Copyright 1996-2011, 2022 Glyph & Cog, LLC
Usage: pdftotext [options] <PDF-file> [<text-file>]
  -f <int>             : first page to convert
  -l <int>             : last page to convert
  -r <fp>              : resolution, in DPI (default is 72)
  -x <int>             : x-coordinate of the crop area top left corner
  -y <int>             : y-coordinate of the crop area top left corner
  -W <int>             : width of crop area in pixels (default is 0)
  -H <int>             : height of crop area in pixels (default is 0)
  -layout              : maintain original physical layout
  -fixed <fp>          : assume fixed-pitch (or tabular) text
  -raw                 : keep strings in content stream order
  -nodiag              : discard diagonal text
  -htmlmeta            : generate a simple HTML file, including the meta information
  -tsv                 : generate a simple TSV file, including the meta information for bounding boxes
  -enc <string>        : output text encoding name
  -listenc             : list available encodings
  -eol <string>        : output end-of-line convention (unix, dos, or mac)
  -nopgbrk             : don't insert page breaks between pages
  -bbox                : output bounding box for each word and page size to html. Sets -htmlmeta
  -bbox-layout         : like -bbox but with extra layout bounding box data.  Sets -htmlmeta
  -cropbox             : use the crop box rather than media box
  -colspacing <fp>     : how much spacing we allow after a word before considering adjacent text to be a new column, as a fraction of the font size (default is 0.7, old releases had a 0.3 default)
  -opw <string>        : owner password (for encrypted files)
  -upw <string>        : user password (for encrypted files)
  -q                   : don't print any messages or errors
  -v                   : print copyright and version info
  -h                   : print usage information
  -help                : print usage information
  --help               : print usage information
  -?                   : print usage information
First,: command not found
 
┌──(kali㉿kali)-[~/picoctf/t4forensic/SecretofthePolyglot]
└─$ 

┌──(kali㉿kali)-[~/picoctf/t4forensic/SecretofthePolyglot]
└─$ First to install use, `sudo apt install poppler-utils`, then to run the command:

WARNING: apt does not have a stable CLI interface. Use with caution in scripts.

Command 'First' not found, did you mean:
  command 'first' from deb yagiuda
Try: sudo apt install <deb name>

┌──(kali㉿kali)-[~/picoctf/t4forensic/SecretofthePolyglot]
└─$ `pdftotext flag2of2-final.pdf`

┌──(kali㉿kali)-[~/picoctf/t4forensic/SecretofthePolyglot]
└─$ 

┌──(kali㉿kali)-[~/picoctf/t4forensic/SecretofthePolyglot]
└─$ Then to get the flag use, `cat flag2of2-final.txt`, to get this: `1n_pn9_&_pdf_7f9...}`
zsh: parse error near `}'
zsh: parse error in command substitution
    
┌──(kali㉿kali)-[~/picoctf/t4forensic/SecretofthePolyglot]
└─$ 

┌──(kali㉿kali)-[~/picoctf/t4forensic/SecretofthePolyglot]
└─$ When looking at the file with `cat flag2of2-final.pdf`, looking through the hex, or running the file command with `file flag2of2-final.pdf` it could be seen that the magic bytes show the file as a png. By changing the name with this command, `mv flag2of2-final.pdf flag2of2-final.png`, the file could be opened as a png and the first part of the flag could be read.
Command 'When' not found, did you mean:
  command 'when' from deb when
Try: sudo apt install <deb name>
  
┌──(kali㉿kali)-[~/picoctf/t4forensic/SecretofthePolyglot]
└─$ 

┌──(kali㉿kali)-[~/picoctf/t4forensic/SecretofthePolyglot]
└─$ Doing it through the command line Optical Character Recognition (ocr) tools could be used. To download a well-known one, `sudo apt install gocr`, then `gocr flag2of2-final.png | tr -d "\n"` to remove the new lines and paste the contents. This gives `piconF{f1u3n7_` which is mostly right other than it regonizing an n instead of CT. Overall it should be `picoCTF{f1u3n7_`.

WARNING: apt does not have a stable CLI interface. Use with caution in scripts.


Flag: `picoCTF{f1u3n7_1n_pn9_&_pdf_7f9...}`^[[201~

piconF{f1u3n7_: command not found
picoCTF{f1u3n7_: command not found
Doing: command not found

┌──(kali㉿kali)-[~/picoctf/t4forensic/SecretofthePolyglot]
└─$ cat flag2of2-final.pdf
cat: flag2of2-final.pdf: No such file or directory

┌──(kali㉿kali)-[~/picoctf/t4forensic/SecretofthePolyglot]
└─$ file flag2of2-final.pdf
flag2of2-final.pdf: cannot open `flag2of2-final.pdf' (No such file or directory)

┌──(kali㉿kali)-[~/picoctf/t4forensic/SecretofthePolyglot]
└─$ file flag2of2-final.pdf
flag2of2-final.pdf: cannot open `flag2of2-final.pdf' (No such fil
```

picoCTF{f1u3n7_1n_pn9_&_pdf_2a6a1ea8}

## Notas

[](https://github.com/neylar-11/notas-hacking-EneJun26/blob/main/picoCTF/16.1%20-%20Tarea%204%20Forensic/7%20-%20Secret%20of%20the%20Polyglot.md#notas)

## Referencias
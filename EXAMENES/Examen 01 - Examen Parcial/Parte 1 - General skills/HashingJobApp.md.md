## Descripción

[](https://github.com/neylar-11/notas-hacking-EneJun26/blob/main/picoCTF/Examen1/General%20Skills/2%20-%20HashingJobApp.md#descripci%C3%B3n)

If you want to hash with the best, beat this test!`nc saturn.picoctf.net 53044`

## Solución

[](https://github.com/neylar-11/notas-hacking-EneJun26/blob/main/picoCTF/Examen1/General%20Skills/2%20-%20HashingJobApp.md#soluci%C3%B3n)

### Solucion

[](https://github.com/neylar-11/notas-hacking-EneJun26/blob/main/picoCTF/Examen1/General%20Skills/2%20-%20HashingJobApp.md#solucion)

- MD5 1:[https://gchq.github.io/CyberChef/#recipe=MD5()&input=Q2xpbnQgRWFzdHdvb2Q](https://gchq.github.io/CyberChef/#recipe=MD5\(\)&input=Q2xpbnQgRWFzdHdvb2Q)
- MD5 2:[https://gchq.github.io/CyberChef/#recipe=MD5()&input=YSB0cmVlaG91c2U](https://gchq.github.io/CyberChef/#recipe=MD5\(\)&input=YSB0cmVlaG91c2U)
- MD5 3: [https://gchq.github.io/CyberChef/#recipe=MD5()&input=SGVsZW4gS2VsbGVy](https://gchq.github.io/CyberChef/#recipe=MD5\(\)&input=SGVsZW4gS2VsbGVy)

```
MaxSteel09-picoctf@webshell:~$ nc saturn.picoctf.net 53044
Please md5 hash the text between quotes, excluding the quotes: 'communists'
Answer: 
^C
neylar11-picoctf@webshell:~$ nc saturn.picoctf.net 53044
Please md5 hash the text between quotes, excluding the quotes: 'Clint Eastwood'
Answer: 
b84954cb41831fa842dd69f6e1836b6e
b84954cb41831fa842dd69f6e1836b6e
Correct.
Please md5 hash the text between quotes, excluding the quotes: 'a treehouse'
Answer: 
98b0ee4dfd8e04322c60bd32481b512e
98b0ee4dfd8e04322c60bd32481b512e
Correct.
Please md5 hash the text between quotes, excluding the quotes: 'Helen Keller'
Answer: 
c0aac1554fe46e67f218df124c318054
c0aac1554fe46e67f218df124c318054
Correct.
picoCTF{4ppl1c4710n_r3c31v3d_bf2ceb02}
```

picoCTF{4ppl1c4710n_r3c31v3d_bf2ceb02}

## Notas

[](https://github.com/neylar-11/notas-hacking-EneJun26/blob/main/picoCTF/Examen1/General%20Skills/2%20-%20HashingJobApp.md#notas)

- Un **hash** es una función que **toma cualquier texto o archivo y lo convierte en una cadena fija de caracteres**. **MD5** significa **Message Digest Algorithm. Características:
    
- produce **128 bits**
    
- se muestra como **32 caracteres hexadecimales**
    

## Referencias
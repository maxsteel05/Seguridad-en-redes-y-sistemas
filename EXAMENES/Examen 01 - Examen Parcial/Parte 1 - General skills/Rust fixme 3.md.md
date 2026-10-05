## Descripción

[](https://github.com/neylar-11/notas-hacking-EneJun26/blob/main/picoCTF/Examen1/General%20Skills/5%20-%20Rust%20fixme%203.md#descripci%C3%B3n)

Have you heard of Rust? Fix the syntax errors in this Rust file to print the flag!Download the Rust code [here](https://challenge-files.picoctf.net/c_verbal_sleep/dcdaf491b35c1d0f5075e9583edbbb7aaea1dffb6ad32bc000e4d87b5200ff7b/fixme3.tar.gz).

## Solución

[](https://github.com/neylar-11/notas-hacking-EneJun26/blob/main/picoCTF/Examen1/General%20Skills/5%20-%20Rust%20fixme%203.md#soluci%C3%B3n)

### Solucion

[](https://github.com/neylar-11/notas-hacking-EneJun26/blob/main/picoCTF/Examen1/General%20Skills/5%20-%20Rust%20fixme%203.md#solucion)

```
┌──(kali㉿kali)-[~]
└─$ cd picoctf
      
┌──(kali㉿kali)-[~/picoctf]
└─$ cd examen1
     
┌──(kali㉿kali)-[~/picoctf/examen1]
└─$ mkdir fixme3 
mkdir: cannot create directory ‘fixme3’: File exists

┌──(kali㉿kali)-[~/picoctf/examen1]
└─$ cd fixme3 

┌──(kali㉿kali)-[~/picoctf/examen1/fixme3]
└─$ wget https://challenge-files.picoctf.net/c_verbal_sleep/dcdaf491b35c1d0f5075e9583edbbb7aaea1dffb6ad32bc000e4d87b5200ff7b/fixme3.tar.gz
--2026-03-10 22:27:46--  https://challenge-files.picoctf.net/c_verbal_sleep/dcdaf491b35c1d0f5075e9583edbbb7aaea1dffb6ad32bc000e4d87b5200ff7b/fixme3.tar.gz
Resolving challenge-files.picoctf.net (challenge-files.picoctf.net)... 3.161.44.61, 3.161.44.22, 3.161.44.84, ...
Connecting to challenge-files.picoctf.net (challenge-files.picoctf.net)|3.161.44.61|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 1776 (1.7K) [application/octet-stream]
Saving to: ‘fixme3.tar.gz’

fixme3.tar.gz                              100%[=======================================================================================>]   1.73K  --.-KB/s    in 0s      

2026-03-10 22:27:47 (9.32 MB/s) - ‘fixme3.tar.gz’ saved [1776/1776]

┌──(kali㉿kali)-[~/picoctf/examen1/fixme3]
└─$ gzip -d fixme3.tar.gz                                                             
┌──(kali㉿kali)-[~/picoctf/examen1/fixme3]
└─$ tar xpf fixme3.tar                                                             
┌──(kali㉿kali)-[~/picoctf/examen1/fixme3]
└─$ ls                                                                                                                                    
Cargo.lock  Cargo.toml  fixme3  fixme3.tar  src

┌──(kali㉿kali)-[~/picoctf/examen1/fixme3]
└─$ cd fixme3                                                                      

┌──(kali㉿kali)-[~/picoctf/examen1/fixme3/fixme3]
└─$ ls
Cargo.lock  Cargo.toml  src

┌──(kali㉿kali)-[~/picoctf/examen1/fixme3/fixme3]
└─$ vi src/main.rs

┌──(kali㉿kali)-[~/picoctf/examen1/fixme3/fixme3]
└─$ cargo run main
   Compiling crossbeam-utils v0.8.20
   Compiling rayon-core v1.12.1
   Compiling either v1.13.0
   Compiling crossbeam-epoch v0.9.18
   Compiling crossbeam-deque v0.8.5
   Compiling rayon v1.10.0
   Compiling xor_cryptor v1.2.3
   Compiling rust_proj v0.1.0 (/home/kali/picoctf/examen1/fixme3/fixme3)
    Finished `dev` profile [unoptimized + debuginfo] target(s) in 5.44s
     Running `target/debug/rust_proj main`
Using memory unsafe languages is a: PARTY FOUL! Here is your flag: 

picoCTF{n0w_y0uv3_f1x3d_1h3m_411}

┌──(kali㉿kali)-[~/picoctf/examen1/fixme3/fixme3]
└─$ 

```

picoCTF{n0w_y0uv3_f1x3d_1h3m_411}

## Notas

[](https://github.com/neylar-11/notas-hacking-EneJun26/blob/main/picoCTF/Examen1/General%20Skills/5%20-%20Rust%20fixme%203.md#notas)

- `unsafe` es una **palabra clave que permite ejecutar código que Rust normalmente no dejaría correr porque puede ser peligroso para la memoria**.
- solo era quitarle los comentarios

## Referencias
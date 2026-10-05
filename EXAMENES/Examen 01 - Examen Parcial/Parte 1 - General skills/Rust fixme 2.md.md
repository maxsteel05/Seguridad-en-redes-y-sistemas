## Descripción

[](https://github.com/neylar-11/notas-hacking-EneJun26/blob/main/picoCTF/Examen1/General%20Skills/4%20-%20Rust%20fixme%202.md#descripci%C3%B3n)

The Rust saga continues? I ask you, can I borrow that, pleeeeeaaaasseeeee?Download the Rust code [here](https://challenge-files.picoctf.net/c_verbal_sleep/babfbee79718a6363826ba86300173ffde6d81577e9dd07d4130c53a7eecf6c3/fixme2.tar.gz).

## Solución

[](https://github.com/neylar-11/notas-hacking-EneJun26/blob/main/picoCTF/Examen1/General%20Skills/4%20-%20Rust%20fixme%202.md#soluci%C3%B3n)

### Solucion

[](https://github.com/neylar-11/notas-hacking-EneJun26/blob/main/picoCTF/Examen1/General%20Skills/4%20-%20Rust%20fixme%202.md#solucion)

```
┌──(kali㉿kali)-[~/picoctf/examen1]
└─$ wget https://challenge-files.picoctf.net/c_verbal_sleep/babfbee79718a6363826ba86300173ffde6d81577e9dd07d4130c53a7eecf6c3/fixme2.tar.gz
--2026-03-10 21:49:27--  https://challenge-files.picoctf.net/c_verbal_sleep/babfbee79718a6363826ba86300173ffde6d81577e9dd07d4130c53a7eecf6c3/fixme2.tar.gz
Resolving challenge-files.picoctf.net (challenge-files.picoctf.net)... 3.161.44.61, 3.161.44.22, 3.161.44.103, ...
Connecting to challenge-files.picoctf.net (challenge-files.picoctf.net)|3.161.44.61|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 1585 (1.5K) [application/octet-stream]
Saving to: ‘fixme2.tar.gz’

fixme2.tar.gz                              100%[=======================================================================================>]   1.55K  --.-KB/s    in 0s      

2026-03-10 21:49:28 (11.7 MB/s) - ‘fixme2.tar.gz’ saved [1585/1585]
  
┌──(kali㉿kali)-[~/picoctf/examen1]
└─$ gzip -d fixme2.tar.gz                                                                                                                 
gzip: fixme2.tar already exists; do you wish to overwrite (y or n)? y

┌──(kali㉿kali)-[~/picoctf/examen1]
└─$ tar xpf fixme2.tar                                                               
┌──(kali㉿kali)-[~/picoctf/examen1]
└─$ cd fixme2                                                                      
┌──(kali㉿kali)-[~/picoctf/examen1/fixme2]
└─$ ls                                                                                                                                    
Cargo.lock  Cargo.toml  src  target

┌──(kali㉿kali)-[~/picoctf/examen1/fixme2]
└─$ vi src/main.rs                                                                                                                        

zsh: suspended  vi src/main.rs

┌──(kali㉿kali)-[~/picoctf/examen1/fixme2]
└─$ cargo run main                                                                                                                        
   Compiling rust_proj v0.1.0 (/home/kali/picoctf/examen1/fixme2)
error[E0596]: cannot borrow `*borrowed_string` as mutable, as it is behind a `&` reference
 --> src/main.rs:9:5
  |
9 |     borrowed_string.push_str("PARTY FOUL! Here is your flag: ");
  |     ^^^^^^^^^^^^^^^ `borrowed_string` is a `&` reference, so the data it refers to cannot be borrowed as mutable
  |
help: consider changing this to be a mutable reference
  |
3 | fn decrypt(encrypted_buffer:Vec<u8>, borrowed_string: &mut String){ // How do we pass values to a function that we want to change?
  |                                                        +++

error[E0596]: cannot borrow `*borrowed_string` as mutable, as it is behind a `&` reference
  --> src/main.rs:20:5
   |
20 |     borrowed_string.push_str(&String::from_utf8_lossy(&decrypted_buffer));
   |     ^^^^^^^^^^^^^^^ `borrowed_string` is a `&` reference, so the data it refers to cannot be borrowed as mutable
   |
help: consider changing this to be a mutable reference
   |
 3 | fn decrypt(encrypted_buffer:Vec<u8>, borrowed_string: &mut String){ // How do we pass values to a function that we want to change?
   |                                                        +++

For more information about this error, try `rustc --explain E0596`.
error: could not compile `rust_proj` (bin "rust_proj") due to 2 previous errors

┌──(kali㉿kali)-[~/picoctf/examen1/fixme2]
└─$ cargo run main
   Compiling rust_proj v0.1.0 (/home/kali/picoctf/examen1/fixme2)
error[E0308]: mismatched types
  --> src/main.rs:35:31
   |
35 |     decrypt(encrypted_buffer, &party_foul); // Is this the correct way to pass a value to a function so that it can be changed?
   |     -------                   ^^^^^^^^^^^ types differ in mutability
   |     |
   |     arguments to this function are incorrect
   |
   = note: expected mutable reference `&mut String`
                      found reference `&String`
note: function defined here
  --> src/main.rs:3:8
   |
 3 |     fn decrypt(encrypted_buffer:Vec<u8>, borrowed_string: &mut String){ // How do we pass values to a function that we want to change?
   |        ^^^^^^^                           ----------------------------

For more information about this error, try `rustc --explain E0308`.
error: could not compile `rust_proj` (bin "rust_proj") due to 1 previous error
                                                                                                                                                                           
┌──(kali㉿kali)-[~/picoctf/examen1/fixme2]
└─$ vi src/main.rs
                                                                                                                                                                           
┌──(kali㉿kali)-[~/picoctf/examen1/fixme2]
└─$ cargo run main
   Compiling rust_proj v0.1.0 (/home/kali/picoctf/examen1/fixme2)
error[E0596]: cannot borrow `party_foul` as mutable, as it is not declared as mutable
  --> src/main.rs:35:31
   |
35 |     decrypt(encrypted_buffer, &mut party_foul); // Is this the correct way to pass a value to a function so that it can be changed?
   |                               ^^^^^^^^^^^^^^^ cannot borrow as mutable
   |
help: consider changing this to be mutable
   |
34 |     let mut party_foul = String::from("Using memory unsafe languages is a: "); // Is this variable changeable?
   |         +++

For more information about this error, try `rustc --explain E0596`.
error: could not compile `rust_proj` (bin "rust_proj") due to 1 previous error

┌──(kali㉿kali)-[~/picoctf/examen1/fixme2]
└─$ !v

┌──(kali㉿kali)-[~/picoctf/examen1/fixme2]
└─$ vi src/main.rs

┌──(kali㉿kali)-[~/picoctf/examen1/fixme2]
└─$ cargo run main
   Compiling rust_proj v0.1.0 (/home/kali/picoctf/examen1/fixme2)
    Finished `dev` profile [unoptimized + debuginfo] target(s) in 0.35s
     Running `target/debug/rust_proj main`
Using memory unsafe languages is a: PARTY FOUL! Here is your flag: picoCTF{4r3_y0u_h4v1n5_fun_y31?}

┌──(kali㉿kali)-[~/picoctf/examen1/fixme2]
└─$ 

```

picoCTF{4r3_y0u_h4v1n5_fun_y31?}

## Notas

[](https://github.com/neylar-11/notas-hacking-EneJun26/blob/main/picoCTF/Examen1/General%20Skills/4%20-%20Rust%20fixme%202.md#notas)

- vi: para abrir la carpeta
- cargo run: ejecutar el programa
- `mut` es una palabra clave de **Rust** que significa **“mutable”**, es decir, que **una variable puede cambiar su valor**.
- solo era agregar los mut faltantes

## Referencias
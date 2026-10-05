## Descripción

[](https://github.com/neylar-11/notas-hacking-EneJun26/blob/main/picoCTF/Examen1/General%20Skills/3%20-%20Rust%20fixme%201.md#descripci%C3%B3n)

¿Has oído hablar de Rust? ¡Corrige los errores de sintaxis en este archivo de Rust para imprimir la bandera!Descargue el código de Rust [aquí](https://challenge-files.picoctf.net/c_verbal_sleep/3f0e13f541928f420d9c8c96b06d4dbf7b2fa18b15adbd457108e8c80a1f5883/fixme1.tar.gz) .

## Solución

[](https://github.com/neylar-11/notas-hacking-EneJun26/blob/main/picoCTF/Examen1/General%20Skills/3%20-%20Rust%20fixme%201.md#soluci%C3%B3n)

### Solucion

[](https://github.com/neylar-11/notas-hacking-EneJun26/blob/main/picoCTF/Examen1/General%20Skills/3%20-%20Rust%20fixme%201.md#solucion)

```
┌──(kali㉿kali)-[~]
└─$ wget https://challenge-files.picoctf.net/c_verbal_sleep/3f0e13f541928f420d9c8c96b06d4dbf7b2fa18b15adbd457108e8c80a1f5883/fixme1.tar.gz
--2026-03-08 20:24:13--  https://challenge-files.picoctf.net/c_verbal_sleep/3f0e13f541928f420d9c8c96b06d4dbf7b2fa18b15adbd457108e8c80a1f5883/fixme1.tar.gz
Resolving challenge-files.picoctf.net (challenge-files.picoctf.net)... 3.161.44.22, 3.161.44.103, 3.161.44.61, ...
Connecting to challenge-files.picoctf.net (challenge-files.picoctf.net)|3.161.44.22|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 1415 (1.4K) [application/octet-stream]
Saving to: ‘fixme1.tar.gz’

fixme1.tar.gz      100%[===============>]   1.38K  --.-KB/s    in 0s      

2026-03-08 20:24:14 (43.3 MB/s) - ‘fixme1.tar.gz’ saved [1415/1415]

 
┌──(kali㉿kali)-[~]
└─$ tar -xvzf fixme1.tar.gz
fixme1/
fixme1/Cargo.toml
fixme1/Cargo.lock
fixme1/src/
fixme1/src/main.rs
    
┌──(kali㉿kali)-[~]
└─$ cd fixme1
   
┌──(kali㉿kali)-[~/fixme1]
└─$ cargo build
Command 'cargo' not found, but can be installed with:
sudo apt install cargo 
sudo apt install rustup

                                                                           
┌──(kali㉿kali)-[~/fixme1]
└─$ sudo apt install cargo                                                
[sudo] password for kali: 
Error: Unable to locate package cargo
                                                                           
┌──(kali㉿kali)-[~/fixme1]
└─$ sudo apt update       
Get:1 http://kali.download/kali kali-rolling InRelease [34.0 kB]
Get:2 http://kali.download/kali kali-rolling/main amd64 Packages [20.8 MB]
Get:3 http://kali.download/kali kali-rolling/main amd64 Contents (deb) [52.6 MB]
Get:4 http://kali.download/kali kali-rolling/contrib amd64 Packages [116 kB]
Get:5 http://kali.download/kali kali-rolling/contrib amd64 Contents (deb) [274 kB]
Get:6 http://kali.download/kali kali-rolling/non-free amd64 Packages [183 kB]
Get:7 http://kali.download/kali kali-rolling/non-free amd64 Contents (deb) [879 kB]
Get:8 http://kali.download/kali kali-rolling/non-free-firmware amd64 Packages [14.3 kB]
Get:9 http://kali.download/kali kali-rolling/non-free-firmware amd64 Contents (deb) [33.8 kB]
Fetched 74.9 MB in 15s (4,907 kB/s)                                       
1701 packages can be upgraded. Run 'apt list --upgradable' to see them.
                                                                           
┌──(kali㉿kali)-[~/fixme1]
└─$ sudo apt install cargo
Installing:                     
  cargo
                                                                           
Installing dependencies:
  clang-21                libllvm21         llvm-21-dev
  clang-tools-21          libmbedtls21      llvm-21-linker-tools           
  libclang-common-21-dev  libmbedx509-7     llvm-21-runtime                
  libclang-cpp21          libstd-rust-1.91  llvm-21-tools                  
  libclang-rt-21-dev      libstd-rust-dev   rust-llvm                      
  libclang1-21            lld-21            rustc                          
  libgit2-1.9             llvm-21                                          
                                                                           
Suggested packages:
  cargo-doc  clang-21-doc  wasi-libc  llvm-21-doc

Summary:
  Upgrading: 0, Installing: 21, Removing: 0, Not Upgrading: 1701
  Download size: 207 MB
  Space needed: 1,160 MB / 61.6 GB available

Continue? [Y/n] y
Get:1 http://kali.download/kali kali-rolling/main amd64 libmbedx509-7 amd64 3.6.5-0.1 [152 kB]
Get:2 http://kali.download/kali kali-rolling/main amd64 libmbedtls21 amd64 3.6.5-0.1 [246 kB]
Get:3 http://http.kali.org/kali kali-rolling/main amd64 libgit2-1.9 amd64 1.9.2+ds-6 [560 kB]
Get:5 http://http.kali.org/kali kali-rolling/main amd64 libstd-rust-1.91 amd64 1.91.1+dfsg1-1 [21.3 MB]
Get:10 http://http.kali.org/kali kali-rolling/main amd64 llvm-21-linker-tools amd64 1:21.1.8-3+b1 [1,280 kB]
Get:4 http://http.kali.org/kali kali-rolling/main amd64 libllvm21 amd64 1:21.1.8-3+b1 [28.3 MB]
Get:6 http://http.kali.org/kali kali-rolling/main amd64 libstd-rust-dev amd64 1.91.1+dfsg1-1 [38.8 MB]
Get:15 http://http.kali.org/kali kali-rolling/main amd64 libclang-rt-21-dev amd64 1:21.1.8-3+b1 [3,909 kB]
Get:8 http://http.kali.org/kali kali-rolling/main amd64 libclang-cpp21 amd64 1:21.1.8-3+b1 [12.8 MB]
Get:9 http://http.kali.org/kali kali-rolling/main amd64 libclang-common-21-dev amd64 1:21.1.8-3+b1 [799 kB]
Get:11 http://http.kali.org/kali kali-rolling/main amd64 libclang1-21 amd64 1:21.1.8-3+b1 [7,731 kB]
Get:12 http://http.kali.org/kali kali-rolling/main amd64 clang-21 amd64 1:21.1.8-3+b1 [170 kB]
Get:13 http://http.kali.org/kali kali-rolling/main amd64 cargo amd64 1.91.1+dfsg1-1 [7,246 kB]
Get:14 http://http.kali.org/kali kali-rolling/main amd64 clang-tools-21 amd64 1:21.1.8-3+b1 [8,986 kB]
Get:17 http://http.kali.org/kali kali-rolling/main amd64 llvm-21-runtime amd64 1:21.1.8-3+b1 [570 kB]
Get:18 http://http.kali.org/kali kali-rolling/main amd64 llvm-21 amd64 1:21.1.8-3+b1 [18.6 MB]
Get:19 http://http.kali.org/kali kal3,909 kB 75%] [4 libllvm21 6,030 kB/28.i-rolling/main amd64 llvm-21-tools amd64 1:21.1.8-3+b1 [558 kB]
Get:20 http://http.kali.org/kali kali-rolling/main amd64 llvm-21-dev amd64 1:21.1.8-3+b1 [47.5 MB]
Get:16 http://http.kali.org/kali kali-rolling/main amd64 lld-21 amd64 1:21.1.8-3+b1 [1,462 kB]                                                          
Get:7 http://http.kali.org/kali kali[4 libllvm21 7,875 kB/28.3 MB 28%] [20  -rolling/main amd64 rustc amd64 1.91.1+dfsg1-1 [4,553 kB]
Get:21 http://http.kali.org/kali kali-rolling/main amd64 rust-llvm amd64 1.91.1+dfsg1-1 [1,876 kB]
Fetched 207 MB in 34s (6,097 kB/s) 
debconf: unable to initialize frontend: Dialog
debconf: (Dialog frontend requires a screen at least 13 lines tall and 31 columns wide.)
debconf: falling back to frontend: Readline
Selecting previously unselected package libmbedx509-7:amd64.
(Reading database ... 422160 files and directories currently installed.)
Preparing to unpack .../00-libmbedx509-7_3.6.5-0.1_amd64.deb ...
Unpacking libmbedx509-7:amd64 (3.6.5-0.1) ...
Selecting previously unselected package libmbedtls21:amd64.
Preparing to unpack .../01-libmbedtls21_3.6.5-0.1_amd64.deb ...
Unpacking libmbedtls21:amd64 (3.6.5-0.1) ...
Selecting previously unselected package libgit2-1.9:amd64.
Preparing to unpack .../02-libgit2-1.9_1.9.2+ds-6_amd64.deb ...
Unpacking libgit2-1.9:amd64 (1.9.2+ds-6) ...
Selecting previously unselected package libllvm21:amd64.
Preparing to unpack .../03-libllvm21_1%3a21.1.8-3+b1_amd64.deb ...
Unpacking libllvm21:amd64 (1:21.1.8-3+b1) ...
Selecting previously unselected package libstd-rust-1.91:amd64.
Preparing to unpack .../04-libstd-rust-1.91_1.91.1+dfsg1-1_amd64.deb ...
Unpacking libstd-rust-1.91:amd64 (1.91.1+dfsg1-1) ...
Selecting previously unselected package libstd-rust-dev:amd64.
Preparing to unpack .../05-libstd-rust-dev_1.91.1+dfsg1-1_amd64.deb ...
Unpacking libstd-rust-dev:amd64 (1.91.1+dfsg1-1) ...
Selecting previously unselected package rustc.
Preparing to unpack .../06-rustc_1.91.1+dfsg1-1_amd64.deb ...
Unpacking rustc (1.91.1+dfsg1-1) ...
Selecting previously unselected package libclang-cpp21.
Preparing to unpack .../07-libclang-cpp21_1%3a21.1.8-3+b1_amd64.deb ...
Unpacking libclang-cpp21 (1:21.1.8-3+b1) ...
Selecting previously unselected package libclang-common-21-dev:amd64.
Preparing to unpack .../08-libclang-common-21-dev_1%3a21.1.8-3+b1_amd64.deb ...
Unpacking libclang-common-21-dev:amd64 (1:21.1.8-3+b1) ...
Selecting previously unselected package llvm-21-linker-tools.
Preparing to unpack .../09-llvm-21-linker-tools_1%3a21.1.8-3+b1_amd64.deb ...
Unpacking llvm-21-linker-tools (1:21.1.8-3+b1) ...
Selecting previously unselected package libclang1-21.
Preparing to unpack .../10-libclang1-21_1%3a21.1.8-3+b1_amd64.deb ...
Unpacking libclang1-21 (1:21.1.8-3+b1) ...
Selecting previously unselected package clang-21.
Preparing to unpack .../11-clang-21_1%3a21.1.8-3+b1_amd64.deb ...
Unpacking clang-21 (1:21.1.8-3+b1) ...
Selecting previously unselected package cargo.
Preparing to unpack .../12-cargo_1.91.1+dfsg1-1_amd64.deb ...
Unpacking cargo (1.91.1+dfsg1-1) ...
Selecting previously unselected package clang-tools-21.
Preparing to unpack .../13-clang-tools-21_1%3a21.1.8-3+b1_amd64.deb ...
Unpacking clang-tools-21 (1:21.1.8-3+b1) ...
Selecting previously unselected package libclang-rt-21-dev.
Preparing to unpack .../14-libclang-rt-21-dev_1%3a21.1.8-3+b1_amd64.deb ...
Unpacking libclang-rt-21-dev (1:21.1.8-3+b1) ...
Selecting previously unselected package lld-21.
Preparing to unpack .../15-lld-21_1%3a21.1.8-3+b1_amd64.deb ...
Unpacking lld-21 (1:21.1.8-3+b1) ...
Selecting previously unselected package llvm-21-runtime.
Preparing to unpack .../16-llvm-21-runtime_1%3a21.1.8-3+b1_amd64.deb ...
Unpacking llvm-21-runtime (1:21.1.8-3+b1) ...
Selecting previously unselected package llvm-21.
Preparing to unpack .../17-llvm-21_1%3a21.1.8-3+b1_amd64.deb ...
Unpacking llvm-21 (1:21.1.8-3+b1) ...
Selecting previously unselected package llvm-21-tools.
Preparing to unpack .../18-llvm-21-tools_1%3a21.1.8-3+b1_amd64.deb ...
Unpacking llvm-21-tools (1:21.1.8-3+b1) ...
Selecting previously unselected package llvm-21-dev.
Preparing to unpack .../19-llvm-21-dev_1%3a21.1.8-3+b1_amd64.deb ...
Unpacking llvm-21-dev (1:21.1.8-3+b1) ...
Selecting previously unselected package rust-llvm.
Preparing to unpack .../20-rust-llvm_1.91.1+dfsg1-1_amd64.deb ...
Unpacking rust-llvm (1.91.1+dfsg1-1) ...
Setting up libmbedx509-7:amd64 (3.6.5-0.1) ...
Setting up libllvm21:amd64 (1:21.1.8-3+b1) ...
Setting up llvm-21-linker-tools (1:21.1.8-3+b1) ...
Setting up libmbedtls21:amd64 (3.6.5-0.1) ...
Setting up libstd-rust-1.91:amd64 (1.91.1+dfsg1-1) ...
Setting up libclang-rt-21-dev (1:21.1.8-3+b1) ...
Setting up libclang-common-21-dev:amd64 (1:21.1.8-3+b1) ...
Setting up libclang1-21 (1:21.1.8-3+b1) ...
Setting up lld-21 (1:21.1.8-3+b1) ...
Setting up libstd-rust-dev:amd64 (1.91.1+dfsg1-1) ...
Setting up libclang-cpp21 (1:21.1.8-3+b1) ...
Setting up llvm-21-tools (1:21.1.8-3+b1) ...
Setting up llvm-21-runtime (1:21.1.8-3+b1) ...
Setting up libgit2-1.9:amd64 (1.9.2+ds-6) ...
Setting up rustc (1.91.1+dfsg1-1) ...
Setting up clang-21 (1:21.1.8-3+b1) ...
Setting up clang-tools-21 (1:21.1.8-3+b1) ...
Setting up cargo (1.91.1+dfsg1-1) ...
Setting up llvm-21 (1:21.1.8-3+b1) ...
Setting up llvm-21-dev (1:21.1.8-3+b1) ...
Setting up rust-llvm (1.91.1+dfsg1-1) ...
Processing triggers for systemd (259~rc1-1) ...
Processing triggers for man-db (2.13.1-1) ...
Processing triggers for kali-menu (2025.4.3) ...
Processing triggers for libc-bin (2.41-12) ...
                                    
┌──(kali㉿kali)-[~/fixme1]
└─$ cargo build
    Updating crates.io index
  Downloaded either v1.13.0
  Downloaded crossbeam-deque v0.8.5
  Downloaded crossbeam-epoch v0.9.18
  Downloaded crossbeam-utils v0.8.20
  Downloaded rayon-core v1.12.1
  Downloaded xor_cryptor v1.2.3
  Downloaded rayon v1.10.0
  Downloaded 7 crates (379.2KiB) in 0.79s
   Compiling crossbeam-utils v0.8.20
   Compiling rayon-core v1.12.1
   Compiling either v1.13.0
   Compiling crossbeam-epoch v0.9.18
   Compiling crossbeam-deque v0.8.5
   Compiling rayon v1.10.0
   Compiling xor_cryptor v1.2.3
   Compiling rust_proj v0.1.0 (/home/kali/fixme1)
error: expected `;`, found keyword `let`
 --> src/main.rs:5:37
  |
5 |     let key = String::from("CSUCKS") //...
  |                                     ^ help: add `;` here
...
8 |     let hex_values = ["41", "30", "20",...
  |     --- unexpected token

error: argument never used
  --> src/main.rs:26:9
   |
25 | ...   ":?", // How do we print out a variable in th...
   |       ---- formatting specifier missing                                                                    
26 | ...   String::from_utf8_lossy(&decrypted_buffer)
   |       ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^ argument never use                                        d                                                                           
   |
help: format specifiers use curly braces, consider adding a format specifier
   |
25 |         ":?{}", // How do we print out a variable in the println function? 
   |            ++

error[E0425]: cannot find value `ret` in this scope
  --> src/main.rs:18:9
   |
18 |         ret; // How do we re...
   |         ^^^ help: a local variable with a similar name exists: `res                                        `                                                                           

For more information about this error, try `rustc --explain E0425`.
error: could not compile `rust_proj` (bin "rust_proj") due to 3 previous errors
   
┌──(kali㉿kali)-[~/fixme1]
└─$ cd src     
  
┌──(kali㉿kali)-[~/fixme1/src]
└─$ nano main.rs

┌──(kali㉿kali)-[~/fixme1/src]
└─$ cargo build 
   Compiling rust_proj v0.1.0 (/home/kali/fixme1)
    Finished `dev` profile [unoptimized + debuginfo] target(s) in 0.36s
   
┌──(kali㉿kali)-[~/fixme1/src]
└─$ cargo run  
    Finished `dev` profile [unoptimized + debuginfo] target(s) in 0.00s
     Running `/home/kali/fixme1/target/debug/rust_proj`
picoCTF{4r3_y0u_4_ru$t4c30n_n0w?}:?
  
┌──(kali㉿kali)-[~/fixme1/src]
└─$ 

```

picoCTF{4r3_y0u_4_ru$t4c30n_n0w?}

## Notas

[](https://github.com/neylar-11/notas-hacking-EneJun26/blob/main/picoCTF/Examen1/General%20Skills/3%20-%20Rust%20fixme%201.md#notas)

`.tar.gz` = archivo **comprimido**

---

tar -xvzf fixme1.tar.gz

Opciones:

- `x` → extraer
    
- `v` → mostrar archivos
    
- `z` → descomprimir gzip
    
- `f` → archivo
    

---

cargo build `cargo` es el **gestor de paquetes y compilador de proyectos Rust**.

---

## Referencias
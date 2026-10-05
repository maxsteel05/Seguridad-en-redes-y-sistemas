## Descripción
We found this [packet capture](https://challenge-files.picoctf.net/c_fickle_tempest/d1e9add4e31989553f239ebf71ba5972f9bed7bd4932f931e14bfba80d75f815/capture.pcap) and [key](https://challenge-files.picoctf.net/c_fickle_tempest/d1e9add4e31989553f239ebf71ba5972f9bed7bd4932f931e14bfba80d75f815/picopico.key). Recover the flag.
### Solucion

```
┌──(kali㉿kali)-[~/picoctf/forensic3/Webnet1]
└─$ wget https://challenge-files.picoctf.net/c_fickle_tempest/d1e9add4e31989553f239ebf71ba5972f9bed7bd4932f931e14bfba80d75f815/capture.pcap
--2026-03-18 10:20:57--  https://challenge-files.picoctf.net/c_fickle_tempest/d1e9add4e31989553f239ebf71ba5972f9bed7bd4932f931e14bfba80d75f815/capture.pcap
Resolving challenge-files.picoctf.net (challenge-files.picoctf.net)... 18.154.206.14, 18.154.206.27, 18.154.206.121, ...
Connecting to challenge-files.picoctf.net (challenge-files.picoctf.net)|18.154.206.14|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 92525 (90K) [application/octet-stream]
Saving to: ‘capture.pcap’

capture.pcap                              100%[=====================================================================================>]  90.36K   441KB/s    in 0.2s    

2026-03-18 10:20:58 (441 KB/s) - ‘capture.pcap’ saved [92525/92525]

┌──(kali㉿kali)-[~/picoctf/forensic3/Webnet1]
└─$ wget https://challenge-files.picoctf.net/c_fickle_tempest/d1e9add4e31989553f239ebf71ba5972f9bed7bd4932f931e14bfba80d75f815/picopico.key
--2026-03-18 10:21:14--  https://challenge-files.picoctf.net/c_fickle_tempest/d1e9add4e31989553f239ebf71ba5972f9bed7bd4932f931e14bfba80d75f815/picopico.key
Resolving challenge-files.picoctf.net (challenge-files.picoctf.net)... 18.154.206.121, 18.154.206.27, 18.154.206.14, ...
Connecting to challenge-files.picoctf.net (challenge-files.picoctf.net)|18.154.206.121|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 1704 (1.7K) [application/octet-stream]
Saving to: ‘picopico.key’

picopico.key                              100%[=====================================================================================>]   1.66K  --.-KB/s    in 0s      

2026-03-18 10:21:15 (73.1 MB/s) - ‘picopico.key’ saved [1704/1704]

┌──(kali㉿kali)-[~/picoctf/forensic3/Webnet1]
└─$ ssldump -r capture.pcap -d -k picopico.key | grep pico -A2
    61 67 3a 20 70 69 63 6f 43 54 46 7b 74 68 69 73    ag: picoCTF{this
    2e 69 73 2e 6e 6f 74 2e 79 6f 75 72 2e 66 6c 61    .is.not.your.fla
    67 2e 61 6e 79 6d 6f 72 65 7d 0d 0a 43 6f 6e 74    g.anymore}..Cont
--
    67 3a 20 70 69 63 6f 43 54 46 7b 74 68 69 73 2e    g: picoCTF{this.
    69 73 2e 6e 6f 74 2e 79 6f 75 72 2e 66 6c 61 67    is.not.your.flag
    2e 61 6e 79 6d 6f 72 65 7d 0d 0a 43 6f 6e 74 65    .anymore}..Conte
--
    Pico-Flag: picoCTF{this.is.not.your.flag.anymore}
    Keep-Alive: timeout=5, max=99
    Connection: Keep-Alive
--
    00 00 00 01 00 00 00 01 70 69 63 6f 43 54 46 7b    ........picoCTF{
    68 6f 6e 65 79 2e 72 6f 61 73 74 65 64 2e 70 65    honey.roasted.pe
    61 6e 75 74 73 7d 00 00 ff e2 02 1c 49 43 43 5f    anuts}......ICC_
Cleaned 4 remaining connection(s) from connection pool

```

picoCTF{honey.roasted.peanuts}

## Notas

## Referencias
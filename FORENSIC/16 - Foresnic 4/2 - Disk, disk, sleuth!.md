## Descripción

Use `srch_strings` from the sleuthkit and some terminal-fu to find a flag in this disk image.[dds1-alpine.flag.img.gz](https://challenge-files.picoctf.net/c_wily_courier/89797cb52348a4096884e4f58164b42a892f8cac34b91d887491f44a5f144718/dds1-alpine.flag.img.gz)

## Solución

```
┌──(kali㉿kali)-[~/picoctf/forensic4/diskdisk]
└─$ gunzip dds1-alpine.flag.img.gz                                                                                                                  
gzip: dds1-alpine.flag.img already exists; do you wish to overwrite (y or n)? y

                                                                                                                                                                        
┌──(kali㉿kali)-[~/picoctf/forensic4/diskdisk]
└─$ 
                                                                                                                                                                        
┌──(kali㉿kali)-[~/picoctf/forensic4/diskdisk]
└─$ fls -o 2048 -r dds1-alpine.flag.img | grep down-at-the-bottom.txt
                                                                                                                                                                        
┌──(kali㉿kali)-[~/picoctf/forensic4/diskdisk]
└─$ fls -r dds1-alpine.flag.img | grep down-at-the-bottom.txt
Cannot determine file system type
                                                                                                                                                                        
┌──(kali㉿kali)-[~/picoctf/forensic4/diskdisk]
└─$ rm dds1-alpine.flag.img
                                                                                                                                                                        
┌──(kali㉿kali)-[~/picoctf/forensic4/diskdisk]
└─$ ls
                                                                                                                                                                        
┌──(kali㉿kali)-[~/picoctf/forensic4/diskdisk]
└─$ wget https://challenge-files.picoctf.net/c_wily_courier/89797cb52348a4096884e4f58164b42a892f8cac34b91d887491f44a5f144718/dds1-alpine.flag.img.gz
--2026-03-23 10:27:57--  https://challenge-files.picoctf.net/c_wily_courier/89797cb52348a4096884e4f58164b42a892f8cac34b91d887491f44a5f144718/dds1-alpine.flag.img.gz
Resolving challenge-files.picoctf.net (challenge-files.picoctf.net)... 3.161.44.61, 3.161.44.103, 3.161.44.22, ...
Connecting to challenge-files.picoctf.net (challenge-files.picoctf.net)|3.161.44.61|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 29768911 (28M) [application/octet-stream]
Saving to: ‘dds1-alpine.flag.img.gz’

dds1-alpine.flag.img.gz                   100%[=====================================================================================>]  28.39M  2.81MB/s    in 14s     

2026-03-23 10:28:27 (2.02 MB/s) - ‘dds1-alpine.flag.img.gz’ saved [29768911/29768911]

                                                                                                                                                                        
┌──(kali㉿kali)-[~/picoctf/forensic4/diskdisk]
└─$ gunzip dds1-alpine.flag.img.gz
                                                                                                                                                                        
┌──(kali㉿kali)-[~/picoctf/forensic4/diskdisk]
└─$ ls -lh dds1-alpine.flag.img
-rw-rw-r-- 1 kali kali 128M Dec 19 14:32 dds1-alpine.flag.img
                                                                                                                                                                        
┌──(kali㉿kali)-[~/picoctf/forensic4/diskdisk]
└─$ mmls dds1-alpine.flag.img
DOS Partition Table
Offset Sector: 0
Units are in 512-byte sectors

      Slot      Start        End          Length       Description
000:  Meta      0000000000   0000000000   0000000001   Primary Table (#0)
001:  -------   0000000000   0000002047   0000002048   Unallocated
002:  000:000   0000002048   0000262143   0000260096   Linux (0x83)
                                                                                                                                                                        
┌──(kali㉿kali)-[~/picoctf/forensic4/diskdisk]
└─$ fls -o 2048 dds1-alpine.flag.img
d/d 10161:      home
d/d 11: lost+found
r/r 12: .dockerenv
d/d 2033:       bin
d/d 8129:       boot
d/d 6097:       dev
d/d 16257:      etc
d/d 28449:      lib
d/d 22353:      media
d/d 24385:      mnt
d/d 26417:      opt
d/d 24386:      proc
d/d 26418:      root
d/d 24387:      run
d/d 26419:      sbin
d/d 20321:      srv
d/d 20322:      sys
d/d 20323:      tmp
d/d 24388:      usr
d/d 20324:      var
V/V 32513:      $OrphanFiles
                                                                                                                                                                        
┌──(kali㉿kali)-[~/picoctf/forensic4/diskdisk]
└─$ fls -r -o 2048 dds1-alpine.flag.img | grep down-at-the-bottom

                                                                                                                                                                        
┌──(kali㉿kali)-[~/picoctf/forensic4/diskdisk]
└─$ fls -r -o 2048 dds1-alpine.flag.img                          
d/d 10161:      home
d/d 11: lost+found
r/r 12: .dockerenv
d/d 2033:       bin
+ -/l * 2049(realloc):  ^
+ l/l 2036:     base64
+ l/l 2037:     bbconfig


┌──(kali㉿kali)-[~/picoctf/forensic4/diskdisk]
└─$ fls -r -o 2048 dds1-alpine.flag.img | grep "*"
+ -/l * 2049(realloc):  ^
+ l/- * 0:      mkdir
+ l/- * 0:      mknod
+ l/- * 0:      mktemp
+ l/- * 0:      more
+ l/- * 0:      mountpoint
+ l/- * 0:      mpstat
+ l/- * 0:      mv
+ l/- * 0:      ping
+ l/- * 0:      ping6
+ l/- * 0:      ps
+ l/- * 0:      reformime
+ l/- * 0:      rev
+ l/- * 0:      rm
+++++ -/l * 2049(realloc):      ^
+++++ r/d * 2(realloc): aegis128l.ko
++++++ -/l * 2049(realloc):     ^
++++++ r/- * 0: nls_cp863.ko
++++++ r/- * 0: nls_cp869.ko
++++++ r/- * 0: nls_cp874.ko
++++++ r/- * 0: nls_cp949.ko
++++++ r/- * 0: nls_iso8859-1.ko
++++++ r/- * 0: nls_iso8859-13.ko
++++++ r/- * 0: nls_iso8859-3.ko
++++++ -/l * 2049(realloc):     ^
++++++ r/- * 0: xt_HL.ko
++++++ r/- * 0: xt_HMARK.ko
++++++ r/- * 0: xt_IDLETIMER.ko
++++++ r/- * 0: xt_NETMAP.ko
++++++ r/- * 0: xt_NFLOG.ko
++++++ r/- * 0: xt_RATEEST.ko
++++++ r/- * 0: xt_SECMARK.ko
++++++ r/- * 0: xt_TCPOPTSTRIP.ko
++++++ r/- * 0: xt_TPROXY.ko
++++++ r/- * 0: xt_addrtype.ko
++++++ r/- * 0: xt_bpf.ko
++++++ r/- * 0: xt_cluster.ko
++++++ r/- * 0: xt_connlimit.ko
++++++ r/- * 0: xt_ecn.ko
++++++ r/- * 0: xt_hashlimit.ko
++++++ r/- * 0: xt_hl.ko
++++++ r/- * 0: xt_iprange.ko
++++++ -/l * 2049(realloc):     ^
++++++ r/d * 2(realloc):        act_connmark.ko
++++++ r/- * 0: sch_cbq.ko
++++++ r/- * 0: sch_choke.ko
++++++ r/- * 0: sch_codel.ko
++++++ r/- * 0: sch_drr.ko
++++++ r/- * 0: sch_dsmark.ko
++++++ r/- * 0: sch_fq_codel.ko
++++++ r/- * 0: sch_gred.ko
+ -/l * 2049(realloc):  ^
+ r/- * 0:      nlplug-findfs
+ l/- * 0:      nologin
+ r/- * 0:      openrc-init
+ r/- * 0:      openrc-run
+ r/- * 0:      openrc-shutdown
+ l/- * 0:      poweroff
+ r/- * 0:      rc
+ r/- * 0:      rc-update
+ l/- * 0:      route
++ -/l * 2049(realloc): ^
++ l/- * 0:     reset
++ l/- * 0:     resize
++ l/- * 0:     sha1sum
++ l/- * 0:     sha512sum
++ l/- * 0:     shuf
++ l/- * 0:     split
++ l/- * 0:     strings
++ l/- * 0:     time
++ l/- * 0:     top
++ l/- * 0:     traceroute
++ l/- * 0:     udhcpc6
++ l/- * 0:     unexpand
++ l/- * 0:     unlink
++ l/- * 0:     unzip
                                                                                                                                                                        
┌──(kali㉿kali)-[~/picoctf/forensic4/diskdisk]
└─$ fls -o 2048 dds1-alpine.flag.img 26418
                                                                                                                                                                        
┌──(kali㉿kali)-[~/picoctf/forensic4/diskdisk]
└─$ fls -r -o 2048 dds1-alpine.flag.img | grep bottom
                                                                                                                                                                        
┌──(kali㉿kali)-[~/picoctf/forensic4/diskdisk]
└─$ srch_strings dds1-alpine.flag.img | grep pico
ffffffff81399ccf t pirq_pico_get
ffffffff81399cee t pirq_pico_set
ffffffff820adb46 t pico_router_probe
  SAY picoCTF{f0r3ns1c4t0r_n30phyt3_5e56e786}

```

picoCTF{f0r3ns1c4t0r_n30phyt3_5e56e786}

## Notas

## Referencias
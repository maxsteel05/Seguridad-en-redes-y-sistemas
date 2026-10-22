## Descripción

Download this disk image and find the flag.Note: if you are using the webshell, download and extract the disk image into `/tmp` not your home directory.

- [Download compressed disk image](https://artifacts.picoctf.net/c/214/disk.flag.img.gz)

## Solución


```
┌──(kali㉿kali)-[~/picoctf/forensic4/Operation_Orchid]
└─$ wget https://artifacts.picoctf.net/c/214/disk.flag.img.gz
--2026-03-23 10:59:42--  https://artifacts.picoctf.net/c/214/disk.flag.img.gz
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 13.225.222.105, 13.225.222.120, 13.225.222.28, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|13.225.222.105|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 44360927 (42M) [application/octet-stream]
Saving to: ‘disk.flag.img.gz’

disk.flag.img.gz                          100%[=====================================================================================>]  42.31M  6.14MB/s    in 9.7s    

2026-03-23 10:59:52 (4.35 MB/s) - ‘disk.flag.img.gz’ saved [44360927/44360927]

                                                                                                                                                                        
┌──(kali㉿kali)-[~/picoctf/forensic4/Operation_Orchid]
└─$ ls
disk.flag.img.gz
                                                                                                                                                                        
┌──(kali㉿kali)-[~/picoctf/forensic4/Operation_Orchid]
└─$ gzip -d disk.flag.img.gz
                                                                                                                                                                        
┌──(kali㉿kali)-[~/picoctf/forensic4/Operation_Orchid]
└─$ ls
disk.flag.img
                                                                                                                                                                        
┌──(kali㉿kali)-[~/picoctf/forensic4/Operation_Orchid]
└─$ mmls disk.flag.img    
DOS Partition Table
Offset Sector: 0
Units are in 512-byte sectors

      Slot      Start        End          Length       Description
000:  Meta      0000000000   0000000000   0000000001   Primary Table (#0)
001:  -------   0000000000   0000002047   0000002048   Unallocated
002:  000:000   0000002048   0000206847   0000204800   Linux (0x83)
003:  000:001   0000206848   0000411647   0000204800   Linux Swap / Solaris x86 (0x82)
004:  000:002   0000411648   0000819199   0000407552   Linux (0x83)
                                                                                                                                                                        
┌──(kali㉿kali)-[~/picoctf/forensic4/Operation_Orchid]
└─$ fls -o 411648 disk.flag.img
d/d 460:        home
d/d 11: lost+found
d/d 12: boot
d/d 13: etc
d/d 81: proc
d/d 82: dev
d/d 83: tmp
d/d 84: lib
d/d 87: var
d/d 96: usr
d/d 106:        bin
d/d 120:        sbin
d/d 466:        media
d/d 470:        mnt
d/d 471:        opt
d/d 472:        root
d/d 473:        run
d/d 475:        srv
d/d 476:        sys
d/d 2041:       swap
V/V 51001:      $OrphanFiles
                                                                                                                                                                        
┌──(kali㉿kali)-[~/picoctf/forensic4/Operation_Orchid]
└─$ fls -r -o 411648 disk.flag.img | grep flag
+ r/r * 1876(realloc):  flag.txt
+ r/r 1782:     flag.txt.enc
                                                                                                                                                                        
┌──(kali㉿kali)-[~/picoctf/forensic4/Operation_Orchid]
└─$ fls -r -o 411648 disk.flag.img | grep pico
                                                                                                                                                                        
┌──(kali㉿kali)-[~/picoctf/forensic4/Operation_Orchid]
└─$ icat -o 411648 disk.flag.img 1782 > flag.txt.enc
                                                                                                                                                                        
┌──(kali㉿kali)-[~/picoctf/forensic4/Operation_Orchid]
└─$ icat -o 411648 disk.flag.img 1876
           -0.881573            34.311733
                                                                                                                                                                        
┌──(kali㉿kali)-[~/picoctf/forensic4/Operation_Orchid]
└─$ file flag.txt.enc
flag.txt.enc: openssl enc'd data with salted password
                                                                                                                                                                        
┌──(kali㉿kali)-[~/picoctf/forensic4/Operation_Orchid]
└─$ fls -r -o 411648 disk.flag.img | grep log
++ r/r 759:     syslog
++ r/r 755:     klogd
+++ l/l 67:     syslog
+ d/d 109:      logrotate.d
++ r/r 766:     klogd
++ r/r 771:     syslog
+++ r/r 32980:  terminology
+++ r/r 32981:  terminology-0.6.1
+++ r/r 32982:  terminology-1.0.0
+++ r/r 32983:  terminology-1.8.1
++ r/r 723:     ct_log_list.cnf.dist
++ r/r 722:     ct_log_list.cnf
+++ r/r 584:    esyslog
++++++ r/r 1219:        dm-log.ko
++++++ r/r 1217:        dm-log-userspace.ko
++++++ r/r 1218:        dm-log-writes.ko
+++++++ r/r 1463:       ebt_nflog.ko
+++++++ r/r 1460:       ebt_log.ko
+++++++ r/r 1473:       nf_log_bridge.ko
+++++++ r/r 1515:       nf_log_arp.ko
+++++++ r/r 1516:       nf_log_ipv4.ko
+++++++ r/r 1580:       nf_log_ipv6.ko
++++++ r/r 1686:        nft_log.ko
++++++ r/r 1658:        nf_log_common.ko
++++++ r/r 1671:        nfnetlink_log.ko
+ d/d 490:      log
++ r/r 1874:    acpid.log
++ l/l 256:     logger
++ l/l 349:     setlogcons
+ l/l 257:      login
+ l/l 248:      klogd
+ l/l 258:      logread
+ l/l 298:      nologin
+ l/l 374:      syslogd
                                                                                                                                                                        
┌──(kali㉿kali)-[~/picoctf/forensic4/Operation_Orchid]
└─$ fls -o 411648 disk.flag.img 490
d/d 859:        chrony
r/r 489:        wtmp
r/r 1871:       dmesg
r/r 33: messages
r/r 1874:       acpid.log
                                                                                                                                                                        
┌──(kali㉿kali)-[~/picoctf/forensic4/Operation_Orchid]
└─$ icat -o 411648 disk.flag.img 759
SYSLOGD_OPTS="-t"
                                                                                                                                                                        
┌──(kali㉿kali)-[~/picoctf/forensic4/Operation_Orchid]
└─$ icat -o 411648 disk.flag.img 771
#!/sbin/openrc-run

description="Message logging system"

name="busybox syslog"
command="/sbin/syslogd"
command_args="${SYSLOGD_OPTS}"
pidfile="/var/run/syslogd.pid"
start_stop_daemon_args="-g wheel -k 027"

depend() {
        need clock hostname localmount
        provide logger
}
                                                                                                                                                                        
┌──(kali㉿kali)-[~/picoctf/forensic4/Operation_Orchid]
└─$ fls -o 411648 disk.flag.img 472
r/r 1875:       .ash_history
r/r * 1876(realloc):    flag.txt
r/r 1782:       flag.txt.enc
                                                                                                                                                                        
┌──(kali㉿kali)-[~/picoctf/forensic4/Operation_Orchid]
└─$ icat -o 411648 disk.flag.img 2000
                                                                                                                                                                        
┌──(kali㉿kali)-[~/picoctf/forensic4/Operation_Orchid]
└─$ cat flag.txt       
cat: flag.txt: No such file or directory
                                                                                                                                                                        
┌──(kali㉿kali)-[~/picoctf/forensic4/Operation_Orchid]
└─$ openssl aes256 -d -salt -in flag.txt.enc -out flag.txt -k unbreakablepassword1234567
*** WARNING : deprecated key derivation used.
Using -iter or -pbkdf2 would be better.
bad decrypt
40F79048527F0000:error:1C800064:Provider routines:ossl_cipher_unpadblock:bad decrypt:../providers/implementations/ciphers/ciphercommon_block.c:107:
                                                                                                                                                                        
┌──(kali㉿kali)-[~/picoctf/forensic4/Operation_Orchid]
└─$ cat flag.txt

```

picoCTF{h4un71ng_p457_1d02081e}

## Notas
## Referencias
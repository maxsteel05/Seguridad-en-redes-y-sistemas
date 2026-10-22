## Descripción

🥛[http://wily-courier.picoctf.net:62696/](http://wily-courier.picoctf.net:62696/)

## Solución

```
┌──(kali㉿kali)-[~/picoctf/forensic4]
└─$ curl -i http://wily-courier.picoctf.net:62696/                                                                  

HTTP/1.1 200 OK
Date: Mon, 23 Mar 2026 13:57:36 GMT
Server: Apache/2.4.38 (Debian)
Last-Modified: Thu, 14 Aug 2025 18:35:22 GMT
ETag: "205-63c5789346e80"
Accept-Ranges: bytes
Content-Length: 517
Vary: Accept-Encoding
Content-Type: text/html

<!doctype html>

<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=400" />
  <title>🥛</title>
  <link rel="stylesheet" href="style.css" />

</head>
<body>
  <div id="image" class="center"></div>
  <div id="foot" class="center">
    <h1>MilkSlap!</h1>
    Inspired by <a href="http://eelslap.com">http://eelslap.com</a> <br>
    Credit to: <a href="https://github.com/boxmein">boxmein</a> for code inspiration.
  </div>
  <script src="script.js">


</script>
</body>
</html>
                                                                                                                                                                        
┌──(kali㉿kali)-[~/picoctf/forensic4]
└─$ wget http://wily-courier.picoctf.net:62696/concat_v.png                                                                                

--2026-03-23 09:58:28--  http://wily-courier.picoctf.net:62696/concat_v.png
Resolving wily-courier.picoctf.net (wily-courier.picoctf.net)... 18.189.99.27
Connecting to wily-courier.picoctf.net (wily-courier.picoctf.net)|18.189.99.27|:62696... connected.
HTTP request sent, awaiting response... 200 OK
Length: 18095920 (17M) [image/png]
Saving to: ‘concat_v.png’

concat_v.png                              100%[=====================================================================================>]  17.26M   162KB/s    in 3m 37s  

2026-03-23 10:02:07 (81.3 KB/s) - ‘concat_v.png’ saved [18095920/18095920]

                                                                                                                                                                        
┌──(kali㉿kali)-[~/picoctf/forensic4]
└─$ zsteg concat_v.png
zsteg: command not found
                                                                                                                                                                        
┌──(kali㉿kali)-[~/picoctf/forensic4]
└─$ sudo apt install zsteg
[sudo] password for kali: 
Error: Unable to locate package zsteg
                                                                                                                                                                        
┌──(kali㉿kali)-[~/picoctf/forensic4]
└─$ sudo gem install zsteg                               
Fetching iostruct-0.7.0.gem
Fetching rainbow-3.1.1.gem
Fetching zsteg-0.2.14.gem
Fetching zpng-0.4.6.gem
Successfully installed rainbow-3.1.1
Successfully installed iostruct-0.7.0
Successfully installed zpng-0.4.6
Successfully installed zsteg-0.2.14
Parsing documentation for rainbow-3.1.1
Installing ri documentation for rainbow-3.1.1
Parsing documentation for iostruct-0.7.0
Installing ri documentation for iostruct-0.7.0
Parsing documentation for zpng-0.4.6
Installing ri documentation for zpng-0.4.6
Parsing documentation for zsteg-0.2.14
Installing ri documentation for zsteg-0.2.14
Done installing documentation for rainbow, iostruct, zpng, zsteg after 1 seconds
4 gems installed
                                                                                                                                                                        
┌──(kali㉿kali)-[~/picoctf/forensic4]
└─$ zsteg concat_v.png    
/var/lib/gems/3.3.0/gems/zpng-0.4.6/lib/zpng/scan_line.rb:369:in `prev_scanline_byte': stack level too deep (SystemStackError)
        from /var/lib/gems/3.3.0/gems/zpng-0.4.6/lib/zpng/scan_line.rb:319:in `block in decoded_bytes'
        from /var/lib/gems/3.3.0/gems/zpng-0.4.6/lib/zpng/scan_line.rb:318:in `upto'
        from /var/lib/gems/3.3.0/gems/zpng-0.4.6/lib/zpng/scan_line.rb:318:in `decoded_bytes'
        from /var/lib/gems/3.3.0/gems/zpng-0.4.6/lib/zpng/scan_line/mixins.rb:17:in `prev_scanline_byte'
        from /var/lib/gems/3.3.0/gems/zpng-0.4.6/lib/zpng/scan_line.rb:377:in `prev_scanline_byte'
        from /var/lib/gems/3.3.0/gems/zpng-0.4.6/lib/zpng/scan_line.rb:319:in `block in decoded_bytes'
        from /var/lib/gems/3.3.0/gems/zpng-0.4.6/lib/zpng/scan_line.rb:318:in `upto'
        from /var/lib/gems/3.3.0/gems/zpng-0.4.6/lib/zpng/scan_line.rb:318:in `decoded_bytes'
         ... 10225 levels...
        from /var/lib/gems/3.3.0/gems/zsteg-0.2.14/lib/zsteg.rb:26:in `run'
        from /var/lib/gems/3.3.0/gems/zsteg-0.2.14/bin/zsteg:8:in `<top (required)>'
        from /usr/local/bin/zsteg:25:in `load'
        from /usr/local/bin/zsteg:25:in `<main>'
                                                                                                                                                                        
┌──(kali㉿kali)-[~/picoctf/forensic4]
└─$ steghide extract -sf concat_v.png
Command 'steghide' not found, but can be installed with:
sudo apt install steghide
Do you want to install it? (N/y)y
sudo apt install steghide
The following package was automatically installed and is no longer required:
  libcrypt-dev
Use 'sudo apt autoremove' to remove it.

Installing:
  steghide
                                                                                                                                                                        
Installing dependencies:
  libmcrypt4  libmhash2
                                                                                                                                                                        
Suggested packages:
  libmcrypt-dev  mcrypt

Summary:
  Upgrading: 0, Installing: 3, Removing: 0, Not Upgrading: 1685
  Download size: 309 kB
  Space needed: 916 kB / 54.8 GB available

Continue? [Y/n] y
Err:1 http://http.kali.org/kali kali-rolling/main amd64 libmcrypt4 amd64 2.5.8-8+b1
  403  Forbidden [IP: 54.39.128.230 80]
Err:2 http://http.kali.org/kali kali-rolling/main amd64 libmhash2 amd64 0.9.9.9-11
  403  Forbidden [IP: 54.39.128.230 80]
Err:3 http://http.kali.org/kali kali-rolling/main amd64 steghide amd64 0.5.1-15
  403  Forbidden [IP: 54.39.128.230 80]
Error: Failed to fetch http://http.kali.org/kali/pool/main/libm/libmcrypt/libmcrypt4_2.5.8-8%2bb1_amd64.deb  403  Forbidden [IP: 54.39.128.230 80]
Error: Failed to fetch http://http.kali.org/kali/pool/main/m/mhash/libmhash2_0.9.9.9-11_amd64.deb  403  Forbidden [IP: 54.39.128.230 80]
Error: Failed to fetch http://http.kali.org/kali/pool/main/s/steghide/steghide_0.5.1-15_amd64.deb  403  Forbidden [IP: 54.39.128.230 80]
Error: Unable to fetch some archives, maybe run apt update or try with --fix-missing?
                                                                                                                                                                        
┌──(kali㉿kali)-[~/picoctf/forensic4]
└─$ sudo apt update
Err:1 http://http.kali.org/kali kali-rolling InRelease 
  403  Forbidden [IP: 54.39.128.230 80]
Error: Failed to fetch http://http.kali.org/kali/dists/kali-rolling/InRelease  403  Forbidden [IP: 54.39.128.230 80]
Error: The repository 'http://http.kali.org/kali kali-rolling InRelease' is no longer signed.
Notice: Updating from such a repository can't be done securely, and is therefore disabled by default.
Notice: See apt-secure(8) manpage for repository creation and user configuration details.
                                                                                                                                                                        
┌──(kali㉿kali)-[~/picoctf/forensic4]
└─$ zsteg -s first concat_v.png
/var/lib/gems/3.3.0/gems/zpng-0.4.6/lib/zpng/scan_line.rb:369:in `prev_scanline_byte': stack level too deep (SystemStackError)
        from /var/lib/gems/3.3.0/gems/zpng-0.4.6/lib/zpng/scan_line.rb:319:in `block in decoded_bytes'
        from /var/lib/gems/3.3.0/gems/zpng-0.4.6/lib/zpng/scan_line.rb:318:in `upto'
        from /var/lib/gems/3.3.0/gems/zpng-0.4.6/lib/zpng/scan_line.rb:318:in `decoded_bytes'
        from /var/lib/gems/3.3.0/gems/zpng-0.4.6/lib/zpng/scan_line/mixins.rb:17:in `prev_scanline_byte'
        from /var/lib/gems/3.3.0/gems/zpng-0.4.6/lib/zpng/scan_line.rb:377:in `prev_scanline_byte'
        from /var/lib/gems/3.3.0/gems/zpng-0.4.6/lib/zpng/scan_line.rb:319:in `block in decoded_bytes'
        from /var/lib/gems/3.3.0/gems/zpng-0.4.6/lib/zpng/scan_line.rb:318:in `upto'
        from /var/lib/gems/3.3.0/gems/zpng-0.4.6/lib/zpng/scan_line.rb:318:in `decoded_bytes'
         ... 10225 levels...
        from /var/lib/gems/3.3.0/gems/zsteg-0.2.14/lib/zsteg.rb:26:in `run'
        from /var/lib/gems/3.3.0/gems/zsteg-0.2.14/bin/zsteg:8:in `<top (required)>'
        from /usr/local/bin/zsteg:25:in `load'
        from /usr/local/bin/zsteg:25:in `<main>'
                                                                                                                                                                        
┌──(kali㉿kali)-[~/picoctf/forensic4]
└─$ zsteg --all --limit 1000 concat_v.png
/var/lib/gems/3.3.0/gems/zpng-0.4.6/lib/zpng/scan_line.rb:369:in `prev_scanline_byte': stack level too deep (SystemStackError)
        from /var/lib/gems/3.3.0/gems/zpng-0.4.6/lib/zpng/scan_line.rb:319:in `block in decoded_bytes'
        from /var/lib/gems/3.3.0/gems/zpng-0.4.6/lib/zpng/scan_line.rb:318:in `upto'
        from /var/lib/gems/3.3.0/gems/zpng-0.4.6/lib/zpng/scan_line.rb:318:in `decoded_bytes'
        from /var/lib/gems/3.3.0/gems/zpng-0.4.6/lib/zpng/scan_line/mixins.rb:17:in `prev_scanline_byte'
        from /var/lib/gems/3.3.0/gems/zpng-0.4.6/lib/zpng/scan_line.rb:377:in `prev_scanline_byte'
        from /var/lib/gems/3.3.0/gems/zpng-0.4.6/lib/zpng/scan_line.rb:319:in `block in decoded_bytes'
        from /var/lib/gems/3.3.0/gems/zpng-0.4.6/lib/zpng/scan_line.rb:318:in `upto'
        from /var/lib/gems/3.3.0/gems/zpng-0.4.6/lib/zpng/scan_line.rb:318:in `decoded_bytes'
         ... 10225 levels...
        from /var/lib/gems/3.3.0/gems/zsteg-0.2.14/lib/zsteg.rb:26:in `run'
        from /var/lib/gems/3.3.0/gems/zsteg-0.2.14/bin/zsteg:8:in `<top (required)>'
        from /usr/local/bin/zsteg:25:in `load'
        from /usr/local/bin/zsteg:25:in `<main>'
                                                                                                                                                                        
┌──(kali㉿kali)-[~/picoctf/forensic4]
└─$ zsteg -E "b1,bgr,lsb,xy" concat_v.png
    




^Z                  
zsh: suspended  zsteg -E "b1,bgr,lsb,xy" concat_v.png
                                                                                                                                                                        
┌──(kali㉿kali)-[~/picoctf/forensic4]
└─$ RUBY_THREAD_DEFAULT_QUANTUM_MS=10 zsteg -s first concat_v.png
/var/lib/gems/3.3.0/gems/zpng-0.4.6/lib/zpng/scan_line.rb:369:in `prev_scanline_byte': stack level too deep (SystemStackError)
        from /var/lib/gems/3.3.0/gems/zpng-0.4.6/lib/zpng/scan_line.rb:319:in `block in decoded_bytes'
        from /var/lib/gems/3.3.0/gems/zpng-0.4.6/lib/zpng/scan_line.rb:318:in `upto'
        from /var/lib/gems/3.3.0/gems/zpng-0.4.6/lib/zpng/scan_line.rb:318:in `decoded_bytes'
        from /var/lib/gems/3.3.0/gems/zpng-0.4.6/lib/zpng/scan_line/mixins.rb:17:in `prev_scanline_byte'
        from /var/lib/gems/3.3.0/gems/zpng-0.4.6/lib/zpng/scan_line.rb:377:in `prev_scanline_byte'
        from /var/lib/gems/3.3.0/gems/zpng-0.4.6/lib/zpng/scan_line.rb:319:in `block in decoded_bytes'
        from /var/lib/gems/3.3.0/gems/zpng-0.4.6/lib/zpng/scan_line.rb:318:in `upto'
        from /var/lib/gems/3.3.0/gems/zpng-0.4.6/lib/zpng/scan_line.rb:318:in `decoded_bytes'
         ... 10225 levels...
        from /var/lib/gems/3.3.0/gems/zsteg-0.2.14/lib/zsteg.rb:26:in `run'
        from /var/lib/gems/3.3.0/gems/zsteg-0.2.14/bin/zsteg:8:in `<top (required)>'
        from /usr/local/bin/zsteg:25:in `load'
        from /usr/local/bin/zsteg:25:in `<main>'
                                                                                                                                                                        
┌──(kali㉿kali)-[~/picoctf/forensic4]
└─$ RUBY_THREAD_TIMESLICE=10 zsteg -s first concat_v.png
/var/lib/gems/3.3.0/gems/zpng-0.4.6/lib/zpng/scan_line.rb:369:in `prev_scanline_byte': stack level too deep (SystemStackError)
        from /var/lib/gems/3.3.0/gems/zpng-0.4.6/lib/zpng/scan_line.rb:319:in `block in decoded_bytes'
        from /var/lib/gems/3.3.0/gems/zpng-0.4.6/lib/zpng/scan_line.rb:318:in `upto'
        from /var/lib/gems/3.3.0/gems/zpng-0.4.6/lib/zpng/scan_line.rb:318:in `decoded_bytes'
        from /var/lib/gems/3.3.0/gems/zpng-0.4.6/lib/zpng/scan_line/mixins.rb:17:in `prev_scanline_byte'
        from /var/lib/gems/3.3.0/gems/zpng-0.4.6/lib/zpng/scan_line.rb:377:in `prev_scanline_byte'
        from /var/lib/gems/3.3.0/gems/zpng-0.4.6/lib/zpng/scan_line.rb:319:in `block in decoded_bytes'
        from /var/lib/gems/3.3.0/gems/zpng-0.4.6/lib/zpng/scan_line.rb:318:in `upto'
        from /var/lib/gems/3.3.0/gems/zpng-0.4.6/lib/zpng/scan_line.rb:318:in `decoded_bytes'
         ... 10225 levels...
        from /var/lib/gems/3.3.0/gems/zsteg-0.2.14/lib/zsteg.rb:26:in `run'
        from /var/lib/gems/3.3.0/gems/zsteg-0.2.14/bin/zsteg:8:in `<top (required)>'
        from /usr/local/bin/zsteg:25:in `load'
        from /usr/local/bin/zsteg:25:in `<main>'
                                                                                                                                                                        
┌──(kali㉿kali)-[~/picoctf/forensic4]
└─$ RUBY_THREAD_DEFAULT_QUANTUM_MS=100000 zsteg -s first concat_v.png
/var/lib/gems/3.3.0/gems/zpng-0.4.6/lib/zpng/scan_line.rb:369:in `prev_scanline_byte': stack level too deep (SystemStackError)
        from /var/lib/gems/3.3.0/gems/zpng-0.4.6/lib/zpng/scan_line.rb:319:in `block in decoded_bytes'
        from /var/lib/gems/3.3.0/gems/zpng-0.4.6/lib/zpng/scan_line.rb:318:in `upto'
        from /var/lib/gems/3.3.0/gems/zpng-0.4.6/lib/zpng/scan_line.rb:318:in `decoded_bytes'
        from /var/lib/gems/3.3.0/gems/zpng-0.4.6/lib/zpng/scan_line/mixins.rb:17:in `prev_scanline_byte'
        from /var/lib/gems/3.3.0/gems/zpng-0.4.6/lib/zpng/scan_line.rb:377:in `prev_scanline_byte'
        from /var/lib/gems/3.3.0/gems/zpng-0.4.6/lib/zpng/scan_line.rb:319:in `block in decoded_bytes'
        from /var/lib/gems/3.3.0/gems/zpng-0.4.6/lib/zpng/scan_line.rb:318:in `upto'
        from /var/lib/gems/3.3.0/gems/zpng-0.4.6/lib/zpng/scan_line.rb:318:in `decoded_bytes'
         ... 10225 levels...
        from /var/lib/gems/3.3.0/gems/zsteg-0.2.14/lib/zsteg.rb:26:in `run'
        from /var/lib/gems/3.3.0/gems/zsteg-0.2.14/bin/zsteg:8:in `<top (required)>'
        from /usr/local/bin/zsteg:25:in `load'
        from /usr/local/bin/zsteg:25:in `<main>'
                                                                                                                                                                        
┌──(kali㉿kali)-[~/picoctf/forensic4]
└─$ zsteg concat_v.png
/var/lib/gems/3.3.0/gems/zpng-0.4.6/lib/zpng/scan_line.rb:369:in `prev_scanline_byte': stack level too deep (SystemStackError)
        from /var/lib/gems/3.3.0/gems/zpng-0.4.6/lib/zpng/scan_line.rb:319:in `block in decoded_bytes'
        from /var/lib/gems/3.3.0/gems/zpng-0.4.6/lib/zpng/scan_line.rb:318:in `upto'
        from /var/lib/gems/3.3.0/gems/zpng-0.4.6/lib/zpng/scan_line.rb:318:in `decoded_bytes'
        from /var/lib/gems/3.3.0/gems/zpng-0.4.6/lib/zpng/scan_line/mixins.rb:17:in `prev_scanline_byte'
        from /var/lib/gems/3.3.0/gems/zpng-0.4.6/lib/zpng/scan_line.rb:377:in `prev_scanline_byte'
        from /var/lib/gems/3.3.0/gems/zpng-0.4.6/lib/zpng/scan_line.rb:319:in `block in decoded_bytes'
        from /var/lib/gems/3.3.0/gems/zpng-0.4.6/lib/zpng/scan_line.rb:318:in `upto'
        from /var/lib/gems/3.3.0/gems/zpng-0.4.6/lib/zpng/scan_line.rb:318:in `decoded_bytes'
         ... 10225 levels...
        from /var/lib/gems/3.3.0/gems/zsteg-0.2.14/lib/zsteg.rb:26:in `run'
        from /var/lib/gems/3.3.0/gems/zsteg-0.2.14/bin/zsteg:8:in `<top (required)>'
        from /usr/local/bin/zsteg:25:in `load'
        from /usr/local/bin/zsteg:25:in `<main>'
                                                                                                                                                                        
┌──(kali㉿kali)-[~/picoctf/forensic4]
└─$ zsteg -s first concat_v.png
/var/lib/gems/3.3.0/gems/zpng-0.4.6/lib/zpng/scan_line.rb:369:in `prev_scanline_byte': stack level too deep (SystemStackError)
        from /var/lib/gems/3.3.0/gems/zpng-0.4.6/lib/zpng/scan_line.rb:319:in `block in decoded_bytes'
        from /var/lib/gems/3.3.0/gems/zpng-0.4.6/lib/zpng/scan_line.rb:318:in `upto'
        from /var/lib/gems/3.3.0/gems/zpng-0.4.6/lib/zpng/scan_line.rb:318:in `decoded_bytes'
        from /var/lib/gems/3.3.0/gems/zpng-0.4.6/lib/zpng/scan_line/mixins.rb:17:in `prev_scanline_byte'
        from /var/lib/gems/3.3.0/gems/zpng-0.4.6/lib/zpng/scan_line.rb:377:in `prev_scanline_byte'
        from /var/lib/gems/3.3.0/gems/zpng-0.4.6/lib/zpng/scan_line.rb:319:in `block in decoded_bytes'
        from /var/lib/gems/3.3.0/gems/zpng-0.4.6/lib/zpng/scan_line.rb:318:in `upto'
        from /var/lib/gems/3.3.0/gems/zpng-0.4.6/lib/zpng/scan_line.rb:318:in `decoded_bytes'
         ... 10225 levels...
        from /var/lib/gems/3.3.0/gems/zsteg-0.2.14/lib/zsteg.rb:26:in `run'
        from /var/lib/gems/3.3.0/gems/zsteg-0.2.14/bin/zsteg:8:in `<top (required)>'
        from /usr/local/bin/zsteg:25:in `load'
        from /usr/local/bin/zsteg:25:in `<main>'
                                                                                                                                                                        
┌──(kali㉿kali)-[~/picoctf/forensic4]
└─$ ruby -r zsteg -e 'puts Zsteg::Image.new(File.read("concat_v.png")).decode(first: true)'
-e:1:in `<main>': uninitialized constant Zsteg (NameError)

puts Zsteg::Image.new(File.read("concat_v.png")).decode(first: true)
     ^^^^^
Did you mean?  ZSteg
                                                                                                                                                                        
┌──(kali㉿kali)-[~/picoctf/forensic4]
└─$ imagedata           .. text: "\n\n\n\n\n\n\t\t"
b1,b,lsb,xy         .. text: "picoCTF{imag3_m4n1pul4t10n_sl4p5}\n"
b1,bgr,lsb,xy       .. <wbStego size=9706075, data="\xB6\xAD\xB6}\xDB\xB2lR\x7F\xDF\x86\xB7c\xFC\xFF\xBF\x02Zr\x8E\xE2Z\x12\xD8q\xE5&MJ-X:\xB5\xBF\xF7\x7F\xDB\xDFI\bm\xDB\xDB\x80m\x00\x00\x00\xB6m\xDB\xDB\xB6\x00\x00\x00\xB6\xB6\x00m\xDB\x12\x12m\xDB\xDB\x00\x00\x00\x00\x00\xB6m\xDB\x00\xB6\x00\x00\x00\xDB\xB6mm\xDB\xB6\xB6\x00\x00\x00\x00\x00m\xDB", even=true, mix=true, controlbyte="[">                                                                                 
b2,r,lsb,xy         .. file: SoftQuad DESC or font file binary
b2,r,msb,xy         .. file: VISX image file
b2,g,lsb,xy         .. file: VISX image file
b2,g,msb,xy         .. file: SoftQuad DESC or font file binary - version 15722
b2,b,msb,xy         .. text: "UfUUUU@UUU"
b4,r,lsb,xy         .. text: "\"\"\"\"\"#4D"
b4,r,msb,xy         .. text: "wwww3333"
b4,g,lsb,xy         .. text: "wewwwwvUS"
b4,g,msb,xy         .. text: "\"\"\"\"DDDD"
b4,b,lsb,xy         .. text: "vdUeVwweDFw"
b4,b,msb,xy         .. text: "UUYYUUUUUUUU"

```

## Notas

## Referencias
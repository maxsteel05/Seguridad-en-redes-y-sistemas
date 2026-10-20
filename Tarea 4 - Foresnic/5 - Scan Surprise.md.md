## Descripción

## Solución

```
┌──(kali㉿kali)-[~/picoctf/t4forensic/ScanSurprise]
└─$ wget I've gotten bored of handing out flags as text. Wouldn't it be cool if they were an image instead?                                
You can download the challenge files here:
challenge.zip
The same files are accessible via SSH here:
ssh -p 63743 ctf-player@atlas.picoctf.net
Using the password 6abf4a82. Accept the fingerprint with yes, and ls once connected to begin. Remember, in a shell, passwords are hidden!
Prepended http:// to 'Ive gotten bored of handing out flags as text. Wouldnt'
--2026-03-24 22:09:56--  http://ive%20gotten%20bored%20of%20handing%20out%20flags%20as%20text.%20wouldnt/
Resolving ive gotten bored of handing out flags as text. wouldnt (ive gotten bored of handing out flags as text. wouldnt)... failed: Name or service not known.
wget: unable to resolve host address ‘ive gotten bored of handing out flags as text. wouldnt’
Prepended http:// to 'it'
--2026-03-24 22:09:56--  http://it/
Resolving it (it)... failed: No address associated with hostname.
wget: unable to resolve host address ‘it’
Prepended http:// to 'be'
--2026-03-24 22:09:56--  http://be/
Resolving be (be)... failed: No address associated with hostname.
wget: unable to resolve host address ‘be’
Prepended http:// to 'cool'
--2026-03-24 22:09:56--  http://cool/
Resolving cool (cool)... failed: No address associated with hostname.
wget: unable to resolve host address ‘cool’
Prepended http:// to 'if'
--2026-03-24 22:09:56--  http://if/
Resolving if (if)... failed: Name or service not known.
wget: unable to resolve host address ‘if’
Prepended http:// to 'they'
--2026-03-24 22:09:56--  http://they/
Resolving they (they)... failed: Name or service not known.
wget: unable to resolve host address ‘they’
Prepended http:// to 'were'
--2026-03-24 22:09:56--  http://were/
Resolving were (were)... failed: Name or service not known.
wget: unable to resolve host address ‘were’
Prepended http:// to 'an'
--2026-03-24 22:09:56--  http://an/
Resolving an (an)... failed: Name or service not known.
wget: unable to resolve host address ‘an’
Prepended http:// to 'image'
--2026-03-24 22:09:57--  http://image/
Resolving image (image)... failed: Name or service not known.
wget: unable to resolve host address ‘image’
Prepended http:// to 'instead?'
--2026-03-24 22:09:57--  http://instead/?
Resolving instead (instead)... failed: Name or service not known.
wget: unable to resolve host address ‘instead’
You: command not found
challenge.zip: command not found
Command 'The' not found, did you mean:
  command 'he' from deb node-he
Try: sudo apt install <deb name>
The authenticity of host '[atlas.picoctf.net]:63743 ([18.217.83.136]:63743)' can't be established.
ED25519 key fingerprint is: SHA256:hVmbk/OaNT4902bBr7h26wfhmBuJWi4tub8AJqoAJCM
This key is not known by any other names.
Are you sure you want to continue connecting (yes/no/[fingerprint])? yes
Warning: Permanently added '[atlas.picoctf.net]:63743' (ED25519) to the list of known hosts.
** WARNING: connection is not using a post-quantum key exchange algorithm.
** This session may be vulnerable to "store now, decrypt later" attacks.
** The server may need to be upgraded. See https://openssh.com/pq.html
ctf-player@atlas.picoctf.net's password: 





Permission denied, please try again.
ctf-player@atlas.picoctf.net's password: 
Permission denied, please try again.
ctf-player@atlas.picoctf.net's password: 
ctf-player@atlas.picoctf.net: Permission denied (publickey,password).
Using: command not found



┌──(kali㉿kali)-[~/picoctf/t4forensic/ScanSurprise]
└─$ ssh -p 63743 ctf-player@atlas.picoctf.net
** WARNING: connection is not using a post-quantum key exchange algorithm.
** This session may be vulnerable to "store now, decrypt later" attacks.
** The server may need to be upgraded. See https://openssh.com/pq.html
ctf-player@atlas.picoctf.net's password: 

```

picoCTF{p33k_@_b00_7843f77c}

## Notas

## Referencias
Descripción:

Why search for the flag when I can make a bookmarklet to print it for me? Browse [here](http://xebec.cylabacademy.net:46353/), and find the flag!

Solución:

Copié el código del bookmarklet que venía en la página, lo pegué en la consola del navegador y al ejecutarlo me tiró una alerta con la bandera descifrada.

```

allow pasting

        javascript:(function() {

            var encryptedFlag = "ÑÌÄÓÈáßëÙ£Ö�ÓÚåÛÑ¢ÕÓ�©��ÕÄÕËí";

            var key = "picoctf";

            var decryptedFlag = "";

            for (var i = 0; i < encryptedFlag.length; i++) {

                decryptedFlag += String.fromCharCode((encryptedFlag.charCodeAt(i) - key.charCodeAt(i % key.length) + 256) % 256);

            }

            alert(decryptedFlag);

        })();

```

academy{p@g3_turn3r_8915faae}

Referencias:

[https://infosecwriteups.com/%EF%B8%8F-picoctf-2024-bookmarklet-web-exploitation-challenge-834b3ce821e2](https://infosecwriteups.com/%EF%B8%8F-picoctf-2024-bookmarklet-web-exploitation-challenge-834b3ce821e2)
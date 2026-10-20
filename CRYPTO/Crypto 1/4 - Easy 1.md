## Descripción

The one time pad can be cryptographically secure, but not when you know the key. Can you solve this?We've given you the encrypted flag, key, and a table to help UFJKXQZQUNB with the key of SOLVECRYPTO. Can you use this [table](https://challenge-files.picoctf.net/c_fickle_tempest/859ffc313a4d8b63149f144745043a7312fc4f993e405eeeb8ee5ae6ca8444a8/table.txt) to solve it?.

## Solución

- cyberchef: [https://gchq.github.io/CyberChef/#recipe=Vigen%C3%A8re_Decode('SOLVECRYPTO')&input=VUZKS1hRWlFVTkIg](https://gchq.github.io/CyberChef/#recipe=Vigen%C3%A8re_Decode\('SOLVECRYPTO'\)&input=VUZKS1hRWlFVTkIg) picoCTF{CRYPTOISFUN}

## Notas

El módulo **Vigenère Decode** en CyberChef sirve para **descifrar textos que fueron cifrados con el cifrado de Vigenère**.

---

## 🔐 ¿Qué es el cifrado Vigenère?

Es un método más avanzado que ROT13. Usa una **clave (palabra secreta)** para desplazar cada letra del mensaje de forma diferente.

👉 En lugar de un solo desplazamiento fijo, cada letra depende de la clave.

## Referencias
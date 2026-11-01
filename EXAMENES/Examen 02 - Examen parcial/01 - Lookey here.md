## Descripción

Attackers have hidden information in a very large mass of data in the past, maybe they are still doing it. Download the data [here](https://challenge-files.cylabacademy.net/library/1e5b915df467718ade9bc65b9de2094f73159c40c620fbea7bfec17f657252b3/anthem.flag.txt).

1.- Download the file and search for the flag based on the known prefix.

## Solución


```
sudo apt update
sudo apt install -y wget grep coreutils gzip file xxd libimage-exiftool-perl steghide sleuthkit python3 xdg-utils

mkdir -p ~/picoctf-forensics/01-lookey-here
cd ~/picoctf-forensics/01-lookey-here
wget -O anthem.flag.txt 'https://challenge-files.cylabacademy.net/library/1e5b915df467718ade9bc65b9de2094f73159c40c620fbea7bfec17f657252b3/anthem.flag.txt'
grep -oE 'academy\{[^}]+\}' anthem.flag.txt

academy{gr3p_15_@w3s0m3_33595e98}
```

## Notas Adicionales

- `grep -o` muestra únicamente la coincidencia, evitando imprimir el documento completo.

## Referencias
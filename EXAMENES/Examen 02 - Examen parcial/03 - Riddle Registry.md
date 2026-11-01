## Descripción

Hi, intrepid investigator! 📄🔍 You've stumbled upon a peculiar PDF filled with what seems like nothing more than garbled nonsense. But beware! Not everything is as it appears. Amidst the chaos lies a hidden treasure—an elusive flag waiting to be uncovered. Find the PDF file here [Hidden Confidential Document](https://challenge-files.cylabacademy.net/library/cd10271d1755c79f00fce1beff6a218832ac3678783ccfce59c111813fcb7276/confidential.pdf) and uncover the flag within the metadata.

1.- Don't be fooled by the visible text; it’s just a decoy!

2.- Look beyond the surface for hidden clues

## Solución

```
mkdir -p ~/picoctf-forensics/03-riddle-registry
cd ~/picoctf-forensics/03-riddle-registry
wget -O confidential.pdf 'https://challenge-files.cylabacademy.net/library/cd10271d1755c79f00fce1beff6a218832ac3678783ccfce59c111813fcb7276/confidential.pdf'
exiftool -Author confidential.pdf
exiftool -s3 -Author confidential.pdf | base64 --decode
printf '\n'

academy{puzzl3d_m3tadata_f0und!_4770d4ec}
```

## Notas Adicionales

- Los metadatos pueden contener información que no aparece en las páginas visibles del documento.

## Referencias
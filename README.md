Formato Condicional
===========

<p align="justify">
	El formato condicional en Excel es una se da un formato en base al valor de cada celda. Esto color de relleno diferente para aquellas celdas que cumplan con ciertas reglas y así poder identificarlas fácilmente en pantalla.
</p>

## Ejemplo - Lista de promedios

### Descripción

<p align="justify">
	Hola, Soy profesor de la clase de <i>Matemáticas</i> en el instituto Pato. 
Mi salón está conformado por 50 alumnos, los cuales presentan 3 exámenes parciales a lo largo del semestre. Me gustaría poder ver en colores: los que reprueban, los que apenas y pasan con un 6 o un 7 y los que sacan al menos 8 o superior. Así mismo si un alumno saco 10 en los 3 exámenes me gustaría ver su nombre remarcado de otro color tal vez morado.

Quiero que me enseñen una muestra <i>simulada</i> sin datos reales de como funcionaría la hoja de Excel, para poder comprarla, gracias.
</p>

### Simulación

<p align="justify">
	Vamos a <b>simular</b> los nombres y las notas, para que se vea algo así:
</p>

<p align="center">
	 <img src="https://github.com/ginppian/Excel-Formato_Condicional/blob/master/imgs/img1.png" width="569" height="380"> 
</p>

* No. Lista

<p align="justify">
	Basta con hacer una <b>serie</b> de números consecutivos.
En la primera celda colocamos 1, en la celda inferior 2 y arrastramos hasta el número 50. Fácil.
</p>

* Nombre

<p align="justify">
	Cómo queremos nombres <b>aleatorios</b> usaremos la función:
</p>

```
=ALEATORIO.ENTRE(inferior,superior)
```

<p align="justify">
	pero esta función nos regresa un <i>número</i> NO una letra. Para ese fin usaremos la función:
</p>

```
=CARACTER(numero)
```

<p align="justify">
la cual nos pide como parámetro un número, porque usa la tabla <b>ASCII</b> :S ¿Qué es la <i>tabla ASCII</i>?
</p>


<p align="justify">
<i>American Standard Code for Information Interchange</i> código basado en el alfabeto latino, es un método para una correspondencia entre cadenas de bits (números) y una serie de símbolos:
</p>

<p align="justify">
Alt + 1 = ☺
Alt + 2 = ☻ ...
Alt + 64=@ ...
Alt +100=d ... 
</p>

<p align="center">
	 <img src="https://github.com/ginppian/Excel-Formato_Condicional/blob/master/imgs/img1.png" width="569" height="380"> 
</p>




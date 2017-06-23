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

#### 1. No. Lista

<p align="justify">
	Basta con hacer una <b>serie</b> de números consecutivos.
En la primera celda colocamos 1, en la celda inferior 2 y arrastramos hasta el número 50. Fácil.
</p>

#### 2. Nombre

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
<i>American Standard Code for Information Interchange</i> código basado en el alfabeto latino. Es un método para una correspondencia entre cadenas de bits (números) y una serie de símbolos:
</p>

<p align="center">
Alt + 1 = ☺<br>
Alt + 2 = ☻ ...<br>
Alt + 64=@ ...<br>
Alt +100=d ...<br>
</p>

<p align="center">
	 <img src="https://github.com/ginppian/Excel-Formato_Condicional/blob/master/imgs/img2.jpg" width="800" height="558"> 
</p>

* <i>Concatenar</i> el Resultado de una Función con Texto:

```
&
```

<p align="justify">
	Para poner un texto ameno que presidente a nuestro resultado bastara con poner: <i>el texto entre comillas</i> <b>&</b> <i>formula()</i>
</p>

* Integrando

```
=CARACTER(ALEATORIO.ENTRE(65,90))&CARACTER(ALEATORIO.ENTRE(65,90))&ALEATORIO.ENTRE(1,10)
```

	1. Entre <b>65:90</b> porque son las letras Mayusculas
	2. Generamos dos letras <i>Aleatorias</i> y un número entre 1 y 10 para generar su nombre.

#### 3. N Parcial

Bastara usar la función:

```
=ALEATORIO.ENTRE(0,10)
```

#### 4. Total

Usaremos:

```
=REDONDEAR(PROMEDIO(celda1, celda2, celda3),0)
```

<p align="justify">
El <i>PROMEDIO</i> nos regresa valores con <i>punto decimal</i> podríamos dejarlos o no. Para este caso práctico <b>redondearemos</b> con la función <i>REDONDEAR</i>.
</p>

<p align="justify">
<b>REDONDEAR</b> funciona redondeando hacia <i>ARRIBA</i> valores igual o mayor(=>) a <b>.5</b> y redondeando hacia <i>ABAJO</i> valores menores(<) que <b>.5</b>.<br>
Ejemplo:
</p>

<p align="center">
<b>4.5</b> será <i>5</i><br>
<b>4.4</b> será <i>4</i><br>
<b>4.8</b> será <i>5</i><br>
</p>

<p align="justify">
La función <i>REDONDEAR</i> nos pide dos <i>argumentos</i> en la función <i>=REDONDEAR(número, num_decimales)</i>.<br></p>

1. <b>número</b> hace clara referencia a número que queremos redondear.
2. <b>num_decimales</b> hasta que número queremos <b>truncar</b> para empezar el redondeo.

Ejemplo:


<p align="center">
<i>=REDONDEAR(3.14159265,4)</i> será <b>3.1416</b>
</p>

<p align="justify">
pues contó 4 dígitos después del punto, y ese número que corresponde al <b>4to número</b> lo usa para <i>redondear</i>.
</p>

#### 5. Formato de tabla

<p align="justify">
Un <b>shortcut</b> para seleccionar toda la <i>matriz</i>:
</p>

```
Shift (⇧) + Ctrl + Espacio 
```

<p align="justify">
<i>Inicio > Estilos > Dar formato como tabla</i>
</p>








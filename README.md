Formato Condicional
===========

<p align="justify">
	El formato condicional en Excel es una se da un formato en base al valor de cada celda. Esto color de relleno diferente para aquellas celdas que cumplan con ciertas reglas y así poder identificarlas fácilmente en pantalla.
</p>

## Ejemplo - Lista de promedios

### Descripción

<p align="justify">
	Hola, Soy profesor de la clase de <i>Matemáticas</i> en el instituto Pato. 
Mi salón está conformado por 50 alumnos, los cuales presentan 3 exámenes parciales a lo largo del semestre. Me gustaría poder ver en colores: los que reprobaron, los que apenas y pasaron (6 o 7) y los que sacan al menos 8 o superior.

Me gustaría que me enseñen una <i>simulación</i> de como funcionaría la hoja de Excel, para poder comprarla 100% convencido, gracias.
</p>

### A. Simulación

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

	1. Elegimos el rango entre 65 y 90 porque son las letras Mayusculas.
	2. Generamos dos letras Aleatorias y un número entre 1 y 10 para generar su nombre.

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

Seleccionamos un estilo de tabla cool 😎 
</p>

### B. Formato Condicional

<p align="justify">
Seleccionamos la <i>celda</i> que queremos y nos vamos a <i>Inicio > Formato Condicional</i>. Aun que <i>Excel</i> ya nos da unas opciones por <i>defecto</i> es conveniente que nos otros creemos nuestras propias <b>reglas</b> ya que debemos tener la certeza de toda nuestra información esté <i>correctamente</i> evaluada.
</p>

<p align="justify">
Vamos a <i>Administrar Reglas</i>
</p>

<p align="center">
	 <img src="https://github.com/ginppian/Excel-Formato_Condicional/blob/master/imgs/img3.png" width="1211" height="450"> 
</p>

<p align="justify">
<i>Nueva Regla</i>
</p>

<p align="center">
	 <img src="https://github.com/ginppian/Excel-Formato_Condicional/blob/master/imgs/img4.png" width="1211" height="450"> 
</p>

<p align="justify">
	Y veremos algo así:
</p>

<p align="center">
	 <img src="https://github.com/ginppian/Excel-Formato_Condicional/blob/master/imgs/img5.png" width="1211" height="450"> 
</p>

<p align="justify">
	Los <i>tipos</i> de regla son diferentes, yo te recomiendo principalmente 3 para los siguientes propósitos:
</p>

1. Para evaluar <b>numeros</b>.
2. Para evaluar <b>texto</b>.
3. Para evaluar en base a una <b>formula</b> personalizada.

<p align="justify">
	En este caso como estamos evaluando números seleccionamos la primera.
</p>

<p align="center">
	 <img src="https://github.com/ginppian/Excel-Formato_Condicional/blob/master/imgs/img6.png" width="510" height="411"> 
</p>

<p align="justify">
	Podemos trabajar con: 2 colores, 3 colores, iconos, etc. Seleccionaremos <i>conjunto de iconos</i>
</p>

<p align="center">
	 <img src="https://github.com/ginppian/Excel-Formato_Condicional/blob/master/imgs/img7.png" width="510" height="411"> 
</p>

<p align="justify">
	Cambiamos el <i>tipo de dato</i> a <b>número</b> y agregamos nuestros <i>valores condicionales</i> y damos <i>aceptar</i>.
</p>

<p align="center">
	 <img src="https://github.com/ginppian/Excel-Formato_Condicional/blob/master/imgs/img9.png" width="1211" height="450"> 
</p>

<p align="justify">
	Por último nos sale una ventana donde nos dice a dónde se <i>aplicará</i>. 
Podemos ver:
</p>


```
=$J$4
```

<p align="justify">
	Las <b>$</b> indican que esa <i>referencia</i> <b>NO se moverá</b>. Es decir, que el <i>FORMATO CONDICIONAL</i> sólo se aplicará a esa celda. Si queremos <i>recorrer</i> a las demás celdas, bastará con quitarle las <b>$</b> y darle aceptar, o picar el la <i>flechita</i> y con el mouse seleccionar todas las celdas que queramos que tengan esa <i>regla</i>.
</p>

<p align="justify">
	Al final se vería algo así:
</p>

<p align="center">
	 <img src="https://github.com/ginppian/Excel-Formato_Condicional/blob/master/imgs/img10.png" width="510" height="411"> 
</p>

## Contacto
Twitter: @ginppian









# Ejercicios con algoritmos

## Primeros 3 ejercicios

### Ejercicio 1

_Calcular la letra del DNI Español_

**Paso 1:** Definir el problema: A partir de un Nº de DNI hemos de calcular la letra.

¿Cómo de calcula la letra del DNI?

 El Número del DNI (de 8 dígitos)  debemos dividirlo entre 23 y el resto será el ```resultadoResto```

El ``resultadoResto`` lo compararemos con la lista de códigosde la siguente ``tablaLatrasDNI``

| Num  | Letra |
| ---- | ----- |
| 0    | T     |
| 1    | R     |
| 2    | W     |
| 3    | A     |
| 4    | G     |
| 5    | M     |
| 6    | Y     |
| 7    | F     |
| 8    | P     |
| 9    | D     |
| 10   | X     |
| 11   | B     |
| 12   | N     |
| 13   | J     |
| 14   | Z     |
| 15   | S     |
| 16   | Q     |
| 17   | V     |
| 18   | H     |
| 19   | L     |
| 20   | C     |
| 21   | K     |
| 22   | E     |

**Paso 2:** Poner la entrada, el proceso y la salida

Entrada: ``DNI`` y ``tablaLetrasDNI``, resultado =""

Proceso:

- Validar que el ``DNI`` tenga 8 dígitos y que sean todos numéricos.
- Si ``DNI`` es invalido, asigne a resultado "DNI Inválido."
- Dividir ``DNI`` entre 23 y el resto lo asignamos a ``resultadoResto``.
- Recorrer la ``tablaLetrasDNI`` buscando una coincidencia del resto y mostrando su letra correspondiente.

Salida:

Escribir el ``resultado``

**Paso 3:** Escribir el pseudocódigo

``` 
Algoritmo CalculoDNI
	# Entrada
	DNI<-Leer()
	tablaletrasDNI="TRWAGMYFPDXBNJZSQVHLCKE"
	resultado<-""
	# Proceso
	Si DNI <= 99999999 Entonces
		resultadoResto<-DNI mod 23 #mod es el resto de dividir
		resultado<-recuperarLetra(resultadoResto, tablaLetrasDNI)
	sino
		resultado<-"DNI Invalido"
	Fin si
	# Salida
	Escribir (resultado)
Fin Algoritmo
```

Sub-Algoritmo de validacion:
```
si DNI <= 99999999
	DNIValido<-true
sino
	DNIValido<-false
```




### Ejercicio 2

_Calcular el salario de un empleado_

**Paso 1:** Definir el problema

El salario en España se calcula a partir del salario bruto anual, que incluye todas las percepciones económicas que recibe un trabajador durante el año, incluyendo salario base, pagas extras, complementos y otros conceptos retributivos. 

**Paso 2:** Poner la entrada, el proceso y la salida

entrada: ``salario base``,  ``pagas extras``, ``complementos``, ``otrosconceptosRetributivos``, ``IRPF``, ``seguridad social``

Proceso:

- Sumar ``salariobase``, ``pagas extras``, ``complementos``, ``otrosconceptosretributivos`` y los asigno a ``salariobruto``

- Sumar ``IRPF``, ``seguridad social`` y lo asigno a ``deducciones``

- ``salarioneto`` asigna ``salariobruto`` - ``deducciones``

  

**Paso 3:** Escribir el pseudocódigo

``` 
Algoritmo Calculosalario
	# Entrada
	salariobase<-Leer()
	pagasExtras<-Leer()
	complementos<-Leer()
	otrosconceptosRetributivos<-Leer()
	IRPF<-Leer()
	SeguridadSocial<-Leer()
	# Proceso
	salarioBruto<-salariobase+pagasExtras+complementos+otrosconceptosRetributivos
	deducciones<-IRPF+SeguridadSocial
	salarioNeto<-salarioBruto-deducciones
	# Salida
	Escribir(SalarioNeto)
Fin Algoritmo
```



### Ejercicio 3

_Determinar la ruta para llegar a una ciudad por avión_

**Paso 1:** Definir el problema

El verdadero problema es saber a qué se esta ajustando la premisa "determinar la ruta". En este caso asumiré que se refiere al billete más barato para viajar, como las clásicas webs que comparan páginas de compañías de vuelo. Para ello crearemos un algoritmo que lea la lista de precios de rutas de vuelo que hay con esos criterios de búsqueda y compare dichos precios entre sí para determinar el más barato. En caso de no encontrar vuelos disponibles dirá que no es posible encontrar billete en estos momentos para ese destino.

**Paso 2:** Poner la entrada, el proceso y la salida

Entrada: ``localización``, ``destino`` y ``listarutas`` 

Proceso:

- Si no existen billetes disponible asignará a ``resultado`` que no hay billetes disponibles.
- Si sí que existen pero solo una ruta asignará a ``resultado`` dicho precio de ruta albergado en ``listarutas``.
- Si sí que existen y son más de 1 iniciará una comparación entre ``precio`` y todos los elementos de ``listarutas`` hasta que se acaben.
- Una vez acabado el bucle asignará a ``resultado`` la frase "La ruta más barata esta por valor de " más el precio mas barato filtrado.

Salida:

Escribir ``resultado``

**Paso 3:** Escribir el pseudocódigo

``` 
Algoritmo Rutasvuelos
	# Entrada
	Localizacion<-Leer()
	destino<-Leer()
	listarutas<-Leer(Localizacion, destino)
	precio<-(100000000000000000000000)
	i<-0
	# Proceso
	si listarutas.lenght = 0
		resultado<- "Lo sentimos, No es posible encontrar billete para ese destino en estos momentos."
	si listarutas.length = 1
		resultado<- "El trayecto más barato es "+listarutas+"."
	si listarutas.length>1
		Repetir
			si listarutas[i]<precio hacer
				precio<-listarutas[i]
				i<-i+1
			Sino
				i<-i+1
			FinSi
		Hasta i=listarutas.length
		resultado<- "La ruta más barata esta por valor de "+precio+"."
	FinSi
	# Salida
	Escribir resultado
Fin Algoritmo
```



### Ejercicio 4

_Calcula el área y perímetro de un círculo dado su radio._

**Paso 1:** Definir el problema

Debemos implementar las ecuaciones ``A=Pir2``, ``P=2PiR``

**Paso 2:** Poner la entrada, el proceso y la salida

Entrada: ``Area``, ``Perimetro``, ``Pi``, ``Radio``

Proceso:

- Multiplicar ``Radio`` por sí mismo, por ``Pi y asignar`` a  ``Area``
- Multiplicar ``Radio`` por ``Pi, por 2 y asignar a ``Perímetro``

Salida:

Escribir ``Area`` y ``Perímetro``

**Paso 3:** Escribir el pseudocódigo

``` 
Algoritmo AreaPerimetro
	# Entrada
	Radio<-Leer()
	Pi<-3,14159264
	# Proceso
	Area<-Radio*Radio*Pi
	Perímetro<-Radio*Pi*2
	# Salida
	Escribir (Area, Perímetro)
Fin Algoritmo
```



### Ejercicio 5

_Dada una lista de números enteros, determina cuál es el mayor y cuál es el menor._

**Paso 1:** Definir el problema

El problema es cómo determinar qué numero de todos es el mayor y cual el menor. Para ello asignaremos el primer elemento de dicha lista como número mayor y número menor y luego iremos iterando sobre cada elemento del resto de la lista comparándolo con el mayor de la lista y el menor, determinando así al finalizar cuales han sido los mayores y menores números de la totalidad.

**Paso 2:** Poner la entrada, el proceso y la salida

Entrada: ``listanum``

Proceso:

- Hacer un bucle de resta y comparación de los número de la lista
- según los resultados asignar los números a ``mayornum`` y ``menornum``

Salida:

Escribir  ``mayornum`` y ``menornum``

**Paso 3:** Escribir el pseudocódigo

``` 
Algoritmo comparadordetamaños
	# Entrada
	listanum<-Leer()
	mayornum<-listanum[0]
	menornum<-listanum[0]
	# Proceso
	Para i=0 hasta listanum.lungitud-1 con paso 1 hacer
		si listanum[i]>mayornum
			mayornum<-listanum[i]
		sino si listanum[i]<menormun
			menornum<-listanum[i]
		Finsi
	# Salida
	Escribir (mayornum, menornum)
Fin Algoritmo
```



### Ejercicio 6

_Crea un algoritmo que convierta grados Celsius a Fahrenheit._

**Paso 1:** Definir el problema

Dado un dato de entrada numérico que se asume que es ``GradosCelsius``, aplicar la siguiente fórmula: ºF=ºCx1.8+32

**Paso 2:** Poner la entrada, el proceso y la salida

Entrada: ``GradosCelsius``

Proceso:

- Multiplicar ``GradosCelsius`` por 1.8, sumarle 32 y asignarle este resultado a ``GradosFahrenheit``

Salida:

Escribir ``GradosFahrenheit``.

**Paso 3:** Escribir el pseudocódigo

``` 
Algoritmo conversorGrados
	# Entrada
	GradosCelsius<-Leer()
	# Proceso
	GradosFahrenheit<-GradosCelsius multiplicado por 1.8+32
	# Salida
	Escribir (GradosFahrenheit)
Fin Algoritmo
```



### Ejercicio 7

_Dado un número entero, crea un algoritmo que determine si es par o impar._

**Paso 1:** Definir el problema

Discernir si el numero dado es divisible entre dos, y por tanto determinar si es par o impar.

**Paso 2:** Poner la entrada, el proceso y la salida

Entrada: ``Numero``

Proceso:

- Dividir ``Numero`` entre 2.
- Asignar en funcion del resultado un boolean de verdadero o falso a ``ResultadoPar``

Salida:

Si ``resultadoPar``=verdadero, escribir "Tu número es par"

Si ``resultadoPar``=falso, escribir "Tu número es falso"

**Paso 3:** Escribir el pseudocódigo

``` 
Algoritmo parimpar
	# Entrada
	Numero<-Leer()
	# Proceso
	si numero mod 2 = 0 Entonces
		resultadoPar=verdadero
	sino
		resultadoPar=falso
	Fin si
	# Salida
	Si resultadoPar=verdadero
		escribir "Tu número es par"
	Sino
		escribir "Tu número es falso"
	Fin si
Fin Algoritmo
```



### Ejercicio 8

_Crea un algoritmo que determine si un año es bisiesto o no._

**Paso 1:** Definir el problema

Para saber si un año es bisiesto debe cumplir una de estas dos condiciones, o que sea divisible entre 4 o que sea divisible entre 400 y 100 al mismo tiempo. Utilizando estos dos condicionales escribimos un Algoritmo que nos de un resultado en función de la cuenta matemática.

**Paso 2:** Poner la entrada, el proceso y la salida

**Paso 3:** Escribir el pseudocódigo

``` 
Algoritmo AnyoBisiesto (entero anyo)
	Escribir "Introduzca un anyo"
	# Entrada
	anyo<-Leer()
	# Proceso
	Si anyo mod 4 = 0 o anyo mod 400 = 0 y anyo mod 100 = 0 Entonces
		Resultado<-Anyo+" es bisiesto"
	Si No
		Resultado<-Anyo+" no es bisiesto"
	# Salida
	Escribir Resultado
FinAlgoritmo
```



### Ejercicio 9

_Crea un algoritmo que determine si una cadena de texto es un palíndromo o no._

**Paso 1:** Definir el problema

Para determinar si una cadena de texto es palíndromo (que se lee igual de izquierda a derecha, o en otras palabras, que invertir los caracteres se lee de la misma manera) hemos de comparar los elementos de la cadena desde sus extremos hasta el centro para asegurarnos que sea simétrica, y por tanto un palíndromo. Para ello utilizaremos 2 contadores, uno que se sitúa al principio de la cadena de texto y otro que se sitúa al final. Ocurren dos casuísticas, que la cadena tenga un número de elementos pares (en cuyo caso no tendrá un elemento central), o que la cadena sea impar (en cuyo caso sí que tendrá un elemento central). Esto es determinante a la hora de establecer la última iteración de comparación de los elementos. En el caso de la cadena par será en el momento en que el contador inicial y el final les separe un valor de 1 de posición y en el caso impar será el elemento central. Una vez analizada esta casuística y separados estos dos apartados en el algoritmo iniciamos en cada uno un bucle de repetición que comparará los elementos hasta el final. Si se llega a la última comparación y es correcta se asignara a resultado que es palíndromo. Si en algún momento los elementos comparados no son iguales se le asignará a resultado que no son palíndromos y el bucle se romperá ya que su condición es hasta que se le asigne un valor a resultado.

**Paso 2:** Poner la entrada, el proceso y la salida

Entrada:``Cadenatxt``

Proceso:

- Asignamos los valores correspondientes al largo de la cadena de texto a ``nmin`` y a ``nmax``, siendo estos 0 y el valor que corresponde a la máxima posición de la cadena.
- Asignamos a ``resultado`` un conjunto vacío.
- Para la cadena de palíndromos par iniciamos un bucle que compara los elementos de los extremos y, si son iguales avanza hacia el centro de la cadena sumando 1 a ``nmin`` y restando 1 a ``nmax``.
- En el momento que se llega a la última comparación, si los elementos vuelven a ser iguales se le asigna a ``resultado`` que son palíndromos y el bucle se termina porque resultado no tiene asignado un conjunto vacío.
- Si en cualquier momento los elementos no son iguales se le asigna a ``resultado`` que no son palindromos y el bucle termina de nuevo por el mismo motivo.
- Para la cadena impar hacemos lo mismo solo que la ultima comparación se da con un condicionante diferente, y es que se llegue a l último elemento, sin tener que compararlo con ningún otro porque es el centro de la cadena.

Salida:

Escribir ``resultado``

**Paso 3:** Escribir el pseudocódigo

``` 
Algoritmo palindromos
	# Entrada
	Cadenatxt<-leer()
	nmin<-0
	nmax<-cadenatxt.lenght-1
	Resultado<-()
	# Proceso
	# Cadena de palindromos par
	si cadenatxt.lenght mod 2 = 0 hacer
        Repetir
        	si nmax no = a nmin
        		Si cadenatxt[nmin]=cadenatxt[nmax]
        			nmin<-nmin+1
        			nmax<-nmax-1
             	Sino
        			resultado<-"Tu cadena de texto no es un palindromo"
        		FinSi
   	# última comparación de la Cadena de palindromos par
        	si nmax=nmin+1
        		Si cadenatxt[nmin]=cadenatxt[nmax]
        			Resultado<-"Tu cadena de texto es un palindromo"
        		sino
        			resultado<-"Tu cadena de texto no es un palindromo"
        		FinSi
			FinSi
        Hasta que Resultado no = a ()
	# Cadena de palindromos impar
	si cadenatxt.leght mod 2 > 0 hacer
	        Repetir
        	si nmax>nmin hacer
        		Si cadenatxt[nmin]=cadenatxt[nmax] hacer
        			nmin<-nmin+1
        			nmax<-nmax-1
             	Sino
        			resultado<-"Tu cadena de texto no es un palindromo"
        		FinSi
	 # última comparación de la Cadena de palindromos impar
        	si nmax=nmin
        		Resultado<-"Tu cadena de texto es un palindromo"
			FinSi
        Hasta que Resultado no = a ()
	FinSi
	# Salida
	Escribir resultado
Fin Algoritmo
```



### Ejercicio 10

_Dada una lista de nombres, crea un algoritmo que ordene la lista alfabéticamente._

**Paso 1:** Definir el problema

Debemos ordenar una lista alfabéticamente y para ello deberemos crear una lista de salida ordenada. Iteraremos sobre ella, colocando el elemento no ordenado más pequeño en la posición correcta en la parte ordenada de la lista.

**Paso 2:** Poner la entrada, el proceso y la salida

Entrada:

``lista``

Proceso:

- Calculamos la longitud de la lista y la almacenamos en una variable llamada ``n``.
- Creamos una copia de la lista original llamada ``listaOrdenada``.
- Luego iteramos sobre los elementos de la lista.
- Dentro del primer bucle, seleccionamos el elemento en el índice actual ``i`` y lo almacenamos en una variable llamada ``menorPalabra``.
- Luego iteramos sobre la parte no ordenada de la lista (desde el índice ``i`` hasta el final de la lista) para encontrar el elemento más pequeño en esta parte no ordenada.
- Dentro del segundo bucle, si se encuentra un elemento que es más pequeño que el ``menorPalabra`` previamente asignado, actualiza ``menorPalabra`` con este nuevo elemento más pequeño y almacena su índice en una variable llamada ``posicion``.
- Una vez que se completa el segundo bucle, intercambiamos el elemento en el índice actual ``i`` con el elemento más pequeño encontrado  y actualizamos ``listaOrdenada`` en consecuencia.
- El primer bucle continúa hasta que todos los elementos estén en sus posiciones de ordenamiento correctas.

Salida:

Escribir listaOrdenada

**Paso 3:** Escribir el pseudocódigo

``` 
Algoritmo ListaOrdenada
    # Entrada
    lista <- Leer()
    # Proceso
    n <- ContarElementosLista(lista)
    listaOrdenada <- lista
    Para i=0 Hasta n-2 con paso 1 Hacer
        menorPalabra <- listaOrdenada[i]
        Para j=i Hasta n-1 con paso 1 Hacer
            Si menorPalabra es mayor que listaOrdenada[j] Entonces
                menorPalabra <- listaOrdenada[j]
                posicion <- j
            FinSi
        FinPara
        temporal <- listaOrdenada[i]
        listaOrdenada[i] <- menorPalabra
        listaOrdenada[posicion] <- temporal
    FinPara
    # Salida
    Escribir(listaOrdenada)
FinAlgoritmo
```



### Ejercicio 11

_Crea un algoritmo que calcule el factorial de un número entero_

**Paso 1:** Definir el problema

Crear un algoritmo que multiplique un número dado por todos los anteriores enteros a él. Para ello crearemos una lista y colocaremos el numero dado en su posición correspondiente a su valor. Luego colocamos todos los números desde ese hasta 1 en la lista de manera descendente. Tras esto multiplicamos resultado (que inicialmente es 1) por el mayor elemento de la lista y lo vamos repitiendo hasta la llegar a 1. El resultado de toda esta operación será el número que buscamos.

**Paso 2:** Poner la entrada, el proceso y la salida

Entrada: ``num``

Proceso:

- Crear una lista que contenga a ``num`` en la posición que dicte su valor
- Agregamos uno a uno todos los números que le preceden hasta llegar a 1
- multiplicamos todos los elementos de la lista creada y lo asignarlo a ``resultado``

Salida:

Escribir ``resultado``

**Paso 3:** Escribir el pseudocódigo

``` 
Algoritmo factorial
	# Entrada
	num<-Leer()
	lista<-()
	resultado<- 1
	# Proceso
	Para i=num-1 hasta i=0 con paso -1 hacer
		lista add num
		num<-num-1
	FinPara
    Para i=lista.length-1 hasta i=0 con paso -1 hacer
    	resultado<-resultado*lista[i]
	# Salida
	Escribir resultado
Fin Algoritmo
```



### Ejercicio 12

_Dado un número entero, crear un algoritmo que determine si es primo o no._

**Paso 1:** Definir el problema

Un número primo es aquel que solo es divisible por el mismo y por 1. Debemos hacer un algoritmo que divida un numero dado por todos los anteriores enteros hasta llegar a 1 y con ello comprobar la condición de primo. Ya que 0 y 1 no son primos porque no cumplen con la definición los añadiremos como excepciones. También lo serán 2 y 3 ya que son los dos numero imnediatos a los anteriores y son primos, no necesitando de divisiones para su comprobación. A partir de aquí si que se dividirá y comparará el resultado para determinar si solo es divisible entre sí mismo y 0.

**Paso 2:** Poner la entrada, el proceso y la salida

Entrada: ``num``

Proceso:

- Crear un ``divisor ``, que estará dividiendo a ``num``
- Crear las excepciones para ``num``<0,``num``=0, ``num``=1, ``num``=2 y ``num``=3
- Creamos un bucle que repetirá la operación de división entre ``num`` y ``divisor``, restándole 1 a ``divisor`` hasta que llegue a alguna de las casuísticas antes enumeradas, siempre y cuando el resto no sea 0.
- En caso de tener resto 0 antes de llegar a 1 asignar a ``resultado`` "No es primo"
- En caso de no tener resto 0 antes de llegar a 1 asignar a ``resultado`` "Si es primo"

Salida:

Escribir resultado

**Paso 3:** Escribir el pseudocódigo

``` 
Algoritmo numerosprimos
	# Entrada
	num<-Leer()
	divisor<-num-1
	# Proceso
	Si num<0
		resultado<-"Solo son numeros primos aquellos enteros divisibles entre ellos y 1."
	Si num=0
		resultado<-"0 no es primo porque no se puede dividir.""
	Si num=1
		resultado<-"1 no es primo porque no tiene más de un divisor."
	Si num=2
		resultado<-"Es primo"
    Si num=3
    	resultado<-"Es primo"
    Si num>3hacer
		Repetir
            num mod divisor no es igual a 0
				divisor-1
			si num mod divisor es igual a 0
				resultado<-"No es un número primo"
				divisor<-1
			Finsi
		Hasta divisor=1
		si resultado=() entonces
			resultado<-"Si es un número primo"
		FinSi
	Finsi
	# Salida
	Escribir resultado
Fin Algoritmo
```



### Ejercicio 13

_Crea un algoritmo que calcule el área y volumen de un cubo dado su lado_

**Paso 1:** Definir el problema

El área de un cubo se calcula con la formula 6 por el lado al cuadrado, y el volumen es el lado al cubo. Debemos realizar un algoritmo que realice estas operaciones.

**Paso 2:** Poner la entrada, el proceso y la salida

Entrada: ``lado``

Proceso:

- Multiplicamos ``lado`` por ``lado`` y lo asignamos a ``cuadrado``
- Multiplicamos ``cuadrado`` por ``6`` y lo asignamos a ``Area``
- Multiplicamos ``cuadrado`` por ``lado`` y lo asignamos a ``volumen``

Salida:

Escribir`` Area`` y ``cubo``

**Paso 3:** Escribir el pseudocódigo

``` 
Algoritmo Rutasvuelos
	# Entrada
	lado<-Leer()
	cuadrado<-()
	# Proceso
	cuadrado<-lado*lado
	Area<-cuadrado*6
	volumen<-cuadrado*lado
	# Salida
	Escribir "A="+Area". y V="+volumen"."
Fin Algoritmo
```



### Ejercicio 14

_Dada una lista de números enteros, crea un algoritmo que calcule la suma de todos los números pares de la lista._

**Paso 1:** Definir el problema

En función de si los elementos de una lista de números son pares o impares, sumaremos aquellos que sean pares. Lo que determinará dicha condición es si el resto de dividirlo entre 2 da resto cero. En ese caso podemos decir que es par y por tanto considerarlo apto para la suma en el algoritmo.

**Paso 2:** Poner la entrada, el proceso y la salida

Entrada: ``lista``

Proceso:

- Recorrer la lista identificando si cada número es par
- Sumar a ``suma`` los que sean pares.

Salida:

Escribir ``suma`` en el resultado.

**Paso 3:** Escribir el pseudocódigo

``` 
Algoritmo Rutasvuelos
	# Entrada
	lista<-Leer()
	suma<-0
	# Proceso
	Para i=0 hasta i=lista.length con paso 1 hacer		
		Si lista[i] mod 2 = 0 entonces
			suma<-suma+lista[i]
		Finsi
	Finpara
	# Salida
	Escribir<-"La suma de los números pares de la lista es"+suma"."
Fin Algoritmo
```



### Ejercicio 15

_Crea un algoritmo que determine si un número es positivo, negativo o cero._

**Paso 1:** Definir el problema

Debemos crear un algoritmo que posicione mediante un switch la condición del número dado en función a 3 posibles casos.

**Paso 2:** Poner la entrada, el proceso y la salida

Entrada: 

``num``

Proceso:

- Un switch de 3 variables: mayor que cero, cero o menor que cero.
- Asignar una respuesta.

Salida:

Escribir respuesta.

**Paso 3:** Escribir el pseudocódigo

``` 
Algoritmo numerocero
	# Entrada
	num<-Leer()
	# Proceso
	Segun num hacer
		caso, num<0
			resultado<-(num+" es menor que cero.")
		caso, num>0
			resultado<-(num+" es mayor que cero.")
		caso, num=0
			resultado<-(num+" es cero.")
	Finsegun
	# Salida
	Escribir resultado
Fin Algoritmo
```



### Ejercicio 16

_Dada una lista de número enteros, crea un algoritmo que calcule la media de la lista_

**Paso 1:** Definir el problema

Debemos sumar todos los números de la lista y dividir el resultado entre el número de elementos de la lista.

**Paso 2:** Poner la entrada, el proceso y la salida

Entrada: ``lista``

Proceso:

- Sumar todos los números de la lista.
- dividir el resultado entre el número de elementos de la lista.
- asignar ese nuevo numero a ``resultado``.

Salida:

Escribir ``resultado``

**Paso 3:** Escribir el pseudocódigo

``` 
Algoritmo Rutasvuelos
	# Entrada
	lista<-Leer()
	suma<-0
	# Proceso
	Para i=0 hasta i=listanum.length-1 con paso 1 hacer
		suma<-lista[i]+suma
	Fin Para
	resultado<-suma/listanum.length-1
	# Salida
	Escribir "La media de la lista es "+resultado+"."
Fin Algoritmo
```



### Ejercicio 17

_Crea un algoritmo que genere un número aleatorio entre 1 y 100, y le pida al usuario adivinarlo. El
algoritmo deberá indicar si el número introducido es mayor o menor que el número aleatorio, hasta
que el usuario adivine el número correcto_

**Paso 1:** Definir el problema

Crear un algoritmo que de un número aleatorio y un comparador entre el numero escogido al azar y el numero que da el usuario hasta que acierte.

**Paso 2:** Poner la entrada, el proceso y la salida

Entrada: 

``nuser``

Proceso:

- Generar ``nalea``
- comparar ``nuser`` y ``nalea``
- dependiendo del resultado asignar a ``resultado`` "es más grande", "es más pequeño" o "¡Ese es!"

Salida:

Escribir ``resultado``

**Paso 3:** Escribir el pseudocódigo

Formula de generador lineal congruencial:
$$
X_{i}=\left(aX_{i-1}+c\right){\bmod {m}}
$$


``` 
Algoritmo Rutasvuelos
	# Entrada
	nalea<-valor entre 1 y 100.
	intento<-0
	# Proceso
	Repetir
		nuser<-Leer()
		intento<-intento+1
		si nuser<nalea
			Escribe<-("Es más grande. Prueba de nuevo.")
		si nuser>nalea
			Escribe<-("Es más pequeño. Prueba de nuevo.")
		si nuser=nalea
			resultado<-("¡Ese es!¡Lo adivinaste!")
	Hasta que resultado<-("¡Ese es!¡Lo adivinaste!")
	# Salida
	Escribir resultado+"Estos han sido tus intentos"+intentos
Fin Algoritmo
```



### Ejercicio 18

_Crea un algoritmo que determine si una cadena de texto es un anagrama de otra cadena de texto._

**Paso 1:** Definir el problema

Debemos determinar si dos cadenas de texto tienen los mismos caracteres desordenados. Para ello haremos una copia de la segunda cadena para compararla con primera e ir borrando los elementos repetidos en ambas. Si al final de la comparación la copia esta vacía de elementos las cadenas serán anagramas. En caso contrario no.

**Paso 2:** Poner la entrada, el proceso y la salida

Entrada: ``cadena1`` y ``cadena2``

Proceso:

- Asignamos ``cadena2`` a un array llamado ``temp``
- Recorremos la ``cadena1``  y  ``cadena2`` simultáneamente.
- En caso de encontrar una coincidencia borramos de ``temp`` dicho elemento
- Si tras compararlas ``temp`` termina vacío asignamos a ``resultado`` que son anagramas
- Si no es el caso le asignamos lo contrario

Salida:

Escribir ``resultado``

**Paso 3:** Escribir el pseudocódigo

``` 
Algoritmo Rutasvuelos
	# Entrada
    cadena1<-Leer()
    cadena2<-Leer()
    temp <- cadena2
    contador <- 0
	# Proceso
    Para i = 0 Hasta longitud cadena1 Con Paso 1
      Para j = 0 Hasta longitud cadena2 Con Paso 1
        Si cadena1[i] = cadena2[j] Entonces
          Borrar(temp[j - contador])
          contador = contador + 1
        Fin Si
      Fin Para
    Fin Para

    Si temp = "" Entonces
      resultado<-cadena1 + " y "+ cadena2 + " son anagramas"
    Sino
      resultado<-cadena1 + " y "+ cadena2 + " no son anagramas"
    Fin Si	
	# Salida
	Escribir resultado
Fin Algoritmo
```



### Ejercicio 19

_Dada una lista de números enteros, crea un algoritmo que elimine los números duplicados de la
lista._

**Paso 1:** Definir el problema

Debemos crear un algoritmo que compare cada elemento que exista en la lista con el resto de elementos para que no haya pares duplicados de información. Para ello crearemos una lista resultado a la que iremos copiando cada elemento de la lista original, comparando con los elementos ya existentes en la lista resultado.

**Paso 2:** Poner la entrada, el proceso y la salida

Entrada: ``lista``

Proceso:

- Creamos ``listares`` y copiamos el primer elemento de ``lista``
- Con un contador ``i``, generamos un bucle que compare el siguiente elemento de ``lista`` con los elementos de ``listares``

Salida:

Escribir ``listares``

**Paso 3:** Escribir el pseudocódigo

``` 
Algoritmo Rutasvuelos
	# Entrada
	lista<-Leer()
	listares<-()
	# Proceso
	Repetir
		Para i=0 Hasta lista.lenght=i hacer
			si lista[i] distinto a listares[desde listares[0] hasta listares[listares.lenght-1]]
				listares add lista[i]
			Finsi
		FinPara
	# Salida
	Escribir listares
Fin Algoritmo
```



### Ejercicio 20

_Crea un algoritmo que determine si un número es capicúa o no._

**Paso 1:** Definir el problema

En matemáticas, la palabra capicúa se refiere a cualquier número que se lee igual de izquierda a derecha que de derecha a izquierda.

Debemos hacer un algoritmo que copie el numero dado, lo invierta, y compare los dos números resultantes para validar o no su condición de capicúa.

**Paso 2:** Poner la entrada, el proceso y la salida

Entrada: 

``Num``

Proceso:

- Recorrer ``Num``  y copar cada valor en una posición invertida en ``Numin``
- Comparar ``Num`` y ``Numin``
- asignar un valor booleano a ``resultado`` en función de la comparación.

Salida:

Escribir ``Resultado``

**Paso 3:** Escribir el pseudocódigo

``` 
Algoritmo Capicua
	# Entrada
	num<-Leer()
	numin[num.length] # Dimensionamos la lista vacia
	j<-0
	# Proceso
	# Inversion del numero
	Desde i=num.lenght-1 hasta i=-1 con paso i-- hacer
		numin[j]<-num[i]
		j<-j+1
	#comparador
	si Num=Numin
		resultado<-(Num+" es capicua.")
	sino
		resultado<-(Num+" no es capicua.")
	Finsi
	# Salida
	Escribir resultado
Fin Algoritmo
```


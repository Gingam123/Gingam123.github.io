# ÁLGEBRA LINEAL: MATLAB
MATLAB, abreviación de _maitrx laboratory_, es un lenguaje de programación y entorno de computación. 

[Guia de MathWorks](https://la.mathworks.com/help/matlab/matlab_prog/)

`\n` representa que lo que le sigue se debe escribir en una línea nueva

![GUI](.\matlabgui.png)
Todo lo que nos interesa está en _`Live Editor`_.

### Comandos
|  |
|----------|
|• ```save [nombre]``` para guardar el espacio de trabajo en un archivo .mat con un nombre
• ```clear``` para eliminar todas las variables
• ```load [nombre]``` para cargar las variables de un archivo
• ```load [nombre del archivo] [nombre de la variable]``` para cargar solo el valor de una variable
• ```[nombre de la variable]``` para ver el contenido de una variable
• `clc` para vaciar la ventana de comandos|

### Aritmética
| |
|---|
|• La variable `ans` almacena las respuesta por defecto, se pueden usar otras variables.
• `x = x + 1` es válido aquí también.
• Usar un `;` al final de un comando suprime su salida en el terminal.
• Flecha arriba para regresar a comandos anteriores.
• Si se usa una variable para calcular el valor de otra y se cambia la primera, no se altera el resultado de la misma.
• Las variables solo pueden contener letras y guiones bajos
• `pi` y otras constantes están ya incorporadas
•  `.*` multiplica los elementos correspondientes de un arreglo de cualquier tamaño. Funciona para otros operadores como `+,-,/` y `^`.|

### Funciones
||
|-|
|FUNCIONES
• Las funciones se representan con paréntesis, como en la notación matemática estándar
• `format [long/short/…]`\n`[variable]` para cambiar el formato en el que se muestra
• `x = rand(2,3)` crea una matriz 2x3 de números aleatorios
•  `x = zeros(6,3)` crea una matriz de 6x3 llena de zeros
•  `y = rand(size(x))` usa la función `size` que retorna las dimensiones de una matriz como argumento para crear otra dentro de la función “rand”
•  `max(X)` retorna el máximo valor de un vector
•  `sqrt()` y `round()` también aplican para arreglos enteros
•  `size(X)` devuelve las dimensiones de `X`. `[dr, dc] = size(data)` asigna esos valores 
•  En `[vMax, ivMax] = max(v2)` vMax es el valor máximo de v2 y ivMax es su índice
•  `[~,ivMin] = min(v2)` ignora el valor y solo retorne el índice usando la nubecita esa. d = v2(ivMin) es el valor
•  `x = randi([1,20],5,7)` retorna una matriz 5x7 con valores aleatorios uniformemente distribuidos entre 1 y 20
•  `doc [algo]` abre la documentacion sobre eso
•  `n = numel( A )` returns the number of elements
•  `lenght(X)` se usa como el `len(x)` en python
• `rref(X)` retorna la matriz escalonada reducida por filas y los indices de los pivotes
• `inv(A)` retorna la unversa de la matriz|

### Arreglos
| |
|---|
|
•  `x(i,j)` retorna los elementos de la matriz `x` dentro del rango especificado
•  `x(i;:)` o  `x(:,j)` retorna todos hasta cierto tope o desde cierto tope, usando `:` tal como en Python
•  `x = A(1:3,:)` Crea una matriz que contiene las filas primera, segunda y tercera de la matriz A.
•  `x = data(y)` recorrió todos los elementos de la primera columna, de la segunda, de la tercera, n columnas, hasta llegar al `y` elemento recorrido. Se pueden usar variables como argumentos.
•  `x = data(end,3)` se va a la última fila, tercer elemento. Se pueden usar operadores aritméticos junto a end, como por ejemplo, para ir a la penúltima fila/columna, la de la mitad, etc
•  `x(1,1) = 0.5` Cambia el valor en una posisción. Se puede combinar asignación con indexación 
• `x = 4` es un escalar, un arreglo de 1x1
• `x = [7,9]` es una fila vector
• `x = [7;9]` es una columna vector
•  `x = [sqrt(10), (pi)^2] = [3.1623   9.8696]`
•  `x = [1:4] = [1  2  3  4]`
•  `x = [1:0.5:5] = [1   1.5   2   2.5   3   3.5   4   4.5   5]`
•  `x = linspace(1,10,5)` crea 5 elementos que empiezan desde el 1 y terminan en 10 sin uno saber necesariamente el espaciado entre cada uno
•  `x = x’` traspone x de tal forma que un vector fila se convierte en un vector columna
•  `x = [5:2:9]’` crea un vector fila que comienza en 5, termina en 9, tiene espaciado de 2 números y al final se traspone a columna
•  `x = linspace(1,2*pi,100)` Usar operadores aritméticos en funciones y arreglos tipo `[]` es válido
•  Se puede sumar o multiplicar un escalar a cada elemento de un arreglo con la notación `y = A + n`, donde `A` es una matriz. Aplica también para la suma de arreglos del mismo tamaño.
|

### Lógica
| |
|---|
|
• Operadores lógicos de siempre mas and `&` y or `\|`
• `x = v1 < 4` Compara cada elemento de v1 a 4 y retorna una matriz donde hay un 1 si se cumple la condición y un 0 si no
• `v = v1(v1<4)` multiplica cada valor de v1 por la matriz donde hay 0 y 1 de tal forma que solo quedan los que cumplen la condición
• Ejemplo de indexación: `sample(v1 < 4)` o `v1(v1 < 4) = 0`
|

### Estructuras de control
| |
|---|
|
• `if/while (condicion)` \n `elseif` \n `else` \n `End`
• `for x = a:b … end`
• `pause(t)` pausa el bucle 
|

### Importación de datos
| |
|---|
|
• `x = columna.tabla` asigna la columna de la tabla importada a una variable
• `elements.Mass = elements.Density.*elements.Volume1` crea una columna si no existe y multiplica cada termino correspondiente por fila
• Al realizarle cambios a la tabla, se puede poner `tabla = sortrows(tabla, "Columna")`
• `top3 = elements(1:3,:)` es un ejemplo de extraer una parte de la tabla y que también se guarden como tabla
|

### Gráficas
| |
|---|
|
• `plot(x, y,[color] )` https://la.mathworks.com/help/matlab/ref/linespec.html
• `hold on` seguido de `plot` superpone gráficas. `hold off` para regresar a gráficas individuales
• `plot([x])` usa los valores del vector como eje y y establece el eje x entre 1 y n elementos del vector
• `plot([x], “LineWidth”, n)` para cambiar el ancho de la fila. [Ver lista de gráficas](https://la.mathworks.com/help/matlab/ref/matlab.graphics.chart.primitive.line-properties.html)
• https://la.mathworks.com/products/matlab/plot-gallery.html#
• `title(”Título”)` se añade en cadena. Se puede usar valores de variables aquí también
• `legend(”a”, “b”, “c”)` añade una leyenda a las gráficas en el orden en el que se pusieron
• `xlim([0,1000])` seguido de plot grafica solo una parte de todos los datos
|


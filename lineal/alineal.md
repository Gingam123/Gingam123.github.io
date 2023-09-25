# Matrices y Vectores
- [Matrices y Vectores](#matrices-y-vectores)
  - [Construir matrices, operar e identificar diferentes tipos](#construir-matrices-operar-e-identificar-diferentes-tipos)
    - [Igualdad de matrices](#igualdad-de-matrices)
    - [Aritmética Matricial](#aritmética-matricial)
    - [Operaciones con matrices](#operaciones-con-matrices)
- [\\end{bmatrix}](#endbmatrix)
- [\\end{bmatrix}](#endbmatrix-1)
    - [Matrices especiales](#matrices-especiales)
    - [Operaciones elementales](#operaciones-elementales)
    - [Matriz escalonada](#matriz-escalonada)
    - [Matriz inversa](#matriz-inversa)
  - [Propiedades](#propiedades)
    - [Rango](#rango)
    - [Determinante](#determinante)
  - [Sistemas de ecuaciones lineales](#sistemas-de-ecuaciones-lineales)
    - [Eliminación Gaussiana](#eliminación-gaussiana)
    - [Consistencia](#consistencia)
  - [Espacios vectoriales](#espacios-vectoriales)
    - [Espacio nulo](#espacio-nulo)
    - [$\\reals^{m}$ como espacio vectorial](#realsm-como-espacio-vectorial)
    - [Independencia lineal](#independencia-lineal)
    - [Base y dimensión](#base-y-dimensión)
    - [Espacio fila, espacio columna y espacio nulo](#espacio-fila-espacio-columna-y-espacio-nulo)
    - [Invarianza, Rango y Nulidad](#invarianza-rango-y-nulidad)
    - [SEL y Espacios fundamentales](#sel-y-espacios-fundamentales)


## Construir matrices, operar e identificar diferentes tipos
Una matriz ***A*** es un arreglo de *m $\times$ n* números reales distribuidos en *m* filas y *n* columnas. A cada elemento dentro de la matriz se le conoce como entrada.
$$
A =
\begin{bmatrix}
   a_{1 1} & a_{12} & a_{13} & \cdots & a_{1n} \\
   a_{21} & a_{22} & a_{23} & \cdots & a_{12n} \\
   \vdots & \vdots & \vdots & \ddots & a_{1n} \\
   a_{m1} & a_{m2} & a_{m3} & \cdots & a_{mn}
\end{bmatrix}
$$

Diremos que una matriz es de tamaño $(m \times n)$ y lo escribiremos simbólicamente como
$$
A = (a_{ij})
$$

donde:
$$
i = 1,2,...,m \\
j=1,2,...,n
$$

### Igualdad de matrices
Dos matrices $A = (a_{ij})$ y $B = (b_{ij})$ son iguales si y solo si:
- ***A*** y ***B*** son del mismo tamaño $(m \times n)$, y
- $\forall i,j:a_{ij}=b_{ij}$

**Ejemplo**
\
Determina el valor de $a$ para que $A$ y $B$ sean iguales.
$$
A =
\begin{bmatrix}
   a & 1 \\
   -1 & 2a
\end{bmatrix}
B =
\begin{bmatrix}
   2 & 1 \\
   -1 & 4
\end{bmatrix}
$$

$a$ debe ser igual a $2$.

### Aritmética Matricial
Suponiendo que los tamaños de las matrices son tales que es posible efectuar las operaciones indicadas, estas reglas son válidas en la aritmética matricial:
- $A+B=B+A$ *(Ley conmutativa para la adición)*
- $A+(B+C)=(A+B)+C$ *(Ley asociativa, adición)*
- $A(BC)=(AB)C$ *(Para la multiplicación)*
- $A(B+C)=AB+AC$ *(Distributiva)*
- $(B+C)A=BA+CA$ *(Distributiva)*
- $A(B-C)=AB-AC$
- $(B-C)A=BA-CA$
- $a(B+C)=aB+aC$
- $a(B-C)=aB-aC$
- $(a+b)C=aC-bC$
- $(ab)C=a(bC)$
- $a(BC)=(aB)C=B(aC)$
\

Adicionalmente:
- $A+0=0+A=A$ 
- $A-A=0$
- $0-A=-A$
- $A0=0;\ 0A=0$
- $AA^{-1}=I$ y $A^{-1}A=I$, donde $I$ es la matriz identidad

### Operaciones con matrices

Multiplicación por escalar
>Sea un escalar $\lambda \in \reals$ y una matriz $A=(a_{ij})$, cada entrada de su producto, la matriz $\lambda A = (m_{ij})$ se define como:
>$$
m_{ij} = \lambda \times a_{ij}
$$

Suma
>Dadas las matrices ***A*** y ***B*** de iguales dimensiones, se define su suma como:
>$$
A+B=(s_{ij})
>$$
>donde
>$$
s_{ij}=a_{ij}+b_{ij}
$$

Multiplicación de matrices
>Sean 2 matrices ***A $=(a_{1j})$*** y ***B $=(b_{i1})$***, se define su producto como:
>$$
\begin{bmatrix}
    a_{11} & a_{12} & \dots a_{1n}
\end{bmatrix}
\times
\begin{bmatrix}
    a_{11}  \\
    a_{21} \\
    \dots \\
    a_{n1} \\
\end{bmatrix}
=
a_{11}b_{11}+a_{12}b_{12}+\dots a_{1n}b_{n1}
$$

>Sean 2 matrices ***A $=(a_{i1})$*** y ***B $=(b_{1j})$***, se define su producto como:
>$$
\begin{bmatrix}
    a_{11}  \\
    a_{21} \\
    \dots \\
    a_{i1} \\
\end{bmatrix}
\times
\begin{bmatrix}
    b_{11} & b_{12} & \dots b_{1j}
\end{bmatrix}
=
\begin{bmatrix}
   a_{1 1}b_{1 1} & a_{11}b_{1 2} & \cdots & a_{11}b_{1n} \\
   a_{2 1}b_{1 1} & a_{21}b_{1 2} & \cdots & a_{21}b_{1n} \\
   \vdots & \vdots & \ddots & \vdots \\
   a_{m 1}b_{1 1} & a_{12}b_{1 2} & \cdots & a_{m1}b_{1n} \\
\end{bmatrix}
$$

>Sea $A$ una matriz $(m\times n)$ y $B$ una $(n\times p)$, el producto de ambas será una matriz $C$ de dimensiones $(m\times p)$ tal que cada elemento $c_{ij}$ de la matriz se determina con la sumatoria
>$$
c_{ij}=\sum_{k=1}^{n} a_{ik}b_{kj},\\ 
i\in\{1,...,m\}\\
j\in\{1,...,p\}
>$$
>En otras palabras, para cada termino $c$ debes agarrar la fila en $A$ correspondiente a su $i$ y la columna en $B$ correspondiente a su $j$ y hacer una multiplicación _horizontal_ por _vertical_ como se vio hace 2 casos.

Transpuesta
>Dado una matriz $A$, su transpuesta $A^{t}$ es la matriz donde las columnas de $A$ son las filas de $A^{t}$ y las filas son las columnas.

### Matrices especiales

- **La matriz _cero_** de tamaño $n \times m$  es aquella donde todas sus componentes son nulas (cero).
- **La matriz cuadrada**, cuando sus dimensiones son iguales. Se dice que es de orden _n_, con _n_ representando las dimensiones de la matriz.
- **Matriz identidad**, una matriz $m \times n$ donde su diagonal principal está compuesta por $1$ y el resto de componentes son $0$.
  - Es decir, $a_{ij}$=1 si $i=j$ y $0$ en caso contrario
- **Matriz triangular superior o inferior**, cuando todas las componentes por debajo o por arriba de la diagonal superior son $0$ respectivamente.
- Una matriz $A$ es **simétrica** cuando $A^{t}=A$
- Una matriz $A$ es **antisimétrica** cuando $A^{t}=-A$

### Operaciones elementales

### Matriz escalonada
### Matriz inversa

## Propiedades
### Rango
### Determinante

## Sistemas de ecuaciones lineales
### Eliminación Gaussiana
### Consistencia


## Espacios vectoriales
### Espacio nulo
### $\reals^{m}$ como espacio vectorial
### Independencia lineal
### Base y dimensión
### Espacio fila, espacio columna y espacio nulo
### Invarianza, Rango y Nulidad
### SEL y Espacios fundamentales
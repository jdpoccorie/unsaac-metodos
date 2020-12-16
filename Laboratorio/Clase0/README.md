# Base teórica complementaria

## Tipos de datos

* Enteros reales
* Complejos
* Lógicos
* Cadenas de caracteres

## Variables

Las variables le permiten dar nombre a los valores y hacer referencia a ellos mas tarde. Los nombres de variables pueden contener letras, numeros y caracteres underscore (guión bajo), pero el primer caácter tiene que ser una letra.

```m
isvarname(name): Retorna true si name es una variable válida
```

## Entrada y salida de datos

* Entrada: `input()`
* Salida: `disp()`, `printf()`

```
pi
    -> ans = 3.1416
```

Para imprimir el valor de una variable sin imprimir su nombre, use la función `disp`.

```m
disp(x)
str = disp(x) 
# Muestra el valor de x
```
```m
$ disp("El valor de pi es: "), disp(pi)
El valor de pi es:
3.1416  
```
Nota que `disp` siempre termina con una nueva linea

```m
$ ans = input(prompt)
$ ans = input(prompt, "s")
# Imprime el mensaje y espera la entrada del usuario

input("Elija un numero, cualquier numero:")
```

```m
choice = menu(title, opt1, ...)
choice = menu(title, {opt1, ...})
# Muestra un menú con title de encabezado y opciones opt1, ... esperando la entrada del usuario
```

```m
kbhit()
kbhit(1)
# Lee una sola pulsación del teclado, si esta con argumento no espera la pulsacion(devuelve una cadena vacía)
```

## Operadores de asignación

=

## Operadores aritméticos

* Suma: a+b
* Resta: a-b
* Multiplicación: a * b
* División: a / b
* Módulo: mod(a, b)
* Raíz cuadrada sqrt(a)
* Potencia: a^b

## Operadores de comparación
* Menor que: a < b
* Menor o igual que: a <= b
* Mayor: a > b
* Mayor o igual que: a >= b
* Igual a: a == b
* No igual a: a ~= b

## Operadores lógicos
* Or: a | b
* And: a & b
* Or exclusico: xor(a, b)
* Not: ~a ó not(a)

## Rangos
En octave podemos definir un tipo de datos especial, llamado Rango, consistente en una colección ordenada(una serie) de números equidistantes

```m
% rango = inicio : incremento : máximo_valor
rango = 1:2:10
% El resultado será: 1 3 5 7 9

% rango = inicio : máximo valor
rango = 1:4
% El resultado será: 1 2 3 4

rango = 4:-1:0
% El resultado será: 4 3 2 1 0
```

## Estructuras de control condicional

### If

```m
global x = 3;
if (x == 0)
  disp("Equis es igual a cero");

if (x == 0 || x == 5)
  disp("Equis es igual a cero");
endif
```

### IF-Else

```m
global x = 5;
disp('Equis es: ')
if (x>0)
  disp('Positivo')
else
  disp("Negativo")
endif
```

### If-ElseIf

```m
if (true)
  disp("Si es verdad")
elseif (true)
  disp("Aha!!")
endif
```
## Estructuras de control repetitivas

### For

En octave se puede definir rangos que permiten controlar las iteraciones del ciclo For

```m
for variable = vector
  ...
endfor
```

### While
```m
while condition
  ...
endwhile
```

### Do...Until
```m
do
  ...
until condition
```

## Break y Continue
* break: Esta sentencia salta hasta el final del bucle y termina el ciclo (for, while, do-until)
* continue: Esta sentencia salta hasta al inicio del bucle y continua con el ciclo (for, while, do-until)

## Arreglos

### Definición

```m
global rango = 0:90:270
global arr = [rango]
disp(arr)
%% El resultado será: 0    90   180   270
```

```m
az = [0:90:27]
%% El resultado será: 0    90   180   270
```

```m
%% global v = linspace(inicio, fin, num_elementos)
global v1 = linspace(1, 10, 10)
disp(v1) 
%% El resultado es 1    2    3    4    5    6    7    8    9   10
global v2 = linspace(1, 10, 5)
disp(v2) 
%% El resultado es 1.0000    3.2500    5.5000    7.7500   10.0000
```

### Lectura de los elementos de un vector

```
global az = [0:90:270]
disp(az(4)) %% 270
disp(az(end)) %% 270
```

### Recorrer un arreglo

```m
global A = [1, 4, 6, 7];
for k = 1:length(A)
  disp(A(k))
endfor
%% Resultado: 1 4 6 7
```

### Funciones útiles para trabajar con vectores

1. **length(v)** Devuelve el numero de componentes del vector v
2. **max(v), min(v)** Devuelve el valor máximo/mínimo de entre las componentes de v
3. **sum(v), prod(v)** Devuelve la suma/producto de las componentes de v
4. **norm(v)** Devuelve el módulo del vector v
5. **dot(v, w)** Devuelve el producto escalar de los vectores v y w
6. **cross(v, w)** Devuelve el vector producto vectorial de v y w (Las dimensiones de v y w) deben ser congruentes como máximo tres
7. **sort(v)** Devuelve un vector con las componentes de v ordenadas de menor a mayor


## Matrices

### Definición 
Para introducir una matriz por teclado bastará ir tecleando el valor de las componentes encerradas entre corchetes. Se teclea cada fila separada de la anterior por punto y coma `","`, y dentro de cada fila, los elementos se separarán con coma `","` o espacio

```m
global arr = [1, 2; 3, 4]
disp(arr)
```
```m
global arr = [1:10; 11:20]
disp(arr)
```
```m
global arr = [1,2,3; 4,5,6; 7,8,9]
global v1 = [1 2 3]
global v2 = [1 2]
disp(arr)
arr(v1, v2) %% (filas, columnas)
```

## Funciones útiles para crear matrices predefinidas
1. **eye(n)** Forma la matriz identidad cuadrada de dimensión n
2. **zeros(n)** Forma la matriz de ceros cuadrada de dimensión n
3. **zeros(m, n)** Forma una matriz de ceros de m filas y n columnas
4. **ones(n)** Forma una matriz de unos cuadrada de dimensión n
5. **ones(m, n)** Forma una matriz de unos de m filas y n columnas

## Lectura de los elementos de un vector

```
global arr = [1, 2; 3, 4]
arr(1,1)
%% El resultado será: ans = 1
arr(1, end)
%% El resultado será: ans = 2
arr(end, end)
%% El resultado será: ans = 4
```

```
global arr = [1,2,3,4; 5,6,7,8; 9,10,11,12; ,13,14,15,16]
disp(arr)
arr(2:3, 2:3)
%% El resultado sería [6 7; 10 11]
arr([2 4], [2 4])
%% El resultado sería [6 8; 14 16]
```

### Recorrer matrices

```
global matriz = [2,5,6; 3,5,1]
[filas, columnas] = size(matriz)

for i = 1:filas
  for j = 1:columnas
    printf("M(%d, %d) = %d \n", i, j, matriz(i, j))
  endfor
endfor
```

### Funciones útiles para crear matrices predefinidas
1. **size(m)** Devuelve un vector de dos componentes con el número de filas y el número de columnas de la matriz
2. **inv(m)** Devuelve la inversa de la matriz m
3. **det(m)** Devuelve la determinante de la matriz m
4. **max(m), min(m)** Devuelve un vector fila con el máximo/mínimo elemento de cada columna de la matriz
5. **sum(v)** Devuelve un vector fila en la que cada elemento es la suma de los elementos de la columna correspondiente de la matriz

## Funciones

### Definición

```m
function nombre
  # cuerpo
endfunction
```

### Funciones sin parámetros

```
function saludo
  disp('hola')
endfunction
```

### Funciones con parámetros






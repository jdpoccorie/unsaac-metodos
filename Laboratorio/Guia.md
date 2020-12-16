# 1. Prefacio

# 2. Una breve introducción a Octave

# 3. Getting Started

# 4. Tipo de datos

Octave incluye un buen numero de tipos de datos predeterminados como por ejemplo:
* Enteros reales
* Complejos
* Lógicos
* Cadenas de caracteres
* Arrays pueden contener todos los tipos de datos

El tipo de dato por defecto es el tipo **double**

```m
typeinfo(expr): Retorna el tipo de dato de la `expr`
              : Si no se escribe `expr` nos devuelve todos los tipos de datos instalados actualmente(c++)
```

## Tipos de datos integrados

Los tipos de datos integrados son 
* Matrices reales y complejas
* Escalares reales y complejas
* Rangos
* Cadena de caractéres
* Un tipo de estructura de datos
* Cell arrays

```m
class(s, id)
class(s, id, p, ...)
Retorna la clase del objeto `obj`
```
```m
isa(obj, classname): Retorna true si `obj` es de la clase `classname`
```
**classname**: Puede ser *"float"*(comprende las clases double y single), *"integer"*(comprende (u)int8, (u)int16, (u)int32, (u)int64,), *"numeric"*(comprende floating pointer o integer)

```m
cast(val, "type"): Convierte `val` al tipo de dato `"type"`
```
Pueden ser cualquiera de las clases integradas
```
"double"
"single"
"logical"
"char"
"int8"
"int16"
"int32"
"int64"
"uint8"
"uint16"
"uint32"
"uint64"
```



# Operaciones matemáticas básicas

# Índice
1. Operadores aritméticos
2. Orden de operaciones
3. Operadores de asignación
4. Funciones matemáticas útiles
5. Operaciones entre distintos tipos
---
# Operadores aritméticos
Python tiene todos los operadores que conoces de matemáticas, más algunos extras:

```python
a = 10
b = 3

print(a + b)   # 13    → Suma
print(a - b)   # 7     → Resta
print(a * b)   # 30    → Multiplicación
print(a / b)   # 3.333 → División (siempre devuelve float)
print(a // b)  # 3     → División entera (sin decimales)
print(a % b)   # 1     → Módulo (el resto de la división)
print(a ** b)  # 1000  → Potencia (10³)
```

> `//` y `%` son los más raros al principio pero los vas a usar muchísimo.
> Piensa en `//` y `%` como el resultado y el resto de una división de primaria.
---
# Orden de operaciones
Python respeta el orden matemático estándar: **PEMDAS**

```
Paréntesis → Exponentes → Multiplicación/División → Suma/Resta
```

```python
print(2 + 3 * 4)      # 14, no 20 (primero multiplica)
print((2 + 3) * 4)    # 20 (el paréntesis fuerza el orden)
print(2 ** 3 + 1)     # 9 (primero la potencia)
print(10 / 2 + 3)     # 8.0 (primero la división)
```

> Cuando tengas dudas, usa paréntesis. Hacen el código más claro y evitan errores.
---
# Operadores de asignación
En lugar de escribir `x = x + 1` puedes abreviarlo:

```python
x = 10

x += 3   # x = x + 3  → x vale 13
x -= 2   # x = x - 2  → x vale 11
x *= 2   # x = x * 2  → x vale 22
x /= 4   # x = x / 4  → x vale 5.5
x //= 2  # x = x // 2 → x vale 2.0
x **= 3  # x = x ** 3 → x vale 8.0
```

Los vas a usar mucho cuando trabajes con contadores o acumuladores más adelante.
---
# Funciones matemáticas útiles
Python trae algunas funciones matemáticas listas para usar sin importar nada:

```python
print(abs(-15))      # 15  → valor absoluto
print(round(3.7))    # 4   → redondea al entero más cercano
print(round(3.14159, 2))  # 3.14 → redondea a 2 decimales
print(max(4, 7, 2))  # 7   → el mayor de varios valores
print(min(4, 7, 2))  # 2   → el menor de varios valores
print(sum([1, 2, 3, 4]))  # 10 → suma una lista de números
```
---
# Operaciones entre distintos tipos
¿Qué pasa cuando operas un `int` con un `float`? Python decide el tipo del resultado
siguiendo una regla simple: **el resultado siempre adopta el tipo más "amplio".**

```python
a = 10      # int
b = 3.0     # float

resultado = a + b
print(resultado)        # 13.0  → float, no int
print(type(resultado))  # <class 'float'>
```

Python lo hace automáticamente para no perder información.

---

## La tabla de quién "gana"
| Operación | Resultado |
|---|---|
| `int` + `int` | `int` |
| `int` + `float` | `float` |
| `float` + `float` | `float` |
| cualquier cosa / cualquier cosa | siempre `float` |

La división `/` **siempre devuelve float**, aunque dividas dos enteros exactos:
```python
print(10 / 2)          # 5.0, no 5
print(type(10 / 2))    # <class 'float'>

# Si quieres un int, usa división entera
print(10 // 2)         # 5
print(type(10 // 2))   # <class 'int'>
```

---

## Diferencias con otros lenguajes
En C++ el tipo de una variable es fijo desde que la declaras y **nunca cambia**:

```cpp
// C++
int a = 10;
int b = 3;
int resultado = a / b;   // resultado = 3, no 3.333...
                         // C++ descarta los decimales sin avisar
```

Por eso es que es muy importante declarar bien las variables en otros lenguajes.

Python en cambio es más inteligente con esto:
```python
# Python
a = 10
b = 3
resultado = a / b
print(resultado)  # 3.3333... → Python preserva la información
```

> Python prioriza no perder datos sobre mantener el tipo original.
> En C++ tienes que ser tú quien lo maneje explícitamente, Python lo resuelve solo.

---

## Caso especial: bool en operaciones
En Python, `True` y `False` son internamente `1` y `0`:

```python
print(True + 1)    # 2
print(False + 5)   # 5
print(True * 10)   # 10

# Rarísimo pero válido, Python no te detiene
print(type(True + 1.0))  # <class 'float'>
```

No es algo que vayas a usar seguido, pero explica por qué `bool`
es técnicamente un subtipo de `int` en Python.

> `import` es la forma de traer herramientas extra a tu programa.
> Python tiene muchísimos módulos así, `math` es solo el primero que vas a usar.
---
# Resumen
| Operador | Operación | Ejemplo | Resultado |
|---|---|---|---|
| `+` `-` `*` `/` | Básicas | `10 / 3` | `3.333` |
| `//` | División entera | `10 // 3` | `3` |
| `%` | Módulo | `10 % 3` | `1` |
| `**` | Potencia | `2 ** 8` | `256` |
| `+=` `-=` etc. | Asignación compuesta | `x += 1` | `x = x + 1` |

**Siguiente módulo:** con variables, entradas y operaciones aritméticas solo te faltaría aplicar la lógica para poder construir programas más avanzados → Operadores lógicos.
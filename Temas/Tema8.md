# Instrucciones condicionales
---
# Índice
1. ¿Qué es una condición?
2. if / else
3. elif: múltiples condiciones
4. Operadores de comparación
5. Operadores lógicos
6. Condiciones anidadas
---
# ¿Qué es una condición?
Un programa no siempre hace lo mismo. A veces necesita tomar decisiones:
¿Está lloviendo?
SÍ → llevar paraguas
NO → dejar el paraguas en casa

En Python eso se traduce directamente a código.
Las condiciones evalúan si algo es `True` o `False` y ejecutan
distintas instrucciones según el resultado.

# if / else
La estructura básica:

```python
if condicion:
    # esto se ejecuta si la condición es True
else:
    # esto se ejecuta si la condición es False
```

Ejemplo real:
```python
edad = int(input("¿Cuántos años tienes? "))

if edad >= 18:
    print("Eres mayor de edad")
else:
    print("Eres menor de edad")
```

⚠️ **La indentación es obligatoria.** Python usa los espacios para saber
qué código pertenece a cada bloque. 4 espacios es el estándar.

```python
# Correcto
if edad >= 18:
    print("Mayor de edad")

# Error
if edad >= 18:
print("Mayor de edad")   # IndentationError
```
---
# elif: múltiples condiciones
Cuando hay más de dos posibilidades:

```python
nota = int(input("¿Cuál es tu nota? "))

if nota >= 90:
    print("Excelente")
elif nota >= 70:
    print("Aprobado")
elif nota >= 50:
    print("Regular")
else:
    print("Desaprobado")
```

Python evalúa de arriba a abajo y se detiene en la primera condición
que sea `True`. El `else` al final atrapa todo lo que no cumplió ninguna condición.

> Puedes tener todos los `elif` que necesites, pero solo un `if` y un `else` por bloque.
---
# Operadores de comparación
Son los que generan el `True` o `False` dentro de tus condiciones:

```python
x = 10

print(x == 10)   # True  → igual a
print(x != 5)    # True  → distinto de
print(x > 8)     # True  → mayor que
print(x < 8)     # False → menor que
print(x >= 10)   # True  → mayor o igual que
print(x <= 9)    # False → menor o igual que
```

⚠️ **Error clásico:** confundir `=` con `==`

```python
x = 10      # asignación: le das un valor a x
x == 10     # comparación: preguntas si x vale 10
```
---
# Operadores lógicos
Sirven para combinar condiciones:

```python
edad = 20
tiene_dni = True

# and → ambas condiciones deben ser True
if edad >= 18 and tiene_dni:
    print("Puede votar")

# or → al menos una condición debe ser True
if edad < 18 or not tiene_dni:
    print("No puede votar")

# not → invierte el resultado
if not tiene_dni:
    print("Le falta el DNI")
```

Tabla de verdad rápida:
| A | B | A and B | A or B |
|---|---|---|---|
| True | True | True | True |
| True | False | False | True |
| False | True | False | True |
| False | False | False | False |
---
# Condiciones anidadas
Puedes poner un `if` dentro de otro `if`:

```python
tiene_cuenta = True
saldo = 150

if tiene_cuenta:
    if saldo >= 100:
        print("Puede realizar la operación")
    else:
        print("Saldo insuficiente")
else:
    print("Primero debe crear una cuenta")
```

> Úsalas con cuidado. Si tienes más de 3 niveles de anidamiento,
> probablemente haya una forma más limpia de escribirlo.
---
# Resumen
| Instrucción | Para qué sirve |
|---|---|
| `if` | Ejecuta código si la condición es True |
| `else` | Ejecuta código si ninguna condición fue True |
| `elif` | Condición alternativa entre if y else |
| `and` | Ambas condiciones deben ser True |
| `or` | Al menos una condición debe ser True |
| `not` | Invierte el resultado de la condición |

**Siguiente paso:** ¿qué pasa si necesitas repetir algo muchas veces? → bucles.
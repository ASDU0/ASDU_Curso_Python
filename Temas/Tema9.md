# Bucles
---
# Índice
1. ¿Qué es un bucle?
2. El bucle while
3. El bucle for
4. range(): el mejor amigo del for
5. break y continue
6. else en bucles
---
# ¿Qué es un bucle?
Un bucle repite un bloque de código mientras se cumpla una condición
o por una cantidad determinada de veces.

Sin bucles:
```python
print("Cargando...")
print("Cargando...")
print("Cargando...")
# ¿Y si necesitas hacerlo 1000 veces?
```

Con bucles:
```python
for i in range(1000):
    print("Cargando...")
```

> Existen dos tipos: `while` (repite mientras algo sea True)
> y `for` (repite por cada elemento de algo).
---
# El bucle while
Repite mientras la condición sea verdadera:

```python
while condicion:
    # código que se repite
```

Ejemplo:
```python
intentos = 3

while intentos > 0:
    respuesta = input("¿Cuál es la contraseña? ")
    if respuesta == "python123":
        print("Acceso concedido")
        intentos = 0      # termina el bucle
    else:
        intentos -= 1
        print(f"Incorrecto. Te quedan {intentos} intentos")
```

⚠️ **Cuidado con el bucle infinito.** Si la condición nunca se vuelve
`False`, el programa nunca termina:

```python
# Bucle infinito
x = 1
while x > 0:
    print(x)
    # x nunca cambia → corre para siempre
```
---
# El bucle for
Recorre cada elemento de una secuencia:

```python
for elemento in secuencia:
    # código que usa cada elemento
```

Con una lista:
```python
frutas = ["manzana", "naranja", "uva"]

for fruta in frutas:
    print(fruta)
# manzana
# naranja
# uva
```

Con un string (también es una secuencia):
```python
for letra in "Python":
    print(letra)
# P
# y
# t
# h
# o
# n
```
---
# range():
`range()` genera una secuencia de números sin tener que escribirlos a mano:

```python
# range(fin) → de 0 hasta fin-1
for i in range(5):
    print(i)          # 0 1 2 3 4

# range(inicio, fin)
for i in range(2, 6):
    print(i)          # 2 3 4 5

# range(inicio, fin, paso)
for i in range(0, 10, 2):
    print(i)          # 0 2 4 6 8

# También funciona al revés
for i in range(5, 0, -1):
    print(i)          # 5 4 3 2 1
```

> `range()` no incluye el número final. `range(5)` llega hasta 4, no hasta 5.
> Es el error más común al empezar con bucles.
---
# break y continue
Controlan el flujo dentro del bucle:

**break** → sale del bucle inmediatamente:
```python
for numero in range(10):
    if numero == 5:
        break           # para cuando llega a 5
    print(numero)
# 0 1 2 3 4
```

**continue** → salta al siguiente ciclo sin ejecutar el resto:
```python
for numero in range(6):
    if numero == 3:
        continue        # se salta el 3
    print(numero)
# 0 1 2 4 5
```

Ejemplo útil: saltarse números pares:
```python
for i in range(10):
    if i % 2 == 0:
        continue
    print(i)    # 1 3 5 7 9
```
---
# else en bucles
Python permite un `else` al final de un bucle. Se ejecuta solo si el
bucle terminó sin un `break`:

```python
password = "python123"

for intento in range(3):
    entrada = input("Contraseña: ")
    if entrada == password:
        print("Acceso concedido")
        break
else:
    # solo llega aquí si los 3 intentos fallaron
    print("Demasiados intentos fallidos. Cuenta bloqueada.")
```

> Esto no existe en muchos otros lenguajes. Es una característica
> exclusiva de Python y muy útil para búsquedas y validaciones.
---
# Resumen
| Bucle | Cuándo usarlo |
|---|---|
| `while` | Cuando no sabes cuántas veces se repetirá |
| `for` | Cuando sabes exactamente cuántas veces o tienes una secuencia |
| `break` | Para salir del bucle antes de que termine |
| `continue` | Para saltarse una iteración específica |
| `else` | Para ejecutar algo solo si el bucle no fue interrumpido |

**Siguiente módulo:** con condicionales y bucles ya puedes construir
programas que toman decisiones y se repiten → funciones.
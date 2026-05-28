# Funciones y métodos
---
# Índice
1. ¿Qué es una función?
2. Definir y llamar una función
3. Parámetros y argumentos
4. Valores de retorno
5. Parámetros con valor por defecto
6. ¿Qué es un método?
7. Funciones vs Métodos
---
# ¿Qué es una función?
Hasta ahora todo tu código se ejecuta línea por línea, de arriba a abajo.
Pero ¿qué pasa si necesitas repetir el mismo bloque de código varias veces?

Sin funciones:
```python
print("Bienvenido, Hugo")
print("Tienes 3 intentos disponibles")
print("─" * 30)

print("Bienvenido, María")
print("Tienes 3 intentos disponibles")
print("─" * 30)
```

Con funciones:
```python
def bienvenida(nombre):
    print(f"Bienvenido, {nombre}")
    print("Tienes 3 intentos disponibles")
    print("─" * 30)

bienvenida("Hugo")
bienvenida("María")
```

Una función es un bloque de código con nombre que puedes reutilizar
todas las veces que necesites.

> Ya usaste funciones sin saberlo: `print()`, `input()`, `len()`, `round()`
> son todas funciones que Python trae incluidas.
---
# Definir y llamar una función
```python
# Definir → crear la función
def saludar():
    print("Hola, bienvenido al curso")
    print("Esto es una función")

# Llamar → ejecutarla
saludar()
saludar()   # puedes llamarla las veces que quieras
```

Reglas básicas:
- Siempre empieza con `def`
- El nombre sigue las mismas reglas que las variables (`snake_case`)
- Los dos puntos `:` al final son obligatorios
- El contenido va indentado (4 espacios)

⚠️ **Definir no es ejecutar.** Si solo escribes `def saludar()` pero
nunca la llamas, el código dentro nunca se ejecuta.

```python
def saludar():
    print("Hola")   # esto nunca se ejecuta si no llamas a saludar()
```
---
# Parámetros y argumentos
Los parámetros permiten que una función reciba datos para trabajar con ellos:

```python
# 'nombre' y 'edad' son parámetros
def presentar(nombre, edad):
    print(f"Me llamo {nombre} y tengo {edad} años")

# "Hugo" y 20 son argumentos (los valores reales que pasas)
presentar("Hugo", 20)
presentar("María", 22)
```

El orden importa:
```python
def restar(a, b):
    print(a - b)

restar(10, 3)   # 7  → a=10, b=3
restar(3, 10)   # -7 → a=3, b=10
```

También puedes pasar argumentos por nombre, y en ese caso
el orden no importa:
```python
restar(b=3, a=10)   # 7 → mismo resultado que restar(10, 3)
```
---
# Valores de retorno
Una función puede devolver un resultado usando `return`:

```python
def sumar(a, b):
    return a + b

resultado = sumar(5, 3)
print(resultado)   # 8
```

La diferencia entre `print` y `return`:
```python
def con_print(a, b):
    print(a + b)      # muestra el resultado pero no lo guarda

def con_return(a, b):
    return a + b      # devuelve el resultado para usarlo después

# con_print no se puede usar así:
total = con_print(5, 3)   # total = None, no el número
print(total)              # None

# con_return sí:
total = con_return(5, 3)  # total = 8
print(total * 2)          # 16 → puedes seguir operando con él
```

> Regla práctica: si necesitas usar el resultado más adelante, usa `return`.
> Si solo quieres mostrarlo, `print` dentro de la función puede bastar.

`return` también detiene la función inmediatamente:
```python
def dividir(a, b):
    if b == 0:
        return "Error: no se puede dividir entre cero"
    return a / b

print(dividir(10, 2))   # 5.0
print(dividir(10, 0))   # Error: no se puede dividir entre cero
```
---
# Parámetros con valor por defecto
Puedes definir un valor que se usa si no se pasa ese argumento:

```python
def saludar(nombre, mensaje="Bienvenido al curso"):
    print(f"Hola {nombre}, {mensaje}")

saludar("Hugo")                        # Hola Hugo, Bienvenido al curso
saludar("María", "qué bueno verte")   # Hola María, qué bueno verte
```

⚠️ Los parámetros con valor por defecto siempre van al final:
```python
# ✅ Correcto
def registrar(nombre, rol="estudiante"):
    pass

# ❌ Error
def registrar(rol="estudiante", nombre):
    pass
```
---
# ¿Qué es un método?
Un método es una función que pertenece a un tipo de dato específico.
Ya los usaste en los primeros temas sin que se llamaran así:

```python
texto = "hola mundo"

texto.upper()       # método de string → "HOLA MUNDO"
texto.replace("hola", "adiós")  # método de string → "adiós mundo"
texto.split()       # método de string → ["hola", "mundo"]
```

La diferencia en la sintaxis:
```python
# Función: el dato se pasa adentro
len(texto)
print(texto)

# Método: el dato va antes del punto
texto.upper()
texto.split()
```

Cada tipo de dato tiene sus propios métodos:
```python
# Métodos de string
"python".upper()          # "PYTHON"
"  hola  ".strip()        # "hola" → elimina espacios al inicio y final
"a,b,c".split(",")        # ["a", "b", "c"]
"hola".startswith("ho")   # True

# Métodos de números (a través de math o el tipo)
import math
math.sqrt(16)             # 4.0
math.ceil(3.2)            # 4
```
---
# Funciones vs Métodos

| | Función | Método |
|---|---|---|
| Sintaxis | `funcion(dato)` | `dato.metodo()` |
| Pertenece a | A nadie en particular | A un tipo de dato |
| Ejemplos | `len()`, `print()`, `round()` | `.upper()`, `.split()`, `.strip()` |

En la práctica vas a usar ambos todo el tiempo.
La distinción importa para entender por qué algunas cosas
se escriben diferente.

```python
# Las dos líneas hacen cosas con texto, pero se escriben distinto
print(len("hola"))        # función dentro de función
print("hola".upper())     # método sobre el dato
```
---
# Resumen
| Concepto | Para qué sirve |
|---|---|
| `def nombre():` | Define una función |
| Parámetros | Datos que la función recibe para trabajar |
| `return` | Devuelve un resultado para usarlo después |
| Valor por defecto | Parámetro opcional con valor preestablecido |
| Método | Función que pertenece a un tipo de dato |

**Siguiente paso:** organizar múltiples funciones relacionadas
en un mismo lugar → módulos y archivos.
# Variables y tipos de datos
---
# Índice
1. ¿Qué es una variable?
2. Reglas para nombrar variables
3. Las variables pueden cambiar
4. Tipos de datos en Python
5. Conversión entre tipos
6. Operaciones según el tipo
---
# ¿Qué es una variable?
Una variable es un espacio en memoria con nombre donde guardas un dato.

```python
nombre = "Hugo"   # Guardas el texto "Hugo" con el nombre 'nombre'
edad = 20         # Guardas el número 20 con el nombre 'edad'
```

Analogía: es como una caja etiquetada. La etiqueta es el nombre, el contenido es el valor.
```
┌─────────┐     ┌─────────┐
│  "Hugo" │     │   20    │
└─────────┘     └─────────┘
   nombre           edad
```
> En Python no necesitas declarar el tipo, él lo detecta solo. Pero cuidado, que al ingresar una variable mediante un input, esta sí se debería declarar en caso de que no sea un String.
---
# Reglas para nombrar variables
✅ Permitido:
```python
nombre = "Ana"
edad_usuario = 25
precio2 = 9.99
_temporal = True
```

❌ No permitido:
```python
2precio = 9.99      # No puede empezar con número
mi variable = "x"  # No puede tener espacios
class = "A"        # No puede ser una palabra reservada de Python
```

**Convención en Python:** usa `snake_case` → palabras separadas por guión bajo.
```python
#  Pythónico
nombre_completo = "Hugo Romero"

#  Evitar
NombreCompleto = "Hugo Romero"  # Eso es para clases, no variables
```
# Las variables pueden cambiar
Una variable puede recibir un nuevo valor en cualquier momento.
Cuando eso pasa, el valor anterior se pierde.

```python
puntos = 0
print(puntos)  # 0

puntos = 10
print(puntos)  # 10

puntos = 50
print(puntos)  # 50
```

Siguiendo la analogía de la caja: es como vaciarla y meter algo nuevo adentro.
```
Antes:          Después:
┌────────┐      ┌────────┐
│   0    │  →   │   10   │
└────────┘      └────────┘
puntos           puntos
```
También puedes actualizar una variable usando su propio valor:

```python
vidas = 3
print(vidas)   # 3

vidas = vidas - 1   # Le quitamos 1 a lo que ya tenía
print(vidas)   # 2
```

> Esto es muy común en juegos, contadores, puntajes, etc.
> Más adelante lo verás abreviado como `vidas -= 1`, que hace exactamente lo mismo.


---
# Tipos de datos en Python

```python
# int → números enteros
edad = 20
anio = 2025

# float → números decimales
precio = 9.99
temperatura = 36.5

# str → texto (string)
nombre = "Hugo"
mensaje = 'También funciona con comilla simple'

# bool → verdadero o falso
esta_lloviendo = False
es_mayor_de_edad = True
```

Para saber qué tipo tiene una variable:
```python
print(type(edad))      # <class 'int'>
print(type(precio))    # <class 'float'>
print(type(nombre))    # <class 'str'>
```
---
# Conversión entre tipos
A veces necesitas cambiar el tipo de un dato:

```python
# str → int
texto = "42"
numero = int(texto)      # 42

# int → float
entero = 5
decimal = float(entero)  # 5.0

# número → str (útil para concatenar)
edad = 20
mensaje = "Tengo " + str(edad) + " años"  # "Tengo 20 años"
```

⚠️ No toda conversión es posible:
```python
int("hola")   # Error: no puedes convertir texto a número
int("3.14")   # Error: tampoco funciona así
int(float("3.14"))  # Primero a float, luego a int → 3
```
---
# Operaciones según el tipo

**Con números:**
```python
a = 10
b = 3
print(a + b)   # 13  → suma
print(a - b)   # 7   → resta
print(a * b)   # 30  → multiplicación
print(a / b)   # 3.333... → división real
print(a // b)  # 3   → división entera
print(a % b)   # 1   → módulo (resto)
print(a ** b)  # 1000 → potencia
```

**Con strings:**
```python
nombre = "Hugo"
apellido = "Romero"
print(nombre + " " + apellido)  # Hugo Romero → concatenación
print(nombre * 3)               # HugoHugoHugo → repetición
print(len(nombre))              # 4 → longitud
```

**Con booleanos:**
```python
print(10 > 5)    # True
print(10 == 5)   # False
print(10 != 5)   # True
```



# Resumen
| Tipo | Ejemplo | Cuándo usarlo |
|---|---|---|
| `int` | `25` | Edades, cantidades, años |
| `float` | `3.14` | Precios, medidas, temperaturas |
| `str` | `"Hola"` | Nombres, mensajes, texto |
| `bool` | `True` | Estados, condiciones |

Una variable puede cambiar de valor en cualquier momento, pero cuidado con cambiarle el tipo sin querer.
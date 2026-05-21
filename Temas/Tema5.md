# Entradas y salidas de datos
# Índice
1. ¿Qué es una entrada y una salida?
2. Salida de datos: `print()`
3. Entrada de datos: `input()`
4. El problema del tipo de dato
5. Ejemplo
---
# ¿Qué es una entrada y una salida?
Todo programa hace básicamente esto:
> [ Usuario / Archivo / Sensor ] → ENTRADA → [ Programa ] → SALIDA → [ Pantalla / Archivo / Red ]

- **Entrada:** datos que el programa recibe para trabajar.
- **Salida:** el resultado que el programa entrega.

> Ejemplo real: Google Maps recibe tu ubicación (entrada) y te muestra la ruta (salida).
---
# Salida de datos: print()
Ya lo conoces, pero tiene más opciones de las que usaste:

```python
# Básico
print("Hola Mundo")

# Varias cosas a la vez
print("Nombre:", "Hugo")

# Cambiando el separador (por defecto es espacio)
print("2024", "11", "30", sep="/")  # 2024/11/30

# Sin salto de línea al final
print("Cargando", end="...")
print("listo")  # Cargando...listo

#Declarando variables y usándolas en la salida
nombre = "Juanín Juan Harry"
print("Hola, mi nombre es", nombre)    # Hola, mi nombre es Juanín Juan Harry
print(f"Hola, mi nombre es {nombre}")  # Hola, mi nombre es Juanín Juan Harry
#Ambas salidas serán iguales
```


---
# Entrada de datos: input()
`input()` pausa el programa y espera a que el usuario escriba algo.

```python
nombre = input("¿Cuál es tu nombre? ")
print("Hola,", nombre)
```

⚠️ **Lo que devuelve `input()` siempre es texto (string)**, sin excepción.

```python
dato = input("Escribe un número: ")
print(type(dato))  # <class 'str'> → es texto, no número
```
---
# El problema del tipo de dato
Si el usuario escribe `25` y quieres operar con ese número, necesitas convertirlo:

```python
edad = int(input("¿Cuántos años tienes? "))
precio = float(input("¿Cuánto cuesta? "))
```

| Función | Convierte a | Ejemplo |
|---|---|---|
| `int()` | Número entero | `int("25")` → `25` |
| `float()` | Número decimal | `float("3.14")` → `3.14` |
| `str()` | Texto | `str(100)` → `"100"` |

> Regla simple: Si vas a hacer matemáticas con el dato: Conviértelo. ¿Solo lo vas a mostrar? Déjalo como string.
---
# Ejemplo


## **Ejemplo — Saludo personalizado:**
Crea dos `input`, uno para pedir el nombre y el otro la ciudad del usuario, luego haz una salida que muestre el siguiente texto en consola: `"Hola [nombre], eres de [ciudad]"`

<details>
<summary> Clic aquí para ver el código python</summary>

```python
nombre = input("Tu nombre: ")
ciudad = input("Tu ciudad: ")
print(f"Hola {nombre}, eres de {ciudad}")
```
</details>


---

# Resumen
| | `print()` | `input()` |
|---|---|---|
| ¿Qué hace? | Muestra datos al usuario | Recibe datos del usuario |
| Dirección | Programa → Usuario | Usuario → Programa |
| Tipo que devuelve | — | Siempre string |

**Siguiente paso:** guardar esos datos en variables con nombre → siguiente tema.
# Primer programa: "Hola Mundo"

# Índice
1. ¿Por qué "Hola Mundo"?
2. Tu primer programa
3. ¿Qué hace cada parte?
4. Variaciones: DIY
5. Errores comunes
6. Extras
---
# ¿Por qué "Hola Mundo"?
Es la tradición de la programación desde 1972.
El objetivo no es el programa en sí, sino confirmar que:
- Tu entorno funciona 
- Sabes ejecutar código 
- La computadora responde a tus instrucciones 
> A partir de aquí, todo lo que construyas es tuyo.
---
# Tu primer programa
¡Felicidades! Llegaste al evento canónico de todo programador.
- Abre el IDLE de Python
- Ve al boton 'File' arriba a la izquierda y crea un nuevo archivo
- Guardalo como `hola.py` y escribe esto:
```python
print("Hola Mundo")
```

Dale a Run (o `F5` si prefieres). Eso es un programa completo y funcional.

# ¿Qué hace cada parte?
```python
print("Hola Mundo")
  │       └─ Lo que quieres mostrar 
  │          (texto entre comillas)
  └─ Función que muestra
     texto en pantalla
```
- `print()` es una **función**: una orden con nombre que hace algo concreto.
- El texto entre comillas se llama **string** (cadena de texto).
- Los paréntesis son obligatorios, ahí van los datos que le pasas a la función.
---
# Variaciones: DIY
No te quedes solo con "Hola Mundo". Prueba esto:
```python
print("Hola, soy [tu nombre]")
print("Estoy aprendiendo a programar")
print("Esto es la línea 3")
```
> Cada `print()` es una línea nueva en pantalla. Puedes usar tantos como quieras.


**PRÁCTICA**\
Ahora prueba con tu nombre e imprimir 3 cosas sobre ti:
- ¿Qué carrera estudias?
- ¿Cuál es tu pasatiempo favorito?
- ¿Qué edad tienes?

O agrega los datos que tú prefieras.

# Errores comunes


| Error | Causa | Solución |
|---|---|---|
| `SyntaxError` | Falta un paréntesis o comilla | Revisa que estén cerrados |
| `NameError` | Escribiste `Print` con mayúscula | Python distingue mayúsculas, es `print` |
| Nada en pantalla | No ejecutaste el archivo | Presiona ▶ o F5 |


---
# Resumen
Con `print()` le dices a Python qué mostrar en pantalla.
Es la función más simple, pero la vas a usar en practicamente todos tus programas.

**Siguiente paso:** hacer que el programa no solo hable, sino que también escuche → `input()`.

# Extras
Ahora veremos como se ejecuta un Hola Mundo en distintos lenguajes.
## Python
```Python
print('Hola Mundo')
```
## Java
```java
public class HolaMundo {
    public static void main(String[] args) {
        System.out.println("¡Hola, Mundo!");
    }
}   
```
## C
```c
    #include <stdio.h>

    int main() {
        printf("Hola Mundo\n");
        return 0;
    }
```

## C++
```cpp
    #include <iostream>

    int main() {
        std::cout << "Hola Mundo" << std::endl;
        return 0;
    }
```
## C#
```csharp
    using System;

    class Program {
        static void Main() {
            Console.WriteLine("Hola Mundo");
        }
    }
```
## Assembly
```assembly
section .data
    msg db "Hola Mundo", 10      ; El string a imprimir. El '10' es el salto de línea (\n)
    len equ $ - msg              ; Calcula automáticamente la longitud del texto

section .text
    global _start

_start:
    ; --- 1. Llamada al sistema para escribir (sys_write) ---
    mov rax, 1                  ; Código de sys_write en Linux x86_64
    mov rdi, 1                  ; File descriptor 1: salida estándar (pantalla)
    mov rsi, msg                ; Dirección de memoria donde empieza nuestro texto
    mov rdx, len                ; Cuántos bytes queremos imprimir
    syscall                     ; Ejecuta la llamada

    ; --- 2. Llamada al sistema para salir limpiamente (sys_exit) ---
    mov rax, 60                 ; Código de sys_exit
    mov rdi, 0                  ; Código de retorno (0 significa "todo bien")
    syscall                     ; Ejecuta la llamada
```
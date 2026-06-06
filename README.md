# Programación con Python
## CAPÍTULO 1: FUNDAMENTOS DE PYTHON

---

### Objetivos

- Comprender las principales características del entorno de trabajo de Python.
- Comprender las bases del lenguaje de programación.
- Ser capaz de realizar cálculos simples con Python.
- Ser capaz de crear y ejecutar scripts de Python.

---

### PYTHON

Python es un lenguaje de programación de propósito general, interpretado y de alto nivel, muy utilizado en cálculo científico, análisis de datos, automatización e inteligencia artificial. A diferencia de un sistema de álgebra simbólica como Maple o Mathematica, Python trabaja principalmente con valores numéricos, aunque su ecosistema de librerías permite cubrir prácticamente cualquier necesidad.

Una de sus mayores ventajas es la legibilidad: el código se parece al pseudocódigo, lo que facilita el aprendizaje. Para cálculo numérico con vectores y matrices se utiliza la librería **NumPy**, y para representar gráficas, **Matplotlib**. Con ellas, cualquier algoritmo que involucre matrices o vectores puede codificarse de forma sencilla, igual que en lenguajes orientados a arrays.

---

### El entorno de trabajo

Existen varias formas de trabajar con Python. Las más habituales para empezar son:

- **Intérprete interactivo (REPL):** se abre escribiendo `python` en la terminal. El prompt `>>>` indica que el programa está listo para recibir instrucciones.
- **Editor / IDE:** como VS Code, PyCharm o el editor de Spyder, donde se escriben los scripts `.py` y se ejecutan con un botón.
- **Cuadernos Jupyter:** permiten mezclar código, resultados y texto explicativo en celdas; muy usados en ciencia de datos.

Antes de empezar conviene crear una carpeta de trabajo donde guardar todos los archivos del proyecto, y abrir el editor o la terminal situados en esa carpeta.

> **Ejercicio 1:** Crea una carpeta llamada `Introduccion_Python` y ábrela en tu editor como directorio de trabajo.

Para salir del intérprete interactivo se escribe `exit()` o se pulsa `Ctrl+D` (en Windows, `Ctrl+Z` y Enter). Para detener un cálculo en ejecución se pulsa `Ctrl+C`.

---

### Operaciones básicas

Puedes usar Python como una calculadora. Por ejemplo, para calcular `1+3` escribe en el intérprete:

```python
>>> 1 + 3
4
```

Las operaciones matemáticas se realizan con la siguiente prioridad:

1. Potencias: `**`
2. Productos, divisiones y resto, de izquierda a derecha: `*`, `/`, `//`, `%`
3. Sumas y restas, de izquierda a derecha: `+`, `-`

Este orden se puede modificar con paréntesis.

**Ejemplo 1:**

```python
>>> 2 + 3 * 2
8
>>> (2 + 3) * 2
10
```

**Ejemplo 2:**

```python
>>> (2 / 3**2 * 5) * (3 - 4**3)**2
4134.444444444444
```

Observa que en Python `**` es la potencia (no `^`, que es el operador XOR), `/` es la división real, `//` la división entera y `%` el resto.

> **Ejercicio 2:** Realiza la siguiente operación usando los menos paréntesis posibles:
>
> $$(20 - 8)^3 \cdot \left(\frac{1 - 3}{5^2 - 1}\right)^2 + 2^3$$

En el intérprete, pulsa la flecha hacia arriba `↑` para recuperar instrucciones anteriores y modificarlas, igual que en una terminal normal.

> **Ejercicio 3:** Repite la operación anterior cambiando el 8 por un 13, reutilizando el comando previo con la flecha arriba.

Para controlar cuántos decimales se muestran puedes usar `round(x, n)` o el formateo de cadenas, por ejemplo `f"{x:.15f}"` para mostrar 15 decimales.

> **Ejercicio 4:** Muestra el resultado de los ejercicios anteriores con 15 cifras decimales.

---

### Asignación de variables

Hasta ahora hemos calculado números sin guardarlos. Podemos almacenar un valor en una variable para usarlo después. La instrucción básica es:

```python
variable = expresion
```

En Python no hace falta declarar el tipo de la variable: se infiere del valor asignado. A diferencia de otros entornos, escribir una expresión en un *script* no la muestra automáticamente; para ver un resultado se usa `print()`. En el intérprete interactivo, en cambio, el valor de la última expresión sí se imprime.

**Ejemplo 3:** Asignas un valor a una variable y lo reutilizas:

```python
>>> x = 3.4
>>> y = 2.7
>>> z = x + y
>>> z
6.1
```

Solo se guarda el valor calculado; por tanto, cambiar `x` después no cambia `z` (salvo que se recalcule):

```python
>>> x = 5.7
>>> z
6.1
```

**Ejemplo 4:** Prueba las siguientes operaciones:

```python
>>> mi_numero = 2.1
>>> mi_numero / 2
1.05
>>> res = mi_numero**2 - 1
```

Como nombre de variable puedes usar cualquier cadena alfanumérica que empiece por letra o guion bajo. Python distingue mayúsculas de minúsculas: `MiNumero` y `minumero` son variables distintas. Conviene evitar nombres de funciones ya existentes (como `sum`, `list` o `type`).

Para conocer las variables definidas en el intérprete puedes usar `dir()`, y para consultar el tipo de una, `type(variable)`. Para borrar una variable se usa `del variable`.

---

### Funciones incorporadas y el módulo `math`

Python incluye funciones integradas como `abs()`, `round()` o `len()`. Para funciones matemáticas más avanzadas se importa el módulo `math` de la librería estándar.

**Ejemplo 5:**

```python
import math

a = math.sqrt(4)     # 2.0
b = math.log(a)      # 0.6931471805599453
print(a, b)
```

Algunas funciones de uso frecuente del módulo `math`:

| Función | Descripción |
|---|---|
| `abs(x)` | valor absoluto (función incorporada, sin `math`) |
| `math.acos, asin, atan` | arco seno, coseno y tangente |
| `math.ceil(x)` | redondeo hacia el entero superior |
| `math.cos, sin, tan` | coseno, seno y tangente de un ángulo (en radianes) |
| `math.exp(x)` | exponencial |
| `math.floor(x)` | redondeo hacia el entero inferior |
| `math.gcd(a, b)` | máximo común divisor |
| `math.lcm(a, b)` | mínimo común múltiplo |
| `math.log, log2, log10` | logaritmo natural, en base 2 y en base 10 |
| `x % y` | resto de una división |
| `round(x)` | redondeo al entero más cercano |
| `math.sqrt(x)` | raíz cuadrada |
| `math.pi, math.e` | constantes π y e |

---

### Scripts

En lugar de escribir línea a línea en el intérprete, podemos guardar las instrucciones en un archivo `.py` y ejecutarlo. Crea un archivo nuevo en tu editor, escribe el código y guárdalo, por ejemplo, como `mi_suma.py` dentro de tu carpeta de trabajo.

**Ejemplo:** contenido de `mi_suma.py`

```python
a = 1
b = 2
print(a + b)
```

Hay varias formas de ejecutar el script:

- Desde la terminal, situándote en la carpeta y escribiendo `python mi_suma.py`.
- Desde el editor (VS Code, Spyder, PyCharm), pulsando el botón de ejecutar (Run).
- Seleccionando solo algunas líneas y ejecutándolas (en editores interactivos como Spyder o Jupyter).

---

### Entrada / salida

Para que un script sea interactivo, podemos pedir datos al usuario con `input()`, que siempre devuelve una cadena de texto. Para usarla como número hay que convertirla con `float()` o `int()`.

**Ejemplo 6:** La siguiente instrucción espera que el usuario escriba un número:

```python
x = float(input("Escribe un número: "))
```

**Ejemplo 7:** Los resultados se muestran con `print()`:

```python
>>> print(x)
```

**Ejemplo 8:** Puedes acompañar el valor con texto descriptivo. Con f-strings la conversión es automática:

```python
>>> print(f"El resultado es {x}")
```

**Ejemplo 9:** El script `volumen_cilindro.py` calcula el volumen de un cilindro a partir de dimensiones introducidas por teclado. Cópialo y ejecútalo.

```python
# Datos
import math
r = float(input("Radio:  "))
h = float(input("Altura: "))

# Cálculo
V = math.pi * r**2 * h

# Resultados
print(V)
print(f"El volumen es {V}")
```

Observa cómo se usan `input` y `print`. Las líneas que empiezan por `#` son comentarios: el intérprete las ignora. Comentar el código facilita entender qué hace cada parte.

> **Ejercicio 5:** Escribe un script que pida tres coeficientes a, b y c de una ecuación de segundo grado $ax^2 + bx + c = 0$, calcule el discriminante $\Delta = b^2 - 4ac$ y lo muestre con `print`. Úsalo con los polinomios $x^2+2x+1$, $x^2+x+1$ y $x^2-1$.

---

### Ejercicios adicionales

**A1.** Evalúa las siguientes operaciones en el intérprete. ¿Son necesarios todos los paréntesis? Recuerda usar las flechas para recuperar instrucciones anteriores:

$$(1 + 2^4)^2 \cdot \frac{7^3}{4^2 - 1}$$

$$(1 + \sqrt{2})^2 \cdot \frac{5^3}{4^2 - 1}$$

$$\left(1 + \operatorname{sen}\frac{2\pi}{3}\right)^2 + \frac{\sqrt{7}}{4^2 - 1}$$

**A2.** Busca la función de Python que genera valores aleatorios (módulo `random`) y escribe un script que pida un entero a y evalúe $\exp(a \cdot x)$ en un valor aleatorio x. Muestra el resultado con `print`.

---

### Referencias

- Documentación oficial de Python: <https://docs.python.org/es/3/>
- Tutorial oficial de Python: <https://docs.python.org/es/3/tutorial/>
- NumPy: <https://numpy.org/doc/> · Matplotlib: <https://matplotlib.org/stable/>

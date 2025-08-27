### Importacion de las bibliotecas
```python
import numpy as np
import pandas as pd
```

### NumPy – Creación y manipulación de arreglos
```python
#Crear arreglos
a = np.array([1, 2, 3, 4])
print(a)
```
Salida:
[1 2 3 4]

```python
b = np.array([[1, 2], [3, 4]])
print(b)
```
Salida:
[[1 2]
[3 4]]

```python
#reshape
c = np.arange(12).reshape(3, 4)
print(c)
```
Salida:
[[ 0  1  2  3]
 [ 4  5  6  7]
 [ 8  9 10 11]]

```python
#concatenate
d = np.concatenate([a, [5, 6, 7]])
print(d)
```
Salida:
[1 2 3 4 5 6 7]

```python
#Operaciones básicas
print("Suma:", a + 40)
print("Multiplicación:", a * 5)
print("Elemento a elemento:", a * np.array([10,50,100,150]))
```
Salida:
Suma: [41 42 43 44]
Multiplicación: [ 5 10 15 20]
Elemento a elemento: [ 10 100 300 600]

### NumPy – Operaciones estadísticas y funciones avanzadas
```python
array = np.random.randint(1, 100, size=10)
print("Array:", array)
```
Salida:
Array: [26 71 68  7 84 17 14 45 18 65]

```python
print("Media:", np.mean(array))
```
Salida:
Media: 41.5

```python
print("Desviación estándar:", np.std(array))
```
Salida:
Desviación estándar: 26.98610753702727

```python
print("Suma:", np.sum(array))
```
Salida:
Suma: 415

```python
#valores igualmente espaciados
print("arange:", np.arange(0, 10, 2))
print("linspace:", np.linspace(0, 1, 5))
```
Salida:
arange: [0 2 4 6 8]
linspace: [0.   0.25 0.5  0.75 1.  ]

```python
#aleatorio
print("Random:", np.random.rand(3,2))
```
Salida:
Random: [[0.44493135 0.94098532]
 [0.71137975 0.84216688]
 [0.6792999  0.02241597]]

```python
# algebra lineal
A = np.array([[1,2],[3,4]])
B = np.array([[5,6],[7,8]])
print("Producto punto:", np.dot(A,B))
print("Inversa:", np.linalg.inv(A))
```
Salida:
Producto punto: [[19 22]
 [43 50]]
Inversa: [[-2.   1. ]
 [ 1.5 -0.5]]

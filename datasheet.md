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

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
print("Primeros 3 elementos:", a[:3])
print("Elementos del 2 al 4:", a[1:4])
print("Últimos 2 elementos:", a[-2:])
```
Salida:
Suma: [41 42 43 44]
Multiplicación: [ 5 10 15 20]
Elemento a elemento: [ 10 100 300 600]
Primeros 3 elementos: [1 2 3]
Elementos del 2 al 4: [2 3 4]
Últimos 2 elementos: [3 4]

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

### Pandas – Creación y manipulación de DataFrames y Series
```python
# Series
s = pd.Series([10, 20, 30], index=["a", "b", "c"])
print(s)
```
salida:
a    10
b    20
c    30
dtype: int64

```python
# DataFrame
data = {"Nombre": ["Emily", "Carol", "María"],
        "Edad": [22, 20, 30],
        "Ciudad": ["Bogotá", "Chía", "Cali"]}
df = pd.DataFrame(data)
print(df)
```
salida:
Nombre  Edad  Ciudad
0  Emily    22  Bogotá
1  Carol    20    Chía
2  María    30    Cali

```python
# Seleccionar columnas
print(df["Nombre"])
```
salida:
0    Emily
1    Carol
2    María
Name: Nombre, dtype: object

```python
# Tipos de datos
print(df.dtypes)
```
Salida:
Nombre    object
Edad       int64
Ciudad    object
dtype: object

```python
# Primeras filas (head)
print(df.head(2))
```
salida:
Nombre  Edad  Ciudad
0  Emily    22  Bogotá
1  Carol    20    Chía

```python
# Cargar datos desde CSV
csv_df = pd.read_csv("/content/Personas - Página1.csv")
print(csv_df.head())
```
salida:
   Nome          Cidade        Estado      País          Curso  Idade
0      Luis            Chia  Cundinamarca  Colômbia  Administração     25
1     Mateo        Medellín  Cundinamarca  Colômbia       Medicina     29
2       Ana      São Carlos            SP    Brasil       Sistemas     23
3    Carlos  Belo Horizonte            MG    Brasil  Administração     35
4  Fernanda        Medellín  Cundinamarca  Colômbia       Sistemas     25

### Pandas – Operaciones avanzadas con DataFrames
```python
# Filtros
print(df[df["Edad"] > 22])
```
salida:
Nombre  Edad Ciudad
2  María    30   Cali

```python
# GroupBy
print(df.groupby("Ciudad")["Edad"].mean())
```
salida:
Ciudad
Bogotá    22.0
Cali      30.0
Chía      20.0
Name: Edad, dtype: float64

```python
# join
df_extra = pd.DataFrame({"Ciudad": ["Bogotá","Cali"],
                         "Poblacion": [8000000, 2200000]})
df_merged = pd.merge(df, df_extra, on="Ciudad", how="left")
print(df_merged)
```

salida:
 Nombre  Edad  Ciudad  Poblacion
0  Emily    22  Bogotá  8000000.0
1  Carol    20    Chía        NaN
2  María    30    Cali  2200000.0

```python
# Manejo de valores nulos
df_merged["Poblacion"] = df_merged["Poblacion"].fillna(0
```
```python
# Eliminar filas con valores nulos (dropna)
print(df_merged.dropna())
```
salida:
Nombre  Edad  Ciudad  Poblacion
0  Emily    22  Bogotá  8000000.0
2  María    30    Cali  2200000.0

```python
# Exportar / Importar
df.to_csv("output.csv", index=False)
```
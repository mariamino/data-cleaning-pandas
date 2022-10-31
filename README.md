![portada](https://github.com/mariamino/data-cleaning-pandas/blob/main/img/tiburon.jpg)

# Proyecto-Shark-Limpieza:

## Pautas del Proyecto

- Crear un repositorio nuevo
    - Src, img, data
    - Readme.md
- Issue (Con nuestro link pegado de nuestro repositorio)
- Limpieza:
    - Borrar columnas más de un 80% de nulos.
    - Resultado: al menos 6.000 filas
    - Mismo tipo de dato, duplicados, etc.
- Presentación.


## Observaciones

- Hay 3 columnas con la fecha (Y-M-D) del suceso:
    - 'Case Number','Case Number1', 'Case Number2'
- Hay 5 columnas relacionadas con fechas:
    - 'Case Number','Case Number1', 'Case Number2', 'Date', 'Year'
- 'Type' información:
    - Alguna información dificil de comprender
    - información 'Invalid' es como NaN?
    - 1 fila con Boatomg será igualada a Boating
    - Questionable será igualado a Invalid
- 'Name' información:
    - cuenta con nombres generales como 'male'
- 'Time' información:
    - hay que transformar el formato para que sea legible en hora
- 'Species' información:
    - hay que homogeneizar valores equivalentes
- 3 columnas relacionadas con el pdf:
    - revisar si es necesario contar con las columnas 'pdf', 'href formula', 'href'
- 'original order' información:
    - revisar si es necesaria la información aportada por la columna. Revisar si debe convertirse en el índice del df.
- columnas con más del 80% de nulos:
    - Unnamed: 22               99.996112
    - Unnamed: 23               99.992225
    - Time                      88.539439
    - Species                   86.533453
    - Age                       86.506240

- Hay muchas filas completamente vacias (todo unknown o 0)


## Transformaciones

### Columnas con un espacio en el nombre:
- Renombramos las columnas:
    - Sex
    - Species

### Filas Nulas:
- Eliminamos las 17020 filas formadas por todo nulos.

### Type de las columnas:
- Transformar a int: 'Age'
- Transformar a datetime: 'Date', 'Case Number.1', 'Case Number.2'

### Valores Nulos:
- Dataframe de columnas eliminadas por >80% de nulos: Unnamed: 22 y Unnamed: 23
- Columna Species: convertir los nulos de species en 'unknown'
- Columna Time: transformada en 'time'
- Columna Age: 'unknown'
- Columna Sex: 'unknown'
- Columna Originalorder: no aporta información de valor y 75% de valores nulos, eliminada.
- Resto de columnas tipo objeto con valores nulos: transformado a 'Unknown'
- Resto de columnas tipo float64 con valores nulos: transformado a '0'

### Columnas con valores no homogéneos
- Dejar lo más homogéneo posible las horas de 'time'
- Dejar lo más homogéneo posible las fechas de 'date'
- Dejar lo más homogéneo posible las especies de 'species'
- Dejar lo más homogéneo posible las entradas de 'type'

### Bajar el peso de la bbdd:
- Bajar el peso de las columnas con valor int al menor peso posible.




## Links & Fuentes

- <https://www.kaggle.com/teajay/global-shark-attacks>
- <https://numpy.org/doc/1.18/>
- <https://pandas.pydata.org/>
- https://docs.python.org/3/library/functions.html
- https://plotly.com/python/
- https://matplotlib.org/
- https://seaborn.pydata.org/
- https://pandas.pydata.org/docs/
- https://towardsdatascience.com/beware-of-storytelling-with-data-1710fea554b0?gi=537e0c10d89e


    
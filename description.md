### Listas por comprensión

Un recurso muy importante en python son las listas por comprensión, esta forma de estructura de datos permite realizar operaciones lógicas e iteracion y al mismo momento definir una lista.

La utilidad de la lista por comprensión viene dada por la claridad y por el hecho de que en una sola linea se puede agrupar código con mucha funcionalidad.

Ahora veamos una situación en donde, a partir de una lista de enteros, debamos sumar uno a cada elemento y devolver cada resultado en otra lista.

``` python
# definimos una lista
enteros = [1, 2, 3, 4, 5]

# inicializamos una lista vacía
enteros_mas_uno = []

# recorremos los elementos de la lista uno por uno
for elemento in lista:
    # sumo uno al elemento y ese resultado lo incluyo en la lista
    enteros_mas_uno.append( elemento + 1 )

print(enteros_mas_uno)
```
 _Salida:_
**>[2, 3, 4, 5, 6]**




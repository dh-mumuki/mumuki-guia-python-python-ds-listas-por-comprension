### Listas por comprensión

Un recurso muy importante en python son las listas por comprensión, esta forma de estructura de datos permite realizar operaciones lógicas e iteracion y al mismo momento definir una lista.

La utilidad de la lista por comprensión viene dada por la claridad y por el hecho de que en una sola linea se puede agrupar código con mucha funcionalidad.

Veamos la sintaxis de la lista por comprensión y comparemos como tendria que definirse sin este recurso

``` python
# definimos una lista
enteros = [1, 2, 3, 4, 5]

# inicializamos una lista vacía
enteros_mas_uno = []

# recorremos los elementos de la lista uno por uno
for elemento in lista:
    enteros_mas_uno.append(elemento)

print(enteros_mas_uno)
```




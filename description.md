### Listas por comprensión

Un recurso muy importante en python son las listas por comprensión, esta forma de estructura de datos permite realizar operaciones lógicas e iteracion y al mismo momento definir una lista.

La utilidad de la lista por comprensión viene dada por la claridad y por el hecho de que en una sola línea se puede agrupar código con mucha funcionalidad.

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


Esta sería una solución posible, en este caso realizamos un llamado al `for` para iterar sobre cada elemento de la lista, dentro de la iteración sumamos uno a cada elemento y lo incluimos en una lista que definimos *antes* de la entrada al `for`.

Vamos a proponer una solución nueva, utilizando esta vez, una lista por comprensión.

``` python
# definimos una lista
enteros = [1, 2, 3, 4, 5]

# definimos una lista por comprension
enteros_mas_uno = [ elemento+1  for  elemento  in  enteros ]

print(enteros_mas_uno)
```
 _Salida:_
**>[2, 3, 4, 5, 6]**

Vamos a explicar de forma ordenada como funciona la sintaxis:

  * elemento + 1 : es la operación que realizamos, esta es la expresión que va a formar parte de la lista final.
  * `for` : es el llamado al for y delimita la operación que queda dentro de la lista con el resto de la expresión
  * elemento: es el nombre que le asignamos durante cada iteración al elemento contenido en la lista **enteros** 


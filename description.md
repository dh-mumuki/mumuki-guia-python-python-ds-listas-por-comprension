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
enteros_mas_uno = [ numero+1  for  numero  in  enteros ]

print(enteros_mas_uno)
```
 _Salida:_
**>[2, 3, 4, 5, 6]**

Como podemos observar, esta lista por comprensión permite resumir muchas operaciones en un solo espacio

Vamos a explicar de forma ordenada como funciona la sintaxis:

  * **numero + 1** : es la operación que realizamos, esta es la expresión que va a formar parte de la lista final.
  * `for` : es el llamado al for y delimita la operación que queda dentro de la lista con el resto de la expresión
  * **numero**: es el nombre que le asignamos durante cada iteración al elemento contenido en la lista **enteros** (nosotros definimos ese nombre como "queramos") 
  * `in` : señala al iterable que vamos a recorrer (en este caso, la lista **enteros**)
  * **enteros**: el iterable, en este caso, una lista conteniendo una serie creciente de números naturales.

Veamos las generalidades de la sintaxis de la lista por comprensión:

``` python
[expresion for elemento in iterable]
```

Como vimos, hay tres actores principales dentro de este recurso, la **expresion** el **elemento** y el **iterable**, vamos a diferenciarlos:

   *  **expresión** : *numero + 1* : esta expresión queda dentro de la lista.
   *  **elemento**  : *numero*     : nombre que asignamos a cada valor dentro del iterable.
   *  **iterable**  : *enteros*    : estructura que recorremos.

Además es posible realizar operaciones lógicas que nos permiten filtrar el resultado de la expresion basándonos en algún criterio, para eso debemos realizar al final un llamado al `if`:

``` python
# definimos una lista
enteros = [1, 2, 3, 4, 5]

# definimos una lista por comprension
enteros_mas_uno = [ numero+1  for  numero  in  enteros if numero > 3 ]

print(enteros_mas_uno)
```
 _Salida:_
**>[5, 6]**

La diferencia con la lista por comprensión anterior es un llamado a `ìf` y un condicional posterior.

Integrando los nuevos recursos:
  
  * `if` : señala la expresión condicional que vamos a evaluar, si el resultado del condicional es `True` la expresión
  es incluida en la lista, si el resultado del condicional es `False` entonces la expresión no es incluida en la lista.
  *  **numero > 3**: es el condicional que va a ser evaluado, para cada valor del iterable asignado a numero, evalúa si la magnitud numérica es mayor a 3.

Como podemos observar, este condicional actua como filtro, dejando únicamente las expresiones para las que el valor número es mayor que 3, lo que es importante señalar, es que la expresión **numero + 1** no influye en si va a ser incluida o no en la lista, ya que eso se decide a nivel del condicional (después del `if`), otra aclaración es que la variable número, se define inmediatamente después del llamado al `for`.


Un recurso muy importante en Python son las **listas por comprensión**. Esta forma de estructura de datos permite realizar iteraciones, operaciones lógicas, operaciones sobre datos y, al mismo tiempo, definir una lista que contenga los resultados esperados.

La utilidad de las listas por comprensión viene dada por la economía de recursos de su sintaxis: ¡basta una sola línea de código para definirlas! A su vez, las listas por comprensión suelen ser muy eficientes en términos de recursos computacionales.

Ahora veamos una situación en donde, a partir de una lista de enteros, debemos sumar uno a cada elemento y devolver los resultados en otra lista:

``` python
# definimos una lista
enteros = [1, 2, 3, 4, 5]

# inicializamos una lista vacía
enteros_mas_uno = []

# recorremos los elementos de la lista uno por uno
for numero in enteros:
    # sumo uno al elemento y ese resultado lo incluyo en la lista enteros_mas_uno
    enteros_mas_uno.append(numero + 1)

print(enteros_mas_uno)

ム
> [2, 3, 4, 5, 6]
```

Ésta sería una solución posible. En este caso, realizamos un llamado al `for` para iterar sobre cada elemento de la lista, y en cada iteración sumamos uno a cada elemento y lo incluimos en una lista que definimos *antes* de la entrada al `for`.

Vamos a proponer una solución nueva, utilizando esta vez una lista por comprensión:

``` python
# definimos una lista
enteros = [1, 2, 3, 4, 5]

# definimos una lista por comprensión
enteros_mas_uno = [numero + 1 for numero in enteros]

print(enteros_mas_uno)

ム
> [2, 3, 4, 5, 6]
```
Como podemos observar, con una lista por comprensión llegamos al mismo resultado, con la diferencia de que resumimos todo a una única línea de código. Nada mal, ¿no? :wink:

Vamos a explicar de forma ordenada cómo funciona la sintaxis de las listas por comprensión:

  * **numero + 1** : es la operación que realizamos sobre cada elemento de la lista original que recorremos; los resultados van a formar parte de la lista final.
  * `for`: al igual que en los bucles que estudiamos anteriormente, el `for` da inicio a múltiples iteraciones.
  * **numero**: es el nombre de la variable a la que asignamos en cada iteración los elementos contenidos en la lista **enteros** (nosotros definimos el nombre de forma arbitraria).
  * `in` : señala al iterable que vamos a recorrer (en este caso, la lista **enteros**).
  * **enteros**: el iterable que recorremos (en este caso, una lista que contiene una serie creciente de números naturales).

De forma genérica, la sintaxis de las listas por comprensión es:

``` python
[**expresión** for **elemento** in **iterable**]
```

En el ejemplo anterior, la **expresion** equivale a **numero + 1**, el **elemento** resulta cada **numero** y el **iterable** que recorremos es la lista **enteros**.

Además, optativamente, también es posible establecer condiciones que nos permitan filtrar los elementos dentro del iterable. Para ello, naturalmente, debemos incluir un llamado al `if` luego de declarar al iterable:

``` python
# definimos una lista
enteros = [1, 2, 3, 4, 5]

# definimos una lista por comprensión
enteros_mas_uno = [numero + 1  for  numero  in  enteros if numero > 3]

print(enteros_mas_uno)

ム
> [5, 6]
```

Para que quede claro:
  
  * `if` : señala la expresión condicional que vamos a evaluar sobre los elementos del iterable que recorremos; si el resultado del condicional es `True`, la expresión es incluida en la lista resultante, mientras que si el resultado del condicional es `False`, entonces la expresión no es incluida.
  *  **numero > 3**: es el condicional que va a ser evaluado; para cada elemento asignado a **numero**, se evalúa si su valor es o no mayor a 3.

Como podemos observar, este condicional actúa como filtro, dejando únicamente las expresiones para las que el valor de **numero** es mayor a 3. Lo que es importante señalar es que la expresión **numero + 1** no influye en el resultado de la evaluación condicional.

Entonces, de forma más general, la sintaxis de las listas por comprensión resulta:

``` python
[**expresión** for **elemento** in **iterable** [if **condición]]
```

Donde los corchetes que encierran la sentencia `if` nos indican que su inclusión es opcional.
# Escítala

La escítala (skytale) es una de las herramientas de cifrado más antiguas conocidas, utilizada en la antigua Grecia alrededor del año 400 a. C. Era un dispositivo cilíndrico sencillo que los espartanos empleaban para enviar mensajes secretos durante las campañas militares.

Una tira de pergamino o cuero se enrollaba alrededor de una vara de madera (*skytale*) de cierto diámetro. Después, el mensaje se escribía a lo largo de la tira enrollada. Para descifrarlo, el receptor enrollaba la tira alrededor de una vara del mismo diámetro y leía el mensaje a lo largo, de la misma forma en que se había escrito.

Si quieres cifrar el mensaje:

```text
attackatdawn
```

y eliges una vara que permite **3 letras por vuelta**, la tira gira alrededor de ella 4 veces. Escribes el mensaje a lo largo de la vara, fila por fila, con 4 letras por fila (una en cada vuelta), formando una tabla:

```text
a t t a
c k a t
d a w n
```

El texto cifrado se obtiene leyendo columna por columna (este es el orden de las letras en la tira desenrollada):

```text
acdtkatawatn
```

Para descifrar el mensaje, el receptor enrolla la tira alrededor de una vara del mismo diámetro y vuelve a leer fila por fila para reconstruir el mensaje original.

## Primera tarea

Crea una aplicación de consola en cualquier lenguaje de programación para cifrar y descifrar mensajes mediante el cifrado de escítala.

El alfabeto permitido para los mensajes contiene solo letras minúsculas del alfabeto inglés:

```text
Σ = { a, b, c, d, e, f, g, h, i, j, k, l, m, n, o, p, q, r, s, t, u, v, w, x, y, z }
```

¡No se permiten espacios, letras mayúsculas, números ni otros caracteres!

En la primera línea de entrada hay un mensaje `m` de como máximo cien caracteres. En la segunda línea hay un entero `k` (el número de columnas de la tabla para el cifrado). En la tercera línea hay un entero `s` (1 para cifrar, 2 para descifrar).

### Ejemplo de prueba 1

Si la entrada es:

```text
attackatdawn
4
1
```

la salida debe ser:

```text
acdtkatawatn
```

### Ejemplo de prueba 2

Si la entrada es:

```text
acdtkatawatn
4
2
```

la salida debe ser:

```text
attackatdawn
```

## Sugerencias de solución

Para el **cifrado**, escribe el texto sin cifrar fila por fila en una tabla con `k` columnas. Lee la tabla columna por columna para obtener el texto cifrado.

Para el **descifrado**, escribe el texto cifrado columna por columna en una tabla con `k` columnas (cada columna contiene la longitud del mensaje dividida entre `k` letras) y luego lee la tabla fila por fila para reconstruir el texto sin cifrar.

## Ejercicios más complejos con la escítala (opcionales)

### Ampliar el alfabeto permitido

Incluye letras mayúsculas, espacios, números y signos de puntuación.

### Usar funciones

Crea las funciones `encrypt()` y `decrypt()` para modularizar el código.

### Crear una clase

Implementa una clase `SkytaleCipher` que almacene `k` y proporcione métodos para cifrar y descifrar.

### Cifrar y descifrar archivos

Modifica el programa para que lea el texto sin cifrar o cifrado de un archivo y escriba el resultado en otro archivo.

### Gestionar filas incompletas

Modifica el programa para que, si la última fila tiene menos de `k` caracteres, siga cifrando y descifrando correctamente y gestione las filas incompletas de forma adecuada.

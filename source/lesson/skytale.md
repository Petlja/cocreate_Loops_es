
# Escítala

La escítala (en inglés, skytale) es una de las herramientas de cifrado conocidas más antiguas. Procede de la antigua Grecia, alrededor del año 400 a. C. Era un dispositivo cilíndrico sencillo que los espartanos utilizaban para enviar mensajes secretos durante las campañas militares.

Una tira de pergamino o cuero se enrollaba alrededor de un palo de madera (*escítala*) de un diámetro determinado. A continuación, el mensaje se escribía a lo largo del palo. Cuando se desenrollaba la tira, las letras parecían mezcladas y no tenían sentido. El destinatario debía tener un palo del **mismo diámetro** para poder enrollar la tira y leer el mensaje original.

Si quieres cifrar el mensaje:

```text
attackatdawn
```


y eliges un palo que permita **4 letras por vuelta**, primero escribes el mensaje verticalmente en columnas, formando filas de longitud 4:

```text
a t t a
c k a t
d a w n
```


Después, el texto cifrado se obtiene leyendo por filas:

```text
acdtkatawatn
```


Para descifrar el mensaje, el destinatario vuelve a enrollar la tira alrededor de un palo del mismo diámetro y lee verticalmente para reconstruir el mensaje original.


## Primera tarea

Crea una aplicación de consola, en cualquier lenguaje de programación, que cifre y descifre mensajes utilizando el cifrado Escítala. Utiliza el entorno de desarrollo que empleáis en las clases de programación.

El alfabeto permitido para los mensajes contiene únicamente letras minúsculas del alfabeto inglés:

```text
Σ = { a, b, c, d, e, f, g, h, i, j, k, l, m, n, o, p, q, r, s, t, u, v, w, x, y, z }
```


¡No se permiten espacios, letras mayúsculas, números ni otros signos!


En la primera línea de entrada aparece el mensaje `m`, de como máximo cien caracteres. En la segunda línea aparece el número entero `k` (el número de columnas, es decir, la circunferencia del palo). En la tercera línea aparece el número entero `s`, que representa la operación. Si $s=1$, se debe cifrar `m`. Si $s=2$, se debe descifrar `m`.


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

## Consejos para la solución

Para **cifrar**, escribe el texto claro verticalmente en una tabla con `k` columnas. Lee la tabla por filas para obtener el texto cifrado. Para **descifrar**, escribe el texto cifrado por filas en una tabla con `k` columnas y, a continuación, lee la tabla verticalmente para reconstruir el texto claro.


## Tareas más complejas con el cifrado Escítala (opcional)

### Amplía el alfabeto permitido

Incluye letras mayúsculas, espacios, números y signos de puntuación.

### Utiliza funciones

Crea las funciones `encrypt()` y `decrypt()` para que el código sea modular.

### Crea una clase

Implementa una clase `SkytaleCipher` que almacene `k` y proporcione métodos para cifrar y descifrar.

### Cifra y descifra archivos

Modifica el programa para que lea texto claro o cifrado de un archivo y escriba el resultado en otro archivo.

### Procesa filas incompletas

Modifica el programa para que, si la última fila es más corta que `k`, siga cifrando y descifrando correctamente mediante el procesamiento de los caracteres que faltan o la adición de relleno.

# Escítala

La escítala (skytale) es una de las herramientas de cifrado más antiguas conocidas, utilizada en la antigua Grecia alrededor del año 400 a. C. Era un dispositivo cilíndrico sencillo que los espartanos empleaban para enviar mensajes secretos durante las campañas militares.

A strip of parchment or leather was wrapped around a wooden rod (*skytale*) of a certain diameter. The message was then written lengthwise across the wrapped strip. To decrypt, the receiver wrapped the strip around a rod of the same diameter and read the message lengthwise, the same way it was written.

Si quieres cifrar el mensaje:

```text
attackatdawn
```

and you choose a rod that allows **3 letters per wrap**, the strip goes around it 4 times. You write the message along the rod, row by row, 4 letters per row (one on each wrap), forming a table:

```text
a t t a
c k a t
d a w n
```

The encrypted text is then obtained by reading column by column (this is the order of the letters on the unwound strip):

```text
acdtkatawatn
```

To decrypt the message, the receiver wraps the strip around a rod of the same diameter and reads row by row again to reconstruct the original message.

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

For **encryption**, write the plaintext row by row in a table with `k` columns. Read the table column by column to get the ciphertext.

For **decryption**, write the ciphertext column by column into a table with `k` columns (each column holds the message length divided by `k` letters), then read the table row by row to reconstruct the plaintext.

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

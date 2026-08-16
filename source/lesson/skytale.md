# Escítala

Al completar esta lección, serás capaz de:

* Explicar cómo funciona el cifrado Escítala.
* Implementar el cifrado y descifrado usando operaciones simples con arrays o cadenas.
* Comprender cómo los dispositivos físicos de cifrado pueden modelarse digitalmente.

La Escítala es una de las herramientas de cifrado más antiguas conocidas, que se remonta a
la antigua Grecia alrededor del año 400 a. C. Era un sencillo dispositivo cilíndrico utilizado por los
espartanos para enviar mensajes secretos durante las campañas militares.

Una tira de pergamino o cuero se enrollaba alrededor de un bastón de madera (la *escítala*)
de un diámetro específico. El mensaje se escribía longitudinalmente a lo largo del bastón.
Una vez desenrolladas, las letras aparecían desordenadas y sin sentido. El destinatario
necesitaba un bastón del **exacto mismo diámetro** para enrollar la tira y leer el
mensaje original.

Si quieres cifrar el mensaje:

```text
attackatdawn
```

y eliges un bastón que permite **4 letras por vuelta**, primero escribes el
mensaje verticalmente en columnas, formando filas de longitud 4:

```text
a t t a
c k a t
d a w n
```

El texto cifrado se crea leyendo fila por fila:

```text
acdtkatawatn
```

Para descifrar, el receptor vuelve a enrollar la tira alrededor de un bastón del mismo diámetro
y lee verticalmente de nuevo para reconstruir el mensaje original.

## Tarea simple

Crea una aplicación de consola en cualquier lenguaje de programación para cifrar y descifrar
mensajes usando el cifrado Escítala.

El alfabeto permitido para los mensajes incluye solo las letras minúsculas del
alfabeto inglés:

```text
Σ = { a, b, c, d, e, f, g, h, i, j, k, l, m, n, o, p, q, r, s, t, u, v, w, x, y, z }
```

No se permiten espacios, letras mayúsculas, números ni otros caracteres.

En la primera línea de la entrada del usuario habrá un mensaje `m` de no más de
cien caracteres. En la segunda línea habrá un entero `k` (el
número de columnas – circunferencia del bastón). En la tercera línea habrá
un entero `s`, que representa la operación. Si $s=1$, entonces `m` debe
cifrarse. Si $s=2$, entonces `m` debe descifrarse.

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

## Comenzar la tarea

[Implement the cypher here ](https://arena.petlja.org/sr-Latn-RS/competition/123-co-create#tab_142946)

## Pistas para la solución

Para el **cifrado**, escribe el texto plano verticalmente en una tabla con `k`
columnas. Lee la tabla fila por fila para formar el texto cifrado. Para el **descifrado**,
escribe el texto cifrado fila por fila en una tabla con `k` columnas, lee la tabla
verticalmente para reconstruir el texto plano.

## Tareas avanzadas de Escítala (opcional)

### Ampliar el alfabeto permitido

Incluye letras mayúsculas, espacios, números y signos de puntuación.

### Usar funciones

Crea funciones `encrypt()` y `decrypt()` para mantener el código modular.

### Crear una Clase

Implementa una clase `SkytaleCipher` que almacene `k` y proporcione métodos para
el cifrado y descifrado.

### Cifrar y Descifrar Archivos

Modifica el programa para leer texto plano o cifrado desde un archivo y escribir
los resultados en otro archivo.

### Manejar filas incompletas

Modifica tu programa para que si la última fila es más corta que `k`, aún
cifre y descifre correctamente manejando los caracteres faltantes o el relleno.

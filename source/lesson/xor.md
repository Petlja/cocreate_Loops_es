
# XOR

XOR *(OR exclusivo)* es una operación lógica que devuelve verdadero (1) únicamente cuando las entradas son diferentes. Es una operación binaria fundamental con importantes aplicaciones en informática y criptografía.

| A | B | A XOR B |
| - | - | :-----: |
| 0 | 0 | 0       |
| 0 | 1 | 1       |
| 1 | 0 | 1       |
| 1 | 1 | 0       |

Por ejemplo, para cifrar la palabra «HELLO» utilizando la clave «KEY», primero debes convertir `HELLO` a formato binario...

| Carácter | ASCII | Binario  |
| ---- | ----- | -------- |
| H    | 72    | 01001000 |
| E    | 69    | 01000101 |
| L    | 76    | 01001100 |
| L    | 76    | 01001100 |
| O    | 79    | 01001111 |

...después convierte `KEY` a formato binario...

| Carácter | ASCII | Binario  |
| ---- | ----- | -------- |
| K    | 75    | 01001011 |
| E    | 69    | 01000101 |
| Y    | 89    | 01011001 |

...y finalmente realiza el cifrado: aplica XOR a cada carácter con la clave, repitiendo la clave tantas veces como sea necesario:

```text
H ⊕ K: 01001000 ⊕ 01001011 = 00000011 (ASCII 3)
E ⊕ E: 01000101 ⊕ 01000101 = 00000000 (ASCII 0)
L ⊕ Y: 01001100 ⊕ 01011001 = 00010101 (ASCII 21)
L ⊕ K: 01001100 ⊕ 01001011 = 00000111 (ASCII 7)
O ⊕ E: 01001111 ⊕ 01000101 = 00001010 (ASCII 10)
```

El texto cifrado obtenido está compuesto por caracteres ASCII no imprimibles con valores decimales 3, 0, 21, 7 y 10. Si un atacante interceptara este mensaje, solo vería datos binarios ilegibles, ya que los caracteres no son imprimibles.

Para descifrar el texto cifrado, debes aplicar XOR al texto cifrado utilizando la misma clave:

```text
3  ⊕ K: 00000011 ⊕ 01001011 = 01001000 (ASCII 72 → H)
0  ⊕ E: 00000000 ⊕ 01000101 = 01000101 (ASCII 69 → E)
21 ⊕ Y: 00010101 ⊕ 01011001 = 01001100 (ASCII 76 → L)
7  ⊕ K: 00000111 ⊕ 01001011 = 01001100 (ASCII 76 → L)
10 ⊕ E: 00001010 ⊕ 01000101 = 01001111 (ASCII 79 → O)
```

La operación XOR es involutiva: aplicar XOR dos veces con la misma clave devuelve los datos originales.

En la práctica, reutilizar la misma clave para varios mensajes hace que el cifrado XOR sea vulnerable al análisis de frecuencia y a los ataques de texto claro conocido. XOR por sí solo no ofrece una seguridad sólida a menos que la clave se gestione correctamente y tenga al menos la misma longitud que el mensaje, como en el caso de la libreta de un solo uso (one-time pad). Aun así, para fines educativos y demostraciones básicas de principios criptográficos, XOR es sencillo e ideal.

## Primera tarea

Crea una aplicación de consola, en cualquier lenguaje de programación, que cifre y descifre mensajes utilizando la operación XOR. Utiliza el entorno de desarrollo que empleáis en las clases de programación.

El alfabeto permitido para los mensajes (tanto para el texto claro como para la clave) contiene únicamente letras minúsculas del alfabeto inglés:

```text
Σ = { a, b, c, d, e, f, g, h, i, j, k, l, m, n, o, p, q, r, s, t, u, v, w, x, y, z }
```

No se permiten espacios, letras mayúsculas, números ni otros signos.

En la primera línea de entrada aparece el mensaje `m`, de como máximo cien caracteres ASCII si es texto claro o 800 bits si es texto cifrado; en la segunda línea, la clave `k`, de como máximo cinco caracteres; y en la tercera línea, el número entero `s`, que representa la operación. Si $s=1$, `m` es texto claro y debe cifrarse; si $s=2$, `m` es texto cifrado en formato binario y debe descifrarse.

### Ejemplo de prueba 1

Si la entrada es:

```text
nikolatesla
ser
1
```

la salida debe ser:

```text
0001110100001100000110010001110000001001000100110000011100000000000000010001111100000100
```

### Ejemplo de prueba 2

Si la entrada es:

```text
0001110100001100000110010001110000001001000100110000011100000000000000010001111100000100
ser
2
```

la salida debe ser:

```text
nikolatesla
```

## Realiza la tarea

[Implementa el cifrado aquí](https://arena.petlja.org/sr-Latn-RS/competition/123-co-create#tab_142947)

## Consejos para la solución

Cada carácter se almacena en la memoria como un valor ASCII de 8 bits (para las letras minúsculas a–z, los códigos van del 97 al 122). Para cifrar un carácter, toma su valor ASCII y el valor ASCII del carácter correspondiente de la clave (recorre la clave cíclicamente), aplica XOR (^) entre ambos y muestra el resultado como un número binario de 8 bits.

Para descifrar, sigue el procedimiento inverso: toma cada bloque binario de 8 bits del texto cifrado, conviértelo de nuevo en un número entero (0–255), aplícale XOR con el valor ASCII del carácter correspondiente de la clave y convierte el resultado en un carácter.

## Tareas más complejas con XOR (opcional)

### Amplía el alfabeto permitido

Permite letras minúsculas y mayúsculas, espacios, números y signos de puntuación. Aplica XOR a los caracteres que no sean letras con la clave de la misma manera.

## Utiliza funciones

Crea dos funciones: `encrypt()` para cifrar mensajes y `decrypt()` para descifrarlos. Utiliza las funciones creadas en el programa principal.

### Crea una clase

Crea una clase `XorCipher` que:

- almacene la clave,
- proporcione los métodos `encrypt()` y `decrypt()`,
- contenga opcionalmente un método auxiliar privado para repetir la clave a lo largo del mensaje.

Utiliza la clase creada en el programa principal.

### Acepta argumentos de la línea de comandos

En lugar de esperar la entrada del usuario, crea una aplicación de consola que acepte los siguientes argumentos de la línea de comandos:

1. el argumento `m` para el mensaje,
2. el argumento `k` para la clave, y
3. el argumento `s` para la operación (`1` para cifrar, `2` para descifrar).

### Cifra y descifra archivos

Utiliza los conocimientos adquiridos hasta ahora para crear un programa que pueda:

- leer texto claro o texto cifrado binario de un archivo,
- cifrarlo o descifrarlo con la clave indicada, y
- escribir el resultado en un archivo nuevo.

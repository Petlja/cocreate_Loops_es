# XOR

XOR *(OR exclusivo)* es una operación lógica que devuelve verdadero (1) solo cuando
las entradas son diferentes. Es una operación binaria fundamental con importantes aplicaciones
en informática y criptografía.

| A | B | A XOR B |
| - | - | :-----: |
| 0 | 0 | 0       |
| 0 | 1 | 1       |
| 1 | 0 | 1       |
| 1 | 1 | 0       |

Por ejemplo, para cifrar la palabra "HELLO" usando la clave "KEY", primero debes
convertir `HELLO` a binario...

| Char | ASCII | Binary   |
| ---- | ----- | -------- |
| H    | 72    | 01001000 |
| E    | 69    | 01000101 |
| L    | 76    | 01001100 |
| L    | 76    | 01001100 |
| O    | 79    | 01001111 |

...luego convertir `KEY` a binario...

| Char | ASCII | Binary   |
| ---- | ----- | -------- |
| K    | 75    | 01001011 |
| E    | 69    | 01000101 |
| Y    | 89    | 01011001 |

...y finalmente realizar el cifrado - aplicar XOR a cada carácter con la clave, repitiendo la
clave tantas veces como sea necesario:

```text
H ⊕ K: 01001000 ⊕ 01001011 = 00000011 (ASCII 3)
E ⊕ E: 01000101 ⊕ 01000101 = 00000000 (ASCII 0)
L ⊕ Y: 01001100 ⊕ 01011001 = 00010101 (ASCII 21)
L ⊕ K: 01001100 ⊕ 01001011 = 00000111 (ASCII 7)
O ⊕ E: 01001111 ⊕ 01000101 = 00001010 (ASCII 10)
```

El texto cifrado resultante consiste en caracteres ASCII no imprimibles con
valores decimales 3, 0, 21, 7 y 10. Si un atacante interceptara este mensaje,
vería solo datos binarios ilegibles, ya que los caracteres son
no imprimibles.

Para descifrar el texto cifrado debes aplicar XOR al texto cifrado con la misma clave:

```text
3  ⊕ K: 00000011 ⊕ 01001011 = 01001000 (ASCII 72 → H)
0  ⊕ E: 00000000 ⊕ 01000101 = 01000101 (ASCII 69 → E)
21 ⊕ Y: 00010101 ⊕ 01011001 = 01001100 (ASCII 76 → L)
7  ⊕ K: 00000111 ⊕ 01001011 = 01001100 (ASCII 76 → L)
10 ⊕ E: 00001010 ⊕ 01000101 = 01001111 (ASCII 79 → O)
```

La operación XOR es auto-inversa — aplicar XOR dos veces con la misma clave
restaurea los datos originales.

En aplicaciones del mundo real, reutilizar la misma clave para múltiples mensajes hace
que el cifrado XOR sea vulnerable al análisis de frecuencia y a los ataques de texto plano conocido.
El XOR por sí solo no proporciona una seguridad sólida a menos que la clave se gestione
correctamente y tenga al menos la misma longitud que el mensaje — como en un bloc de un solo uso. Sin embargo, para
fines educativos y demostraciones básicas de principios criptográficos, XOR
es simple e ideal.

## Tarea simple

Crea una aplicación de consola en cualquier lenguaje de programación para cifrar y descifrar
mensajes usando la operación XOR.

El alfabeto permitido para los mensajes (tanto texto plano como clave) incluye solo
letras minúsculas del inglés:

```text
Σ = { a, b, c, d, e, f, g, h, i, j, k, l, m, n, o, p, q, r, s, t, u, v, w, x, y, z }
```

No se permiten espacios, letras mayúsculas, números ni otros caracteres.

En la primera línea de la entrada del usuario habrá un mensaje `m` de no más de
cien caracteres ASCII para texto plano o 800 bits para texto cifrado, en la
segunda línea habrá una clave `k` de no más de cinco caracteres, y en la
tercera línea habrá un entero `s`, que representa la operación. Si
$s=1$ entonces `m` es texto plano y debe cifrarse, y si $s=2$, entonces `m` es
texto cifrado en binario y debe descifrarse.

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

## Comenzar la tarea

[Implement the cypher here ](https://arena.petlja.org/sr-Latn-RS/competition/123-co-create#tab_142947)

## Pistas para la solución

Cada carácter se almacena en memoria como un valor ASCII de 8 bits (para letras minúsculas
a–z, los códigos van del 97 al 122). Para cifrar un carácter, toma su
valor ASCII y el valor ASCII del carácter de clave correspondiente (ciclando
por la clave), aplica XOR (^) entre ellos y muestra el resultado como un número binario de 8 bits.

Para descifrar, sigue el proceso inverso: toma cada bloque binario de 8 bits del
texto cifrado, conviértelo de nuevo a un entero (0–255), aplica XOR con el valor ASCII del
carácter de clave correspondiente y convierte el resultado de nuevo a un carácter.

## Tareas avanzadas de XOR (opcional)

### Ampliar el alfabeto permitido

Permite letras minúsculas y mayúsculas, espacios, números y signos de puntuación.
Los caracteres que no son letras se someten a XOR con la clave de la misma manera.

## Usar funciones

Crea dos funciones: `encrypt()` para cifrar mensajes y `decrypt()` para
descifrar mensajes. Usa las funciones creadas en tu programa principal.

### Crear una Clase

Crea una clase `XorCipher` que:

* Almacene la clave,
* Proporcione métodos `encrypt()` y `decrypt()`,
* Opcionalmente incluya un método auxiliar privado para repetir la clave a lo largo de la longitud del mensaje.

Usa la clase creada en tu programa principal.

### Aceptar Argumentos de Línea de Comandos

En lugar de esperar la entrada del usuario, crea una aplicación de consola que
acepte los siguientes argumentos de línea de comandos:

1. argumento `m` para especificar el mensaje,
2. argumento `k` para especificar la clave, y
3. argumento `s` para especificar la operación (`1` para cifrar, `2` para descifrar).

### Cifrar y Descifrar Archivos

Usa el conocimiento adquirido hasta ahora para crear un programa que pueda:

* leer texto plano o texto cifrado en binario desde un archivo,
* cifrarlo o descifrarlo con una clave dada, y
* escribir el resultado en un nuevo archivo.

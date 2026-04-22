# Cifrado César

Uno de los grandes generales que usó mensajes cifrados fue Julio César, alrededor del año 50
a. C. Cuando César enviaba mensajes a sus generales, los cifraba desplazando
las letras del texto un número fijo de posiciones en el alfabeto. Los
destinatarios del mensaje podían descifrarlo porque conocían el valor del desplazamiento
— mientras que todos los demás veían solo texto sin sentido.

Por ejemplo, si escribieras `NIKOLATESLA` y desplazaras cada letra tres posiciones hacia
la derecha:

```text
A B C D E F G H I J K L M N O P Q R S T U V W X Y Z
X Y Z A B C D E F G H I J K L M N O P Q R S T U V W
```

La letra `N` se convierte en `K`, `I` se convierte en `F`, y así sucesivamente. Cada letra es
reemplazada por otra letra que está un número fijo de posiciones más adelante en
el alfabeto. Cuando se llega al final del alfabeto, la secuencia continúa
desde el principio. El resultado de la operación de desplazamiento de tres letras hacia la
derecha sería el mensaje cifrado `KFHLIXQBPIX`. Por otro lado, si cada
letra de la palabra resultante se desplazara tres letras hacia la izquierda:

```text
A B C D E F G H I J K L M N O P Q R S T U V W X Y Z
D E F G H I J K L M N O P Q R S T U V W X Y Z A B C
```

La letra `K` se convierte en `N`, `F` se convierte en `I`, y así sucesivamente. El resultado de la operación de desplazamiento
sería el mensaje descifrado original `NIKOLATESLA`.

![Caesar Cipher Left Shift](./images/caesar1.png)

## Tarea simple

Crea una aplicación de consola en cualquier lenguaje de programación para cifrar y descifrar
mensajes usando el cifrado César.

```{infonote}
El primer estudiante (*el conductor*) debe centrarse en la sintaxis mientras escribe el
código para el cifrado del mensaje. El segundo estudiante (*el navegador*) debe revisar
cada línea de código a medida que se escribe, buscando errores, haciendo preguntas
y sugiriendo mejoras. Después, los estudiantes deben cambiar de rol
y continuar escribiendo el código de descifrado.
```

El alfabeto permitido para los mensajes (tanto para texto plano como para texto cifrado) puede incluir
solamente letras minúsculas del alfabeto inglés:

```text
Σ = { a, b, c, d, e, f, g, h, i, j, k, l, m, n, o, p, q, r, s, t, u, v, w, x, y, z }
```

No se permiten espacios, letras mayúsculas, números ni otros caracteres.

En la primera línea de la entrada del usuario habrá un mensaje `m` de no más de
cien caracteres, en la segunda línea habrá un entero `n` que
representa el valor del desplazamiento ($1 \leq n < 26$), y en la tercera línea habrá
un entero `s`, que representa la dirección del cifrado. Si $s=1$ entonces `m`
debe cifrarse, y si $s=2$, entonces `m` debe descifrarse.

### Ejemplo de prueba 1

Si la entrada es:

```text
nikolatesla
3
1
```

la salida debe ser:

```text
kfhlixqbpix
```

### Ejemplo de prueba 2

Si la entrada es:

```text
kfhlixqbpix
3
2
```

la salida debe ser:

```text
nikolatesla
```

## Comenzar la tarea

[Implement the cypher here ](https://arena.petlja.org/sr-Latn-RS/competition/123-co-create#tab_142923)

## Pistas para la solución

Como hay 26 letras en el alfabeto inglés, la posición de cada letra
puede representarse con un número del 0 al 25.

* a → 0
* b → 1
* c → 2
* ...
* z → 25

Para **cifrar** una letra, puedes usar la siguiente fórmula:

```text
new_letter_position = (current_letter_position + shift_value) mod 26
```

`original_position` representa el valor numérico de la letra en el alfabeto,
`shift_value` representa el número de posiciones a mover (1–25), y `mod 26`
asegura que el resultado vuelva al inicio del alfabeto si supera
la `z`.

Para **descifrar** una letra, puedes usar la siguiente fórmula:

```text
new_letter_position = (current_letter_position - shift_value + 26) mod 26
```

De forma similar al cifrado, pero se resta el valor del desplazamiento, y `+ 26` asegura
que el valor no se vuelva negativo antes de aplicar `mod 26`.

## Tareas avanzadas del Cifrado César (opcional)

### Ampliar el alfabeto permitido

Crea una aplicación de consola en cualquier lenguaje de programación para cifrar y descifrar
mensajes usando el cifrado César. El alfabeto permitido para los mensajes (tanto para
texto plano como para texto cifrado) puede incluir letras minúsculas y mayúsculas del
alfabeto inglés, espacios, números y signos de puntuación.

La aplicación debe cifrar o descifrar solo letras minúsculas y mayúsculas.
Los espacios, números y signos de puntuación deben permanecer sin cambios durante
el cifrado o descifrado.

En la primera línea de la entrada estándar habrá un mensaje `m` de no más
de cien caracteres, en la segunda línea habrá un entero `n`
que representa el desplazamiento ($1 \leq n < 26$), y en la tercera línea habrá
un entero `s`, que representa la dirección del cifrado. Si $s=1$ entonces `m`
debe cifrarse, y si $s=2$, entonces `m` debe descifrarse.

## Usar funciones

Crea dos funciones: una para cifrar mensajes y otra para descifrar
mensajes. Usa las funciones creadas en tu programa principal.

## Crear una Clase

Crea una clase `CaesarCipher` que contenga:

* un constructor con un parámetro que acepte el valor del desplazamiento y garantice que
el valor esté dentro del rango permitido,
* una propiedad privada para almacenar el valor del desplazamiento, con métodos getter y setter,
* un método público para cifrar el mensaje,
* un método público para descifrar el mensaje, y
* opcionalmente, incluye un método privado para procesar mensajes, que será usado
tanto por los métodos de cifrado como de descifrado.

Usa la clase creada en tu programa principal.

## Aceptar Argumentos de Línea de Comandos

En lugar de esperar la entrada del usuario, crea una aplicación de consola que
acepte los siguientes argumentos de línea de comandos:

1. argumento `m` para especificar el mensaje,
2. argumento `n` para especificar el valor del desplazamiento (`0` a `25`), y
3. argumento `s` para especificar la dirección del desplazamiento (`1` para cifrado, y `2`
para descifrado).

## Cifrar y descifrar archivos

Usa el conocimiento adquirido hasta ahora para crear una aplicación de consola para
cifrar y descifrar archivos de texto. Tu aplicación debe aceptar los
siguientes argumentos de línea de comandos:

1. argumento `m` para especificar el nombre del archivo (o una ruta),
2. argumento `n` para especificar el valor del desplazamiento (`0` a `25`), y
3. argumento `s` para especificar la dirección del desplazamiento (`1` para cifrado, y `2`
para descifrado).

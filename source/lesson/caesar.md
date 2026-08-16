
# Cifrado César

Uno de los grandes generales que utilizó mensajes cifrados fue Julio César, alrededor del año 50 a. C. Cuando César enviaba mensajes a sus generales, los cifraba desplazando las letras del texto un número determinado de posiciones en el alfabeto. Los destinatarios podían descifrarlos porque conocían el valor del desplazamiento, mientras que todos los demás solo veían un texto sin sentido.

Por ejemplo, si escribes `NIKOLATESLA` y desplazas cada letra tres posiciones hacia la derecha:

```text
A B C D E F G H I J K L M N O P Q R S T U V W X Y Z
X Y Z A B C D E F G H I J K L M N O P Q R S T U V W
```


La letra `N` se convierte en `K`, `I` se convierte en `F`, y así sucesivamente. Por tanto, cada letra se sustituye por otra situada un número determinado de posiciones más adelante en el alfabeto. Cuando se llega al final del alfabeto, se continúa desde el principio. El resultado de desplazar tres letras hacia la derecha es el mensaje cifrado `KFHLIXQBPIX`. Por otro lado, si desplazas cada letra de la palabra obtenida tres posiciones hacia la izquierda:

```text
A B C D E F G H I J K L M N O P Q R S T U V W X Y Z
D E F G H I J K L M N O P Q R S T U V W X Y Z A B C
```


La letra `K` se convierte en `N`, `F` se convierte en `I`, y así sucesivamente. El resultado de este desplazamiento es el mensaje original descifrado `NIKOLATESLA`.

![Caesar Cipher Left Shift](./images/caesar1.png)


## Ejercicio de reflexión

Piensa en cómo crearías una aplicación de consola, en cualquier lenguaje de programación, que cifre y descifre mensajes utilizando el cifrado César. A continuación se ofrecen algunos consejos. Después de leerlos, intenta crear una aplicación de consola en el entorno de desarrollo que utilizáis en las clases de programación.


```{infonote}
El primer estudiante (*conductor*) debe centrarse en la sintaxis mientras escribe el código para cifrar el mensaje. El segundo estudiante (*navegador*) debe revisar cada línea de código mientras se escribe, buscar errores, hacer preguntas y proponer mejoras. Después, los estudiantes cambian de rol y continúan escribiendo el código para descifrar el mensaje.
```


El alfabeto permitido para los mensajes (tanto para el texto claro como para el texto cifrado) puede contener únicamente letras minúsculas del alfabeto inglés:

```text
Σ = { a, b, c, d, e, f, g, h, i, j, k, l, m, n, o, p, q, r, s, t, u, v, w, x, y, z }
```


No se permiten espacios, letras mayúsculas, números ni otros signos.


En la primera línea de entrada aparece el mensaje `m`, de como máximo cien caracteres; en la segunda línea, el número entero `n`, que representa el valor del desplazamiento ($1 \leq n < 26$); y en la tercera línea, el número entero `s`, que representa la dirección del cifrado. Si $s=1$, se debe cifrar `m`, y si $s=2`, se debe descifrar `m`.


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

## Consejos para la solución

Como el alfabeto inglés tiene 26 letras, la posición de cada letra puede representarse con un número del 0 al 25.

* a → 0
* b → 1
* c → 2
* ...
* z → 25


Para **cifrar** una letra, puedes utilizar la siguiente fórmula:

```text
new_letter_position = (current_letter_position + shift_value) mod 26
```


`original_position` representa el valor numérico de la letra en el alfabeto, `shift_value` representa el número de posiciones del desplazamiento (1–25), y `mod 26` garantiza que el resultado vuelva al principio del alfabeto si supera la letra `z`.


Para **descifrar** una letra, puedes utilizar la siguiente fórmula:

```text
new_letter_position = (current_letter_position - shift_value + 26) mod 26
```


El procedimiento es similar al cifrado, pero se resta el valor del desplazamiento, y `+ 26` garantiza que el valor no sea negativo antes de aplicar `mod 26`.


## Tareas más complejas con el cifrado César (opcional)

### Amplía el alfabeto permitido

Crea una aplicación de consola, en cualquier lenguaje de programación, que cifre y descifre mensajes utilizando el cifrado César. El alfabeto permitido para los mensajes (tanto para el texto claro como para el texto cifrado) puede contener letras minúsculas y mayúsculas del alfabeto inglés, espacios, números y signos de puntuación.

La aplicación debe cifrar o descifrar únicamente las letras minúsculas y mayúsculas. Los espacios, números y signos de puntuación deben permanecer sin cambios durante el cifrado o el descifrado.

En la primera línea de entrada aparece el mensaje `m`, de como máximo cien caracteres; en la segunda línea, el número entero `n`, que representa el valor del desplazamiento ($1 \leq n < 26$); y en la tercera línea, el número entero `s`, que representa la dirección del cifrado. Si $s=1$, se debe cifrar `m`, y si $s=2`, se debe descifrar `m`.


## Utiliza funciones

Crea dos funciones: una para cifrar mensajes y otra para descifrarlos. Utiliza las funciones creadas en el programa principal.

¡Aquí podéis trabajar por parejas: una persona debe cifrar el mensaje y la otra debe descifrarlo!


## Crea una clase

Crea una clase `CaesarCipher` que contenga:

- un constructor con un parámetro que acepte el valor del desplazamiento y garantice que está dentro del intervalo permitido,
- una propiedad privada para almacenar el valor del desplazamiento, con métodos getter y setter,
- un método público para cifrar mensajes,
- un método público para descifrar mensajes y
- opcionalmente, un método privado para procesar mensajes que utilicen ambos métodos.

Utiliza la clase creada en el programa principal.


## Acepta argumentos de la línea de comandos

En lugar de esperar la entrada del usuario, crea una aplicación de consola que acepte los siguientes argumentos de la línea de comandos:

1. el argumento `m` para el mensaje,
2. el argumento `n` para el valor del desplazamiento (`0` a `25`), y
3. el argumento `s` para la dirección del cifrado (`1` para cifrar, `2` para descifrar).


## Cifra y descifra archivos

Utiliza los conocimientos adquiridos hasta ahora para crear una aplicación de consola que cifre y descifre archivos de texto. Tu aplicación debe aceptar los siguientes argumentos de la línea de comandos:

1. el argumento `m` para el nombre del archivo (o la ruta),
2. el argumento `n` para el valor del desplazamiento (`0` a `25`), y
3. el argumento `s` para la dirección del cifrado (`1` para cifrar, `2` para descifrar).

# Cifrado César

Uno de los grandes comandantes militares que utilizó mensajes cifrados fue Julio César, alrededor del año 50 a. C. Usó un cifrado simple conocido como cifrado César para proteger las comunicaciones militares. Este cifrado también se conoce como cifrado por desplazamiento porque cada letra del texto sin cifrar se reemplaza por una letra situada a un número fijo de posiciones más arriba o más abajo en el alfabeto.

For example, if you write `NIKOLATESLA` and shift each letter three places to the left:

```text
A B C D E F G H I J K L M N O P Q R S T U V W X Y Z
X Y Z A B C D E F G H I J K L M N O P Q R S T U V W
```
![Caesar Cipher Left Shift](./images/caesar1.png)

La letra `N` se convierte en `K`, la `I` se convierte en `F`, y así sucesivamente. Por tanto, cada letra se reemplaza por otra letra que está a cierta distancia en el alfabeto.

**Decryption** works the same way, but in reverse. To decrypt the ciphertext, shift each letter back three places to the right:

```text
A B C D E F G H I J K L M N O P Q R S T U V W X Y Z
D E F G H I J K L M N O P Q R S T U V W X Y Z A B C
```

La letra `K` se convierte en `N`, la `F` se convierte en `I`, y así sucesivamente. El resultado de este desplazamiento es el mensaje descifrado original `NIKOLATESLA`.


## Tarea para reflexionar

Piensa en cómo crearías una aplicación de consola en cualquier lenguaje de programación que cifre y descifre mensajes mediante el cifrado César.

```{infonote}
El primer estudiante (*driver*) debe centrarse en la sintaxis mientras escribe el código para cifrar el mensaje. El segundo estudiante (*navigator*) debe observar el código, sugerir mejoras y hacer preguntas. Después de cifrar, cambiad los roles para descifrar.
```

El alfabeto permitido para los mensajes, tanto para el texto sin cifrar como para el texto cifrado, solo puede contener letras minúsculas del alfabeto inglés:

```text
Σ = { a, b, c, d, e, f, g, h, i, j, k, l, m, n, o, p, q, r, s, t, u, v, w, x, y, z }
```

No se permiten espacios, letras mayúsculas, números ni otros caracteres.

En la primera línea de entrada hay un mensaje `m` de como máximo cien caracteres; en la segunda línea hay un entero `n` que representa el valor del desplazamiento (1–25), y en la tercera línea hay un entero `s` que representa la dirección del cifrado. Si `s=1`, se debe cifrar `m`; si `s=2`, se debe descifrar.

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

## Sugerencias de solución

Dado que el alfabeto inglés tiene 26 letras, la posición de cada letra se puede representar mediante un número del 0 al 25.

* a → 0
* b → 1
* c → 2
* ...
* z → 25

Para **cifrar** una letra, puedes utilizar la siguiente fórmula:

```text
new_letter_position = (current_letter_position - shift_value + 26) mod 26
```

`current_letter_position` represents the numeric value of the letter in the alphabet, `shift_value` represents the number of positions to shift (1–25), `+ 26` ensures the value does not become negative, and `mod 26` ensures the value wraps around the alphabet.

Para **descifrar** una letra, puedes utilizar la siguiente fórmula:

```text
new_letter_position = (current_letter_position + shift_value) mod 26
```

Similarly to encryption, but the shift value is added, so the value cannot become negative and `+ 26` is not needed.

## Ejercicios más complejos sobre el cifrado César (opcionales)

### Ampliar el alfabeto permitido

Crea una aplicación de consola en cualquier lenguaje de programación que cifre y descifre mensajes mediante el cifrado César, pero con un alfabeto ampliado.

La aplicación debe cifrar o descifrar solo las letras minúsculas y mayúsculas. Los espacios, los números y los signos de puntuación deben permanecer sin cambios.

En la primera línea de entrada hay un mensaje `m` de como máximo cien caracteres; en la segunda línea hay un entero `n` (el valor del desplazamiento, de 1–25) y en la tercera línea hay un entero `s` (1 para cifrar, 2 para descifrar).

## Usa las funciones

Crea dos funciones: una para cifrar mensajes y otra para descifrarlos. Usa las funciones creadas en tu programa principal.

Aquí puedes trabajar en parejas: una persona debe cifrar el mensaje y la otra debe descifrarlo.

## Crear una clase

Crea una clase `CaesarCipher` que contenga:

- un constructor con un parámetro que acepta un valor de desplazamiento y garantiza que esté dentro del intervalo permitido (0–25),
- una propiedad privada para almacenar el valor de desplazamiento, con métodos getter y setter,
- un método público para cifrar un mensaje,
- un método público para descifrar un mensaje, y
- opcionalmente, un método privado para procesar mensajes que utilizan ambos métodos.

Usa la clase creada en el programa principal.

## Aceptar argumentos de la línea de comandos

En lugar de esperar a que el usuario introduzca datos, crea una aplicación de consola que acepte los siguientes argumentos de la línea de comandos:

1. el argumento `m` para el mensaje,
2. el argumento `n` para el valor del desplazamiento (`0` a `25`), y
3. el argumento `s` para la dirección de cifrado (`1` para cifrar, `2` para descifrar).

## Cifrar y descifrar archivos

Utiliza los conocimientos adquiridos hasta ahora para crear una aplicación de consola que cifre y descifre archivos de texto mediante el cifrado César.

La aplicación debe aceptar los siguientes argumentos de la línea de comandos:

1. el argumento `m` para el nombre del archivo (o la ruta),
2. el argumento `n` para el valor del desplazamiento (`0` a `25`), y
3. el argumento `s` para la dirección de cifrado (`1` para cifrar, `2` para descifrar).

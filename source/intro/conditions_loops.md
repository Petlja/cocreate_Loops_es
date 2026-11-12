# Condiciones y bucles

Para dominar con éxito el material sobre cifrado, es necesario que conozcas los hechos básicos sobre el trabajo con condiciones y bucles. Las condiciones y los bucles son los mecanismos principales que permiten a los programas informáticos tomar decisiones y repetir determinadas acciones. Gracias a las condiciones, un programa puede reaccionar de manera diferente según los datos que recibe, mientras que los bucles permiten repetir de manera eficiente los mismos pasos varias veces. Estos conceptos son de vital importancia en el cifrado, ya que los algoritmos de protección de datos se basan en una serie de reglas, comprobaciones y procedimientos repetitivos que garantizan la seguridad de la información.


## Condiciones

En la mayoría de los lenguajes de programación modernos, las instrucciones condicionales se utilizan para tomar decisiones y controlar el flujo del programa. Las construcciones más habituales son:

* if
* if-else
* switch-case

Aunque la sintaxis varía entre lenguajes, la lógica básica es la misma.

### Instrucción `if`

La instrucción `if` ejecuta un bloque de código solo si la condición dada se cumple (es cierta).

```text
if condition then
    statement(s)
```

Por ejemplo, en C, C++, C# y Java, si quieres comprobar si `x` es mayor que `0`, la instrucción condicional se puede escribir así:

```csharp
int x = 5;
if (x > 0) {
    // ...
}
```

### Instrucción `if-else`

La instrucción `if-else` ejecuta un bloque de código si la condición se cumple y otro bloque si no.

```text
if condition then
    statement(s)
else
    statement(s)
```

Por ejemplo, en C, C++, C# y Java, si quieres comprobar si `x` es mayor que `0` o no, la instrucción condicional se puede escribir así:

```csharp
int x = 5;
if (x > 0) {
    // ...
} else {
    // ...
}
```

### Instrucción `switch-case`

La instrucción `switch-case` es útil cuando una misma variable se compara con varios valores posibles. Esta construcción puede ser más clara que varias instrucciones `if-else`.

```text
switch expression do
    case value1:
        statement(s)
    case value2:
        statement(s)
    ...
    default:
        statement(s)
```

Por ejemplo, en C, C++, C# y Java, si quieres determinar el nombre del día a partir de su número de día de la semana, la instrucción condicional se puede escribir así:

```csharp
int day = 3;
string name = "";
switch (day) {
    case 1:
        name = "Monday";
        break;
    case 2:
        name = "Tuesday";
        break;
    case 3:
        name = "Wednesday";
        break;
    // ...
    default:
        name = "";
        break;
}
```

### Anidamiento de condiciones

Las instrucciones condicionales pueden estar colocadas una dentro de otra: esto se denomina **anidamiento**. Las condiciones anidadas son útiles cuando la decisión depende del resultado de una decisión anterior. Por ejemplo, quizá primero compruebes si el usuario está conectado y, después, dentro de ese bloque, compruebes si tiene permiso para ejecutar una determinada acción.

## Bucles

En la mayoría de los lenguajes de programación modernos, los bucles se llevan a cabo normalmente mediante alguna de estas construcciones:

* `for`,
* `while` (o `while-do`),
* `do-while` (o `repeat-until`),
* `foreach` (o `for-each`).

Aunque la sintaxis varía entre lenguajes, la lógica básica es la misma.

### Bucle `for`

La instrucción `for` se utiliza cuando el número de repeticiones es finito y conocido de antemano.

```text
for variable ← start to end do
    statement(s)
```

Por ejemplo, en C, C++, C# y Java, un bucle `for` para recorrer los números del 0 al 9 se puede escribir así:

```csharp
for (int i = 0; i <= 9; i++) {
    // ...
}
```

### Bucle `while`

La instrucción `while` (o `while-do`) se utiliza cuando el número de repeticiones no se conoce de antemano. La condición se comprueba antes de cada iteración, y por eso este bucle se denomina **bucle con condición previa**.

```text
while condition do
    statement(s)
```

Por ejemplo, en C, C++, C# y Java, un bucle `while` para recorrer los números del 0 al 9 se puede escribir así:

```csharp
int i = 0;
while (i <= 9) {
    // ...
    i++;
}
```

### Bucle `do-while`

La instrucción `do-while` (o `repeat-until`) también admite un número de repeticiones desconocido, pero la condición se comprueba después de cada iteración. Este es un **bucle con condición posterior** y siempre se ejecuta al menos una vez.

```text
repeat
    statement(s)
until condition
```

Por ejemplo, en C, C++, C# y Java, un bucle `do-while` para recorrer los números del 0 al 9 se puede escribir así:

```csharp
int i = 0;
do {
    // ...
    i++;
} while (i <= 9);
```

### Bucle `foreach`

La instrucción `foreach` (o `for-each`) se utiliza para recorrer todos los elementos de una colección o de un array. Este bucle simplifica la iteración cuando no te importa el índice.

```text
for-each element in collection do
    statement(s)
```

Por ejemplo, un bucle `for-each` para recorrer un array `nums` se puede escribir en C++ así:

```cpp
int nums[] = { 0, 1, 2, 3, 4, 5, 6, 7, 8, 9 };
for (int i : nums) {
    // ...
}
```

...o en C# así...

```csharp
int[] nums = { 0, 1, 2, 3, 4, 5, 6, 7, 8, 9 };
foreach (int i in nums) {
    // ...
}
```

...o en Java así:

```java
int[] nums = { 0, 1, 2, 3, 4, 5, 6, 7, 8, 9 };
for (int i : nums) {
    // ...
}
```

### Anidamiento de bucles

Los bucles también pueden estar anidados, es decir, un bucle puede estar dentro de otro. Esto ocurre a menudo cuando se trabaja con datos multidimensionales, como recorrer filas y columnas de una matriz o iterar sobre una cuadrícula en un juego. Además, los bucles y las condiciones se pueden combinar libremente: por ejemplo, un bucle puede contener una instrucción `if` para procesar solo algunos elementos, o una instrucción `if` puede contener un bucle para repetir acciones cuando se cumple la condición. Esta posibilidad de combinar y anidar bucles y condiciones permite crear algoritmos complejos manteniendo la lógica clara.


¡Diversos tipos de bucles serán necesarios para los diferentes tipos de cifrado que aprenderás en las próximas páginas!

# Condiciones y bucles

Para dominar con éxito el material sobre cifrado, es necesario que entiendas los conceptos básicos sobre cómo funcionan las condiciones y los bucles.

¡Vamos a recordar algunos conceptos fundamentales! Si aún te resulta confusa esta área, te recomendamos que revises la lección en Petlja.

El enlace a la lección de Petlja sobre bucles está [aquí](https://www.petlja.org/sr-Latn-RS/kurs/477/12/5844)
<!--Link za verzije kursa koje nisu na sprskokm https://petlja.org/en/biblioteka/r/lekcije/python-za-svakog/01_karel_eng_02_for -->

```{learnmorenote} Para maestros

Enlace a la lección de Petlja en serbio https://www.petlja.org/sr-Latn-RS/kurs/477/12/5844
Enlace para versiones del curso que no estén en serbio https://petlja.org/en/biblioteka/r/lekcije/python-za-svakog/01_karel_eng_02_for
```

## Condiciones

En la mayoría de los lenguajes de programación modernos, las sentencias condicionales se utilizan para tomar decisiones y controlar el flujo de un programa. Las más comunes incluyen:

* if
* if-else
* switch-case

Algo que debe notarse es que aunque la sintaxis difiere entre lenguajes, la lógica central es la misma.

### La sentencia `if`

La sentencia if ejecuta un bloque de código solo si la condición especificada es verdadera.

```text
if condition then
    statement(s)
```

Por ejemplo, en C, C++, C# y Java, si quieres comprobar si `x` es mayor que `0`, la sentencia condicional se puede escribir así:

```csharp
int x = 5;
if (x > 0) {
    // ...
}
```

### La sentencia `if-else`

La sentencia if-else ejecuta un bloque de código si la condición es verdadera, y otro bloque si es falsa.

```text
if condition then
    statement(s)
else
    statement(s)
```

Por ejemplo, en C, C++, C# y Java, si quieres comprobar si `x` es mayor que `0` o no, la sentencia condicional se puede escribir así:

```csharp
int x = 5;
if (x > 0) {
    // ...
} else {
    // ...
}
```

### La sentencia `switch-case`

La sentencia `switch-case` es útil cuando se compara la misma variable con muchos valores posibles. Puede ser más legible que usar múltiples sentencias `if-else`.

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

Por ejemplo, en C, C++, C# y Java, si quieres determinar el nombre del día basado en su número ordinal en la semana, la sentencia condicional se puede escribir así:

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

Las sentencias condicionales pueden colocarse dentro de otras sentencias condicionales; a esto se le llama **anidamiento**. Las condiciones anidadas son útiles cuando una decisión depende del resultado de una decisión anterior. Por ejemplo, primero podrías comprobar si un usuario ha iniciado sesión y, dentro de ese bloque, comprobar si tiene permiso para realizar una determinada acción.

## Bucles

En la mayoría de los lenguajes de programación modernos, los bucles se implementan habitualmente usando una de las siguientes construcciones:

* `for`,
* `while` (o `while-do`),
* `do-while` (o `repeat-until`),
* `foreach` (o `for-each`).

Algo que debe notarse es que aunque la sintaxis difiere entre lenguajes, la lógica central es la misma.

### El bucle `for`

El bucle `for` se utiliza cuando el número de iteraciones es finito y predeterminado.

```text
for variable ← start to end do
    statement(s)
```

Por ejemplo, en C, C++, C# y Java, un bucle `for` para iterar números del 0 al 9 se puede escribir así:

```csharp
for (int i = 0; i <= 9; i++) {
    // ...
}
```

### El bucle `while`

El bucle `while` (o `while-do`) se utiliza cuando el número de iteraciones no se conoce de antemano. La condición se verifica antes de cada iteración, por lo que se conoce como **bucle con precondición**.

```text
while condition do
    statement(s)
```

Por ejemplo, en C, C++, C# y Java, un bucle `while` para iterar números del 0 al 9 se puede escribir así:

```csharp
int i = 0;
while (i <= 9) {
    // ...
    i++;
}
```

### El bucle `do-while`

El bucle `do-while` (o `repeat-until`) también admite un número de iteraciones desconocido, pero la condición se verifica después de cada iteración, por lo que se conoce como **bucle con postcondición**.

```text
repeat
    statement(s)
until condition
```

Por ejemplo, en C, C++, C# y Java, un bucle `do-while` para iterar números del 0 al 9 se puede escribir así:

```csharp
int i = 0;
do {
    // ...
    i++;
} while (i <= 9);
```

### El bucle `foreach`

El bucle `foreach` (o `for-each`) se utiliza para iterar a través de todos los elementos en una colección o matriz. Este tipo de bucle simplifica el código y reduce la probabilidad de errores.

```text
for-each element in collection do
    statement(s)
```

Por ejemplo, un bucle `for-each` para iterar a través de una matriz `nums` se puede escribir en C++ como:

```cpp
int nums[] = { 0, 1, 2, 3, 4, 5, 6, 7, 8, 9 };
for (int i : nums) {
    // ...
}
```

...o en C# así:

```csharp
int[] nums = { 0, 1, 2, 3, 4, 5, 6, 7, 8, 9 };
foreach (int i in nums) {
    // ...
}  
```

...o en Java:

```java
int[] nums = { 0, 1, 2, 3, 4, 5, 6, 7, 8, 9 };
for (int i : nums) {
    // ...
}   
```

### Anidamiento de bucles

Los bucles también pueden estar anidados, lo que significa que un bucle está dentro de otro. Esto es común cuando se trabaja con matrices multidimensionales o cuando se necesita realizar comparaciones entre elementos.

Los diferentes tipos de bucles serán necesarios para diferentes formas de cifrado que aprenderás en las páginas siguientes.

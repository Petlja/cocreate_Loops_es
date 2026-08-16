# Condiciones y bucles

Para dominar con éxito el material sobre cifrado, es necesario conocer algunos conceptos básicos sobre el trabajo con condiciones y bucles. Las condiciones y los bucles son mecanismos fundamentales que permiten a los programas informáticos tomar decisiones y repetir determinadas acciones. Gracias a las condiciones, un programa puede reaccionar de forma diferente según los datos que reciba, mientras que los bucles permiten repetir los mismos pasos varias veces de manera eficiente. Estos conceptos son esenciales en el cifrado, ya que los algoritmos para proteger los datos se basan en una serie de reglas, comprobaciones y procedimientos repetitivos que garantizan la seguridad de la información.

¡Repasemos algunos conceptos básicos! Si este tema aún no te resulta claro, repasa la lección de Petlja dedicada específicamente a él.

El enlace a la lección de Petlja sobre bucles está [aquí](https://www.petlja.org/sr-Latn-RS/kurs/477/12/5844)
<!--Enlace a las versiones del curso que no están en serbio https://petlja.org/en/biblioteka/r/lekcije/python-za-svakog/01_karel_eng_02_for -->

```{learnmorenote} Para docentes

Enlace a la lección de Petlja en serbio https://www.petlja.org/sr-Latn-RS/kurs/477/12/5844
Enlace a las versiones del curso que no están en serbio https://petlja.org/en/biblioteka/r/lekcije/python-za-svakog/01_karel_eng_02_for
```

## Condiciones

En la mayoría de los lenguajes de programación modernos, las instrucciones condicionales se utilizan para tomar decisiones y controlar el flujo del programa. Las construcciones más habituales son:

* if
* if-else
* switch-case

Aunque la sintaxis varía entre lenguajes, la lógica básica es la misma.

### Instrucción `if`

La instrucción `if` ejecuta un bloque de código solo si se cumple la condición indicada (es verdadera).

```text
if condition then
    statement(s)
```

Por ejemplo, en C, C++, C# y Java, si quieres comprobar si `x` es mayor que `0`, la instrucción condicional puede escribirse así:

```csharp
int x = 5;
if (x > 0) {
    // ...
}
```

### Instrucción `if-else`

La instrucción `if-else` ejecuta un bloque de código si se cumple la condición y otro bloque si no se cumple.

```text
if condition then
    statement(s)
else
    statement(s)
```

Por ejemplo, en C, C++, C# y Java, si quieres comprobar si `x` es mayor que `0` o no, la instrucción condicional puede escribirse así:

```csharp
int x = 5;
if (x > 0) {
    // ...
} else {
    // ...
}
```

### Instrucción `switch-case`

La instrucción `switch-case` es útil cuando se compara una misma variable con varios valores posibles. Esta construcción puede ser más clara que varias instrucciones `if-else`.

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

Por ejemplo, en C, C++, C# y Java, si quieres determinar el nombre de un día a partir de su número de orden en la semana, la instrucción condicional puede escribirse así:

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

Las instrucciones condicionales pueden colocarse unas dentro de otras; esto se denomina **anidamiento**. Las condiciones anidadas son útiles cuando una decisión depende del resultado de una decisión anterior. Por ejemplo, primero puedes comprobar si el usuario ha iniciado sesión y después comprobar dentro de ese bloque si tiene permiso para realizar una determinada acción.

## Bucles

En la mayoría de los lenguajes de programación modernos, los bucles suelen implementarse mediante una de las siguientes construcciones:

* `for`,
* `while` (o `while-do`),
* `do-while` (o `repeat-until`),
* `foreach` (o `for-each`).

Aunque la sintaxis varía entre lenguajes, la lógica básica es la misma.

### Bucle `for`

El bucle `for` se utiliza cuando el número de repeticiones es finito y se conoce de antemano.

```text
for variable ← start to end do
    statement(s)
```

Por ejemplo, en C, C++, C# y Java, un bucle `for` para recorrer los números del 0 al 9 puede escribirse así:

```csharp
for (int i = 0; i <= 9; i++) {
    // ...
}
```

### Bucle `while`

El bucle `while` (o `while-do`) se utiliza cuando el número de repeticiones no se conoce de antemano. La condición se comprueba antes de cada iteración, por lo que este bucle se denomina **bucle con precondición**.

```text
while condition do
    statement(s)
```

Por ejemplo, en C, C++, C# y Java, un bucle `while` para recorrer los números del 0 al 9 puede escribirse así:

```csharp
int i = 0;
while (i <= 9) {
    // ...
    i++;
}
```

### Bucle `do-while`

El bucle `do-while` (o `repeat-until`) también admite un número de repeticiones desconocido, pero la condición se comprueba después de cada iteración. Es un **bucle con postcondición** y siempre se ejecuta al menos una vez.

```text
repeat
    statement(s)
until condition
```

Por ejemplo, en C, C++, C# y Java, un bucle `do-while` para recorrer los números del 0 al 9 puede escribirse así:

```csharp
int i = 0;
do {
    // ...
    i++;
} while (i <= 9);
```


### Bucle `foreach`

El bucle `foreach` (o `for-each`) se utiliza para recorrer todos los elementos de una colección o un array. Este bucle simplifica la iteración cuando el índice no es importante.

```text
for-each element in collection do
    statement(s)
```

Por ejemplo, un bucle `for-each` para recorrer el array `nums` puede escribirse en C++ así:

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

Los bucles también pueden anidarse, lo que significa que un bucle se encuentra dentro de otro. Esto es habitual cuando se trabaja con datos multidimensionales, como al recorrer las filas y columnas de una matriz o iterar por una cuadrícula en un juego. Además, los bucles y las condiciones pueden combinarse libremente; por ejemplo, un bucle puede contener una instrucción `if` para procesar solo determinados elementos, o una instrucción `if` puede contener un bucle para repetir acciones cuando se cumple la condición. Esta posibilidad de combinar y anidar bucles y condiciones permite crear algoritmos complejos manteniendo la lógica clara.


Se necesitarán diferentes formas de bucles para los distintos tipos de cifrado que aprenderás en las páginas siguientes.


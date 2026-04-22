# Condiciones y bucles

Para dominar con éxito el material de la siguiente lección, es necesario conocer
los conceptos básicos sobre el trabajo con condiciones y bucles.

## Condiciones

En la mayoría de los lenguajes de programación modernos, las sentencias condicionales se utilizan para tomar
decisiones y controlar el flujo de un programa. Las construcciones más comunes son:

* if
* if-else
* switch-case

Aunque la sintaxis difiere entre lenguajes, la lógica central es la misma.

### La sentencia `if`

La sentencia `if` ejecuta un bloque de código solo si una condición especificada es
verdadera.

```text
if condition then
    statement(s)
```

Por ejemplo, en C, C++, C# y Java, si se quiere comprobar si `x` es mayor que
`0`, la sentencia condicional se puede escribir así:

```csharp
int x = 5;
if (x > 0) {
    // ...
}
```

### La sentencia `if-else`

La sentencia if-else ejecuta un bloque de código si la condición es verdadera, y
otro bloque si es falsa.

```text
if condition then
    statement(s)
else
    statement(s)
```

Por ejemplo, en C, C++, C# y Java, si se quiere comprobar si `x` es mayor que
`0` o no mayor que `0`, la sentencia condicional se puede escribir así:

```csharp
int x = 5;
if (x > 0) {
    // ...
} else {
    // ...
}
```

### La sentencia `switch-case`

La sentencia `switch-case` es útil cuando se compara la misma variable con
muchos valores posibles. Puede ser más legible que usar múltiples sentencias
`if-else`.

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

Por ejemplo, en C, C++, C# y Java, si se quiere determinar el nombre del
día basándose en su número ordinal en la semana, la sentencia condicional se puede
escribir así:

```csharp
int day = 3;
string name = "";
switch (day) {
    case 1:
        name = "Lunes";
        break;
    case 2:
        name = "Martes";
        break;
    case 3:
        name = "Miércoles";
        break;
    // ...
    default:
        name = "";
        break;
}
```

### Anidamiento de condiciones

Las sentencias condicionales pueden colocarse dentro de otras sentencias condicionales; a esto
se le llama **anidamiento**. Las condiciones anidadas son útiles cuando una decisión depende del
resultado de una decisión anterior. Por ejemplo, primero se podría comprobar si un usuario
ha iniciado sesión y, dentro de ese bloque, comprobar si tiene permiso para
realizar una determinada acción.

## Bucles

En la mayoría de los lenguajes de programación modernos, los bucles se implementan habitualmente usando una
de las siguientes construcciones:

* `for`,
* `while` (or `while-do`),
* `do-while` (or `repeat-until`),
* `foreach` (or `for-each`).

Aunque la sintaxis difiere entre lenguajes, la lógica central es la misma.

### El bucle `for`

El bucle `for` se usa cuando el número de iteraciones es finito y
predeterminado.

```text
for variable ← start to end do
    statement(s)
```

Por ejemplo, en C, C++, C# y Java, un bucle `for` para iterar por los números
del 0 al 9 se puede escribir así:

```csharp
for (int i = 0; i <= 9; i++) {
    // ...
}
```

### El bucle `while`

El bucle `while` (o `while-do`) se usa cuando el número de iteraciones es
desconocido de antemano. La condición se verifica antes de cada iteración, por lo que
se denomina **bucle con precondición**.

```text
while condition do
    statement(s)
```

Por ejemplo, en C, C++, C# y Java, un bucle `while` para iterar por los números
del 0 al 9 se puede escribir así:

```csharp
int i = 0;
while (i <= 9) {
    // ...
    i++;
}
```

### El bucle `do-while`

El bucle `do-while` (o `repeat-until`) también admite un número desconocido de
iteraciones, pero la condición se verifica después de cada iteración. Se denomina
**bucle con postcondición** y siempre se ejecuta al menos una vez.

```text
repeat
    statement(s)
until condition
```

Por ejemplo, en C, C++, C# y Java, un bucle `do-while` para iterar por los
números del 0 al 9 se puede escribir así:

```csharp
int i = 0;
do {
    // ...
    i++;
} while (i <= 9);
```

### El bucle `foreach`

El bucle `foreach` (o `for-each`) se usa para iterar sobre todos los elementos de una
colección o array. Simplifica la iteración cuando no es necesario conocer el
índice.

```text
for-each element in collection do
    statement(s)
```

Por ejemplo, un bucle `for-each` para iterar por el array `nums` se puede escribir
en C++ así:

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

Los bucles también pueden anidarse, es decir, un bucle se coloca dentro de otro. Esto
es común cuando se trabaja con datos multidimensionales, como recorrer filas y
columnas en una matriz o iterar sobre una cuadrícula en un juego. Además, los bucles y
las condiciones pueden combinarse libremente — por ejemplo, un bucle puede contener una sentencia
`if` para procesar solo ciertos elementos, o una sentencia `if` puede contener un
bucle para realizar acciones repetidas cuando una condición es verdadera. Esta capacidad de mezclar
y anidar bucles y condiciones permite la creación de algoritmos complejos
manteniéndose la lógica subyacente estructurada.

# Condicions i bucles

Per dominar amb èxit el material sobre xifratge, cal que coneguis els fets bàsics sobre el treball amb condicions i bucles. Les condicions i els bucles són els mecanismes principals que permeten als programes informàtics prendre decisions i repetir determinades accions. Gràcies a les condicions, un programa pot reaccionar de manera diferent segons les dades que rep, mentre que els bucles permeten repetir de manera eficient els mateixos passos diverses vegades. Aquests conceptes són de vital importància en xifratge, ja que els algorismes de protecció de dades es basen en una sèrie de regles, comprovacions i procediments repetitius que garanteixen la seguretat de la informació.


## Condicions

A la majoria dels llenguatges de programació moderns, les instruccions condicionals es fan servir per prendre decisions i controlar el flux del programa. Les construccions més habituals són:

* if
* if-else
* switch-case

Tot i que la sintaxi varia entre llenguatges, la lògica bàsica és la mateixa.

### Instrucció `if`

L'instrucció `if` executa un bloc de codi només si la condició donada es compleix (és certa).

```text
if condition then
    statement(s)
```

Per exemple, en C, C++, C# i Java, si vols comprovar si `x` és més gran que `0`, la instrucció condicional es pot escriure així:

```csharp
int x = 5;
if (x > 0) {
    // ...
}
```

### Instrucció `if-else`

La instrucció `if-else` executa un bloc de codi si la condició es compleix i un altre bloc si no.

```text
if condition then
    statement(s)
else
    statement(s)
```

Per exemple, en C, C++, C# i Java, si vols comprovar si `x` és més gran que `0` o no, la instrucció condicional es pot escriure així:

```csharp
int x = 5;
if (x > 0) {
    // ...
} else {
    // ...
}
```

### Instrucció `switch-case`

L'instrucció `switch-case` és útil quan una mateixa variable es compara amb diverses possibles valors. Aquesta construcció pot ser més clara que diverses instruccions `if-else`.

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

Per exemple, en C, C++, C# i Java, si vols determinar el nom del dia a partir del seu número de dia de la setmana, la instrucció condicional es pot escriure així:

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

### Anidament de condicions

Les instruccions condicionals poden estar col·locades una dins de l'altra: això s'anomena **anidament**. Les condicions anidades són útils quan la decisió depèn del resultat d'una decisió anterior. Per exemple, potser primer comproves si l'usuari està connectat i, després, dins d'aquest bloc, comproves si té permís per executar una determinada acció.

## Bucles

A la majoria dels llenguatges de programació moderns, els bucles es duen a terme normalment mitjançant alguna d'aquestes construccions:

* `for`,
* `while` (o `while-do`),
* `do-while` (o `repeat-until`),
* `foreach` (o `for-each`).

Tot i que la sintaxi varia entre llenguatges, la lògica bàsica és la mateixa.

### Bucle `for`

La instrucció `for` es fa servir quan el nombre de repeticions és finit i conegut per endavant.

```text
for variable ← start to end do
    statement(s)
```

Per exemple, en C, C++, C# i Java, un bucle `for` per recórrer els nombres de 0 a 9 es pot escriure així:

```csharp
for (int i = 0; i <= 9; i++) {
    // ...
}
```

### Bucle `while`

La instrucció `while` (o `while-do`) es fa servir quan el nombre de repeticions no es coneix per endavant. La condició es comprova abans de cada iteració, i per això aquest bucle s'anomena **bucle amb condició prèvia**.

```text
while condition do
    statement(s)
```

Per exemple, en C, C++, C# i Java, un bucle `while` per recórrer els nombres de 0 a 9 es pot escriure així:

```csharp
int i = 0;
while (i <= 9) {
    // ...
    i++;
}
```

### Bucle `do-while`

La instrucció `do-while` (o `repeat-until`) també admet un nombre de repeticions desconegut, però la condició es comprova després de cada iteració. Aquest és un **bucle amb condició posterior** i sempre s'executa almenys una vegada.

```text
repeat
    statement(s)
until condition
```

Per exemple, en C, C++, C# i Java, un bucle `do-while` per recórrer els nombres de 0 a 9 es pot escriure així:

```csharp
int i = 0;
do {
    // ...
    i++;
} while (i <= 9);
```

### Bucle `foreach`

La instrucció `foreach` (o `for-each`) es fa servir per recórrer tots els elements d'una col·lecció o d'un array. Aquest bucle simplifica la iteració quan no et preocupa l'índex.

```text
for-each element in collection do
    statement(s)
```

Per exemple, un bucle `for-each` per recórrer un array `nums` es pot escriure en C++ així:

```cpp
int nums[] = { 0, 1, 2, 3, 4, 5, 6, 7, 8, 9 };
for (int i : nums) {
    // ...
}
```

...o en C# així...

```csharp
int[] nums = { 0, 1, 2, 3, 4, 5, 6, 7, 8, 9 };
foreach (int i in nums) {
    // ...
}
```

...o en Java així:

```java
int[] nums = { 0, 1, 2, 3, 4, 5, 6, 7, 8, 9 };
for (int i : nums) {
    // ...
}
```

### Anidament de bucles

Els bucles també poden estar anidats, és a dir, un bucle pot estar dins d'un altre. Això passa sovint quan es treballa amb dades multidimensionals, com recórrer files i columnes d'una matriu o iterar sobre una graella en un joc. A més, els bucles i les condicions es poden combinar lliurement: per exemple, un bucle pot contenir una instrucció `if` per processar només alguns elements, o una instrucció `if` pot contenir un bucle per repetir accions quan es compleix la condició. Aquesta possibilitat de combinar i anidar bucles i condicions permet crear algorismes complexos mantenint la lògica clara.


Diversos tipus de bucles seran necessaris per als diferents tipus de xifratge que aprendràs en les properes pàgines!

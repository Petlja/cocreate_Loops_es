
# XOR

XOR *(exclusiva O)* és una operació lògica que produeix veritat (1) només quan les entrades difereixen. És una operació binària fonamental utilitzada en criptografia.

| A | B | A XOR B |
| - | - | :-----: |
| 0 | 0 | 0       |
| 0 | 1 | 1       |
| 1 | 0 | 1       |
| 1 | 1 | 0       |

Per exemple, per xifrar la paraula "HELLO" utilitzant la clau "KEY", primer debes convertir `HELLO` a forma binària...

| Caràcter | ASCII | Binari   |
| -------- | ----- | -------- |
| H        | 72    | 01001000 |
| E        | 69    | 01000101 |
| L        | 76    | 01001100 |
| L        | 76    | 01001100 |
| O        | 79    | 01001111 |

...després converteix `KEY` a forma binària...

| Caràcter | ASCII | Binari   |
| -------- | ----- | -------- |
| K        | 75    | 01001011 |
| E        | 69    | 01000101 |
| Y        | 89    | 01011001 |

...i finalment realitza el xifratge – aplica XOR a cada caràcter amb la clau, repetint la clau tantes vegades com sigui necessari:

```text
H ⊕ K: 01001000 ⊕ 01001011 = 00000011 (ASCII 3)
E ⊕ E: 01000101 ⊕ 01000101 = 00000000 (ASCII 0)
L ⊕ Y: 01001100 ⊕ 01011001 = 00010101 (ASCII 21)
L ⊕ K: 01001100 ⊕ 01001011 = 00000111 (ASCII 7)
O ⊕ E: 01001111 ⊕ 01000101 = 00001010 (ASCII 10)
```

El text xifratge resultant consta de caràcters ASCII no imprimibles amb valors decimals 3, 0, 21, 7 i 10. Si necessites veure aquests valors com a nombres, pots mostrar-los com a la seva representació binària o hexadecimal.

Per desxifrar el text xifratge, debus aplicar XOR al text xifratge amb la mateixa clau:

```text
3  ⊕ K: 00000011 ⊕ 01001011 = 01001000 (ASCII 72 → H)
0  ⊕ E: 00000000 ⊕ 01000101 = 01000101 (ASCII 69 → E)
21 ⊕ Y: 00010101 ⊕ 01011001 = 01001100 (ASCII 76 → L)
7  ⊕ K: 00000111 ⊕ 01001011 = 01001100 (ASCII 76 → L)
10 ⊕ E: 00001010 ⊕ 01000101 = 01001111 (ASCII 79 → O)
```

L'operació XOR és autoinversa — aplicar XOR dues vegades amb la mateixa clau retorna les dades originals.

En la pràctica, reutilitzar la mateixa clau per a més d'un missatge fa que el xifratge XOR sigui vulnerable a l'anàlisi de freqüència i a altres atacs criptogràfics. Però és un concepte fonamental en criptografia moderna.

## Tasca simple

Crea una aplicació de consola en qualsevol llenguatge de programació per xifrar i desxifrar missatges utilitzant el xifratge XOR.

L'alfabet permès per als missatges (tant per al text pla com per a la clau) inclou només les lletres minúscules de l'alfabet anglès:

```text
Σ = { a, b, c, d, e, f, g, h, i, j, k, l, m, n, o, p, q, r, s, t, u, v, w, x, y, z }
```

No es permeten espais, lletres majúscules, nombres ni altres caràcters.

A la primera línia d'entrada hi haurà un missatge `m` de no més de cent caràcters ASCII per a text pla o 800 bits per a text xifratge. A la segona línia hi haurà una clau `k` de no més de cinc caràcters, i a la tercera línia hi haurà un enter `s`, que representa l'operació. Si $s=1$ aleshores `m` és text pla i ha de xifrarse, i si $s=2$, aleshores `m` és text xifratge en binari i ha de desxifrarse.

### Exemple de prova 1

Si l'entrada és:

```text
nikolateslaa
ser
1
```

la sortida ha de ser:

```text
0001110100001100000110010001110000001001000100110000011100000000000000010001111100000100
```

### Exemple de prova 2

Si l'entrada és:

```text
0001110100001100000110010001110000001001000100110000011100000000000000010001111100000100
ser
2
```

la sortida ha de ser:

```text
nikolateslaa
```


## Pistes per a la solució

Cada caràcter s'emmagatzema en memòria com a un valor ASCII de 8 bits (per a lletres minúscules
a–z, els codis van del 97 al 122). Per xifrar un caràcter, pren el seu
valor ASCII i el valor ASCII del caràcter de clau corresponent (ciclant
per la clau), aplica XOR (^) entre ells i mostra el resultat com a un nombre binari de 8 bits.

Per desxifrar, segueix el procés invers: pren cada bloc binari de 8 bits del
text xifratge, converteix-ho de nou a un enter (0–255), aplica XOR amb el valor ASCII del
caràcter de clau corresponent i converteix el resultat de nou a un caràcter.

## Tasques avançades de XOR (opcional)

### Ampliar l'alfabet permès

Permit lletres minúscules i majúscules, espais, nombres i signes de puntuació. Els caràcters que no són lletres se sotmeten a XOR amb la clau de la mateixa manera.

## Usar funcions

Crea dues funcions: `encrypt()` per xifrar missatges i `decrypt()` per desxifrar missatges. Usa les funcions creades en el teu programa principal.

### Crear una classe

Crea una classe `XorCipher` que:

- Emmagatzemi la clau,
- Proporcioni mètodes `encrypt()` i `decrypt()`,
- Opcionalment inclou un mètode auxiliar privat per repetir la clau al llarg de la longitud del missatge.

Usa la classe creada en el teu programa principal.

### Acceptar arguments de línia de comandaments

En lloc d'esperar l'entrada de l'usuari, crea una aplicació de consola que accepti els següents arguments de línia de comandaments:

1. argument `m` per especificar el missatge,
2. argument `k` per especificar la clau, i
3. argument `s` per especificar l'operació (`1` per xifrar, `2` per desxifrar).

### Xifrar i desxifrar fitxers

Utilitza el coneixement adquirit fins ara per crear un programa que pugui:

- Llegir text pla o binari xifratge d'un fitxer,
- Xifratge-lo o desxifratge-lo amb la clau donada, i
- Escriure el resultat en un fitxer nou.

# Una Breve Introducción a la Criptografía

Desde la antigüedad, cuando las personas comenzaron a escribir, ha existido la necesidad de mantener
algunos textos escritos en secreto. Al desarrollar técnicas para ocultar información registrada,
surgió un nuevo campo científico – la criptografía.

> **La criptografía** es una disciplina científica que se ocupa del desarrollo
> de sistemas para cifrar información. La palabra criptografía proviene de las
> palabras griegas kryptós (*oculto, secreto*) y graphein (*escribir*).

En India, escritos de hace 2000 años hablan de dos tipos de cifrado – el primer
tipo se basaba en la sustitución de letras según sus relaciones fonéticas,
y el segundo en un alfabeto codificado mediante el emparejamiento de letras y el uso
de letras recíprocas. En Persia, el actual Irán, también había dos tipos de
cifrado – el primer guion real se usaba para la correspondencia oficial dentro
del reino, y el segundo para la comunicación con otros estados.

El primer libro sobre criptografía, titulado “El Libro de los Mensajes Criptográficos”
según fuentes históricas, fue escrito por el filósofo árabe Al-Khalil
(717–786), en el que se utilizan por primera vez permutaciones y combinaciones
para enumerar todas las palabras árabes con y sin vocales. Sin embargo, los métodos de cifrado
clásicos a menudo revelan patrones estadísticos sobre el mensaje original, que pueden
aprovecharse para descifrar el código.

![Manuscrito de Kindi sobre el descifrado de mensajes criptográficos](./images/kindi.jpg)

Tras el descubrimiento del análisis de frecuencia de letras en un mensaje, el
matemático árabe Al-Kindi escribió el libro “Manuscrito para el Descifrado de
Mensajes Criptográficos” en el siglo IX, en el que se describió por primera vez
el uso de técnicas de análisis de frecuencia.

> **El criptoanálisis** es la disciplina científica que estudia métodos para
> “quebrar” sistemas criptográficos. La palabra criptoanálisis proviene de las palabras
> griegas kryptós (*oculto, secreto*) y analýein (*análisis*).

El primer tratado conocido sobre criptografía fue escrito en 25 páginas por el arquitecto italiano
Leone Battista Alberti en 1467. Él es también el creador del círculo cifrador
y otras soluciones para el ocultamiento de texto en doble capa. Medio siglo
después, se publicó la obra de Johannes Trithemus sobre criptografía en cinco volúmenes.
En el siglo XVI, realizaron contribuciones significativas el médico milanés
Girolamo Cardano, el matemático Battista Porta y el diplomático francés
Blaise de Vigenere.

![Máquina Cifrada Francesa en Forma de Libro del Siglo XVI](./images/cyphermachine.jpg)

En el siglo XIX, se llegó a la conclusión de que la criptografía no debía basarse en el
secreto de los algoritmos de cifrado, sino en el secreto de la clave. El
secreto de la propia clave debe ser suficiente para evitar que el mensaje cifrado
sea descifrado. Esto se convirtió en uno de los principios fundamentales de
la criptografía, escrito en 1883 por Auguste Kerckhoffs (Principio de Kerckhoffs).
De forma más explícita, fue reiterado por Claude Shannon, el fundador
de la Teoría de la Información y figura clave en la criptografía teórica, como
la Máxima de Shannon: "el enemigo conoce el sistema".

Durante la Segunda Guerra Mundial, los alemanes construyeron una máquina llamada Enigma que
cifraba mensajes de una forma nunca vista antes. Sin embargo, por revolucionaria que
fuera en su momento, los Aliados, liderados por Alan Turing, fueron capaces de descifrar el
sistema criptográfico Enigma mediante el criptoanálisis.

![Enigma](./images/enigma.jpg)

La criptografía y el criptoanálisis son las dos disciplinas principales de la criptología.

> **La criptología** es la ciencia que se ocupa de los distintos aspectos de la seguridad
> de la información. La palabra criptología proviene de las palabras griegas kryptós (*oculto,
> secreto*) y logos (*ciencia*).

## Presente

Tras la Segunda Guerra Mundial, con el desarrollo de la tecnología de la información, la criptología
y sus disciplinas científicas se volvieron cada vez más importantes. Los ordenadores modernos
pueden descifrar códigos simples a velocidades increíbles, por lo que los algoritmos criptográficos se han
vuelto mucho más avanzados. Hoy en día, la criptografía se divide generalmente en
cifrado **simétrico**, donde se usa la misma clave tanto para cifrar como para
descifrar...

![Cifrado simétrico](./images/symmetric.png)

...y cifrado **asimétrico**, donde se utiliza un par de claves pública y privada:

![Cifrado asimétrico](./images/asymmetric.png)

Otra herramienta esencial es la función hash criptográfica, que crea una
huella digital única de los datos y se usa ampliamente en la protección de contraseñas,
firmas digitales y tecnología blockchain.

## El Futuro

De cara al futuro, se espera que la criptografía cuántica se convierta en un pilar de
la comunicación segura. Se basa en el principio de incertidumbre de Heisenberg de
la física cuántica. Sin embargo, la computación cuántica también representa una amenaza para muchos
algoritmos criptográficos en uso hoy en día, lo que ha llevado al desarrollo de
la criptografía poscuántica.

![Google Quantum AI](./images/google.jpg)

La importancia de la criptología en la sociedad moderna no puede subestimarse.
Los sistemas criptográficos garantizan la privacidad de las comunicaciones electrónicas,
habilitan el comercio electrónico seguro, protegen las criptomonedas y en algunos países
incluso salvaguardan la votación electrónica y el recuento de votos.

# Introducción a Bitcoin
Table of contents:

1. TOC
{:toc}

## Introducción

Las dos principales contribuciones de la criptomoneda Bitcoin son:
  1. Un sistema de moneda digital que funciona continuamente.
  2. Un modelo para la tecnología autónoma de aplicaciones descentralizadas llamada blockchain.

Alrededor de 2008, 2009, cuando las instituciones y mercados en los que confiábamos se desmoronaron, y todo el mundo estaba huyendo de Wall Street, una persona misteriosa, o personas, llamada Satoshi Nakamoto, introdujo una nueva moneda digital, una criptomoneda llamada **Bitcoin**. 

| *Bitcoin habilitó una plataforma innovadora para la transferencia de valor entre pares sin ninguna autoridad central.* |

![](/My-Blockchain-Book/images/peer_to_peer.PNG "Transferencia de valor entre pares")

## Blockchain o Cadena de bloques

Pero... Sin una autoridad central, ¿cómo proporciona Bitcoin confianza y seguridad? Pues mediante la implementación de programas de software para validación, verificación y consenso en una infraestructura novedosa llamada **blockchain**. Más adelante, alrededor de 2012, 2013, se añadieron elementos de computación a la infraestructura de la blockchain que abrió todo un mundo de posibilidades más allá de la simple transferencia de divisas.  

| *Blockchain trata de habilitar transacciones peer to peer en una red descentralizada (transferencia de recursos digitales sin intermediarios) estableciendo la confianza entre pares o participantes desconocidos y registrando la transacción "en un libro digital" inmutable.* |

![](/My-Blockchain-Book/images/Intro-Blockchain.jpg "Cadena de bloques o Blockchain")

La cadena de bloques ha abarcado actualmente una amplia gama de aplicaciones en muchas industrias, incluyendo finanzas, salud, gobierno, fabricación y distribución.

## Que es una red descentralizada?

Consideremos un escenario en el que un cliente quiere comprar un artículo con su tarjeta de crédito. Los intermediarios que estarán involucrados en la realización de esta tarea serán:

- Agencia de tarjeta de créditos.
- Banco del cliente.
- Banco de tarjetas de crédito.
- Un intercambio.
- Banco del comerciante.
- El comerciante.

Este es un ejemplo de un **sistema centralizado** al que estamos tan acostumbrados. Ahora comparemos este con un sistema donde los participantes pueden realizar transacciones directamente entre ellos, independientemente de dónde se encuentren. Las funciones de los intermediarios del sistema centralizado se desplazan a la periferia al participante del mismo nivel en la infraestructura blockchain. Estos participantes o también llamados peers no son necesariamente conocidos entre sí. **Esto es un sistema descentralizado**.

![](/My-Blockchain-Book/images/Centralized-Decentralized.png "Sistema centralizado vs descentralizado")
[Pincha para leer más sobre sistemas centralizados y descentralizados](https://medium.com/hackernoon/centralization-vs-decentralization-the-best-and-worst-of-both-worlds-7bfdd628ad09)

Pero ¿cómo establecemos la confianza entre los participantes en un sistema tan descentralizado? Pues disponiendo de un proceso para validar, verificar y confirmar las transacciones. Para posteriormente registrar dicha transacción en un "libro mayor distribuido de bloques", crear un registro de bloques a prueba de manipulaciones (cadena de bloques) e implementar un protocolo de consenso para acordar el bloque que se va a agregar a dicha cadena.

| *Por lo tanto, la validación, la verificación, el consenso y la grabación inmutable conducen a la confianza y la seguridad de la cadena de bloques* |

Vamos a ver lo comentado a traves de un ejemplo: David le presta a Amy 10.000€ (esto es una única transacción punto a punto) y ambos lo anotan en sus libros mayores. Pero, David es deshonesto y cambia en su libro dicha entrada de 10.000€ a 11.000€. Amy hace lo mismo cambiando su entrada de 10.000 € a 1.000€. 

Para evitar esta violación de confianza, necesitamos buscar la ayuda de personas que nos rodean, por ejemplo, Lisa, Allison y Francis y le proporcionamos a todos ellos una copia válida de este libro mayor. Este es el concepto básico del **libro mayor distribuido inmutable** definido en un proceso blockchain. 

En este escenario, da la casulaidad que todos estamos físicamente presentes en un solo lugar. Ahora imaginemos que esto es una transacción online entre pares desconocidos. Además, en lugar de tener una única transacción tenemos 10.000 transacciones o tal vez un millón de transacciones. Deberíamos de ser capaz de realizar estas transacciones con la misma facilidad con cualquier otro participante desconocido en cualquier otro lugar. Este es el principio de un sistema descentralizado apoyado por blockchain.  

En el caso que acabamos de describir, ¿cómo confiamos en otros participantes desconocidos? A través de **la verificación y validación**. En nuestro ejemplo, Amy le pide a Kevin que verifique la cantidad que David acordó con ella. Kevin lo comprueba y encuentra que la cantidad de la transacción no es 10.000, sino 300, por lo tanto no es válida. Kevin rechaza y anula la transacción.

Similar a estos, la validación y los métodos de verificación ideados por la cadena de bloques e implementados por los pares proporcionan la confianza del colector necesaria en un sistema descentralizado.

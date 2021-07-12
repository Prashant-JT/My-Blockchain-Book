# Introducción a Bitcoin 🇪🇸
> Introducción a conceptos básicos de blockchain

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
| *Blockchain trata de habilitar transacciones peer to peer en una red descentralizada (transferencia de recursos digitales sin intermediarios) estableciendo la confianza entre pares desconocidos y registrando la transacción "en un libro digital" inmutable.* |

![](/My-Blockchain-Book/images/Intro-Blockchain.jpg "Cadena de bloques o Blockchain")
La cadena de bloques ha abarcado actualmente una amplia gama de aplicaciones en distintas industrias, incluyendo finanzas, salud, gobierno, fabricación y distribución.

### Que es una red descentralizada?

Consideremos un escenario en el que un cliente quiere comprar un artículo con su tarjeta de crédito. Los intermediarios que estarán involucrados en la realización de esta tarea serán:

- La agencia de tarjeta de créditos.
- El banco del cliente.
- Un banco de tarjetas de crédito.
- Un intercambio.
- El banco del comerciante.
- El comerciante.

Este es un ejemplo de un **sistema centralizado** al que estamos tan acostumbrados. Ahora comparemos este con un sistema donde los participantes pueden realizar transacciones directamente entre ellos, independientemente de dónde se encuentren. Las funciones de los intermediarios del sistema centralizado se desplazan a la periferia al participante del mismo nivel en la infraestructura blockchain. Estos participantes o también llamados peers no son necesariamente conocidos entre sí. **Esto es un sistema descentralizado**.

![](/My-Blockchain-Book/images/Centralized-Decentralized.png "Sistema centralizado vs descentralizado")
[Pincha para leer más sobre sistemas centralizados y descentralizados](https://medium.com/hackernoon/centralization-vs-decentralization-the-best-and-worst-of-both-worlds-7bfdd628ad09)

Pero ¿cómo establecemos la confianza entre los participantes en un sistema tan descentralizado? Pues disponiendo de un proceso para validar, verificar y confirmar las transacciones. Para posteriormente registrar dicha transacción en un "libro mayor distribuido de bloques", crear un registro de bloques a prueba de manipulaciones (cadena de bloques) e implementar un protocolo de consenso para acordar el bloque que se va a agregar a dicha cadena.

| *Por lo tanto, la validación, la verificación, el consenso y la grabación inmutable conducen a la confianza y la seguridad de la cadena de bloques* |

Vamos a ver lo comentado anteriormente a traves de un ejemplo: David le presta a Amy 10.000€ (esto es una única transacción punto a punto) y ambos lo anotan en sus respectivos libros mayores. Pero, David es deshonesto y cambia en su libro dicha entrada de 10.000€ a 11.000€. Amy hace lo mismo cambiando su entrada de 10.000 € a 1.000€. 

Para evitar esta violación de confianza, necesitamos buscar la ayuda de personas que nos rodean, por ejemplo, Lisa, Allison y Francis y le proporcionamos a todos ellos una copia válida de este libro mayor. Este es el concepto básico del **libro mayor distribuido inmutable** definido en un proceso blockchain. 

En este escenario, da la casualidad que todos estamos físicamente presentes en un solo lugar. Ahora imaginemos que esto es una transacción online entre pares desconocidos. Además, en lugar de tener una única transacción tenemos 10.000 transacciones o tal vez un millón de transacciones. Deberíamos de ser capaz de realizar estas transacciones con la misma facilidad con cualquier otro participante desconocido en cualquier otro lugar. Este es el principio de un sistema descentralizado apoyado por blockchain.  

En el caso que acabamos de describir, ¿cómo confiamos en otros participantes desconocidos? A través de **la verificación y validación**. En nuestro ejemplo, Amy le pide a Kevin que verifique la cantidad que David acordó con ella. Kevin lo comprueba y encuentra que la cantidad de la transacción no es 10.000, sino 300, por lo tanto la transacción no es válida. Kevin rechaza y anula dicha transacción.

Similar a estos, la validación y los métodos de verificación ideados por la cadena de bloques e implementados por los pares proporcionan la confianza del colector necesaria en un sistema descentralizado.

### Estructura de la blockchain

Una transacción es el elemento básico de la blockchain de bitcoin.
1. Las transacciones son validadas y difundidas.
2. Varias transacciones forman un bloque.
3. Muchos bloques forman una cadena a través de un enlace de datos digital.
4. Los bloques pasan por un proceso de consenso, para seleccionar cual será el siguiente bloque que se agregará a la cadena.
5. El bloque elegido se verifica y se agrega a la cadena actual.
6. El proceso de consenso y la validación son realizados por nodos especiales llamados mineros. Estos son potentes ordenadores ejecutando software definido por el protocolo de la blockchain. 

### Transacción en Bitcoin

Veamos ahora cuáles son detalles de una transacción en la blockchain de bitcoin.

#### UTXO

Un concepto fundamental de una red de bitcoin es una **Unspent Transaction Output (transacción de salida no gastada)**, también conocida como UTXO. El conjunto de todas las UTXOs en una red de bitcoin define colectivamente el estado de la cadena de bloques. 

![](/My-Blockchain-Book/images/UTXO.PNG "UTXOs se referencian tanto como entradas de una transacción y como salidas deneradas por esa transacción. Todas esas UTXOs en un sistema, son almacenados por los nodos participantes en una base de datos") 

[Picha aqui para leer más sobre UTXO (español)](https://academy.bit2me.com/que-es-una-utxo/)

Ahora revisemos el papel de las UTXOs en una blockchain de bitcoin: una **transacción** utiliza la cantidad especificada por una o más UTXOs de entrada y la transmite a una o más UTXOs de salida recién creadas, según la petición iniciada por el remitente. La estructura de una **UTXO** dada es la siguiente:
- Un identificador único de la transacción que creó este UTXO.
- Un índice o posición de la UTXO en la lista de UTXOs de salida de la transacción.
- Un valor o cantidad para la que es válida.
- Y un texto opcional que indica las condiciones bajo las cuales la salida puede ser gastada.

#### Transacción

Una transacción a su vez incluye:
- Un número de referencia de la transacción actual
- Referencias a una o más UTXOs de entrada
- Referencias a una o más UTXOs de salida recién generadas por la transacción actual, es decir, transacción de salida no gastada
- Cantidad total de entrada y salida

Veamos ahora un ejemplo de una transacción real

![](/My-Blockchain-Book/images/Transaction-Number.PNG "Identificador de la transacción") 

Vemos que justo abajo hay tres UTXOs de entrada a dicha transacción y una flecha que señala a las UTXOs de salida de la transacción

![](/My-Blockchain-Book/images/Input-UTXO.PNG "UTXOs de entrada") 
![](/My-Blockchain-Book/images/Output-UTXO.PNG "UTXOs de salida") 

Observa que hay tres UTXOs de entrada y solo dos de salida. Esto significa que la cantidad total de las tres UTXOs de entrada se emplean en generar dos nuevas UTXOs de salida. Justo debajo de las UTXOs de salida está la cantidad total transferida en valor de Bitcoin.

![](/My-Blockchain-Book/images/BTC-total-value.PNG "Cantidad total transferida en valor de Bitcoin") 

#### Bloque

Un bloque dispone de una cabecera con información sobre el bloque y un conjunto de transacciones válidas.

![](/My-Blockchain-Book/images/Block-header.PNG "Cabecera del bloque")

Este el llamado bloque génesis. Satoshi Nakamoto inició la blockchain de Bitcoin con una transacción de 50 BTC. Esta transacción creó mitad de las UTXOs de salida hacia su propia dirección. La fecha de la creación de este bloque génesis en la blockchain es el 3 de enero de 2009.

[Picha aqui para leer más sobre el bloque génesis (en español)](https://academy.bit2me.com/que-es-bloque-genesis/)

No había ningún bloque anterior ya que este es el primero de la cadena, por lo que el campo **Previous Block** esta a cero. También se lista una recompensa de bloque o unos honorarios de minero de 50 BTC. Hablaremos de la recompensa del minero en lecciones más adelante. 

![](/My-Blockchain-Book/images/Block-transaction.PNG "Conjunto de transacciones válidas en el bloque génesis")

Ahora, echemos un vistazo a la estructura de la Blockchain mirando en la blockchain de Bitcoin. Nuestro objetivo es entender la relación entre los bloques. Consideremos la cadena de tres bloques: #488868, #488867 y #488869.

![](/My-Blockchain-Book/images/Block-link.PNG "Bloques #488867, #488868 y #488869")

Vemos que el bloque #488868 que se muestra en el medio, tiene el hash del bloque #488867 como su hash anterior. Por otra lado, el bloque #488869 tiene el hash del #488868 como su hash anterior, formando de esta manera **los enlaces en la cadena**.

En resumen, una transacción genera la transferencia de valor en la blockchain de Bitcoin. El concepto de UTXO define las entradas y salidas de dichas transacciones. Una vez que un bloque es verificado y algorítmicamente acordado por los mineros, se agrega a la cadena de bloques, es decir, a la blockchain.

## Operaciones básicas en Blockchain

Las operaciones en una red descentralizada son responsabilidad de los participantes (peers) y de sus respectivos nodos computacionales, estos últimos pueden ser: portátil, ordenador o bastidores de servidores. Estas operaciones incluyen:
- Validación de las transacciones
- Agrupar las transacciones en un bloque
- Publicar bloques y transacciones válidas
- Llegar a un consenso para la creación del siguiente bloque de la cadena
- Encadenar bloques para crear un registro inmutable

### Participantes

Podemos distinguir entre dos tipos de participantes:
- Aquellos que inician la transferencia de valor creando una transacción
- **Miners**: son aquellos que deciden realizar un "trabajos o cálculos" extra para verificar las transacciones y emitir transacciones. Además compiten con otros mineros para poder crear un bloque, trabajan por conseguir consenso al validar un bloque, aparte de emitir el nuevo bloque y confirmar transacciones.

![](/My-Blockchain-Book/images/participantes.PNG "Participantes en la Blockchain")

**¿Pero porqué un participante se hace cargo de este trabajo adicional?**

Los mineros son **recompensados** con bitcoins (o la criptomoneda correspondiente) por sus esfuerzos en gestionar la cadena de bloques.

### Validación de transacciones

La **validación de las transacciones** se realiza de forma independiente por todos los mineros. Este proceso consiste en la validación de más de 20 requisitos, incluyendo tamaño, sintaxis, etc. Algunos de estos criterios pueden ser por ejemplo, que los UTXOs de entrada y salida de la transacción son correctos o que la cantidad de entrada y la cantidad de salida emparejan correctamente. 

![](/My-Blockchain-Book/images/Transaction-Validation.PNG "Proceso de validación de las transacciones")

Las transacciones no válidas se rechazan y no serán transmitidas a la blockchain. Todas aquellas transacciones válidas se añaden a un grupo de transacciones no confirmadas de las que los **mineros** procederán a seleccionar un conjunto de ellas para poder crear un bloque. Pero esto genera el problema de que si cada minero agrega un bloque a la cadena, habrán muchas ramas en la cadena, resultando en un estado inconsistente de la misma. Recuerda que la blockchain es **una sola consistente y enlazada cadena de flujo**. Por lo tanto, necesitamos un sistema para poder superar este problema.

La solución es que los mineros van a competir para resolver un puzle para determinar quién se gana el derecho a crear el siguiente bloque en la cadena. En el caso de la blockchain de Bitcoin este puzle se trata de un problema de cálculo que utiliza intensivamente la CPU. Una vez que un minero soluciona el puzle, el anuncio se difunde a la red y el bloque se transmite también a la red. A continuación, otro participante verifica el nuevo bloque. Tras ello los participantes llegan a un consenso para agregar un nuevo bloque a la cadena o blockchain y además este nuevo bloque es añadido a su copia local de la blockchain (consistencia). Y de esta manera nuevas transacciones son **registradas y confirmadas** en la blockchain. Este algoritmo de consenso se llama **proof-of-work** puesto que implica potencia computacional para resolver el puzle y para reclamar el derecho de crear el siguiente bloque. 

### Transacción Cero o Coinbase

![](/My-Blockchain-Book/images/Coinbase-Transaction.PNG "Transacción Coinbase o Cero")

La transacción cero, es decir, el índice cero de un bloque confirmado, es creada por el minero del bloque. Se caracteriza por tener un UTXO especial y por no tener ningun UTXO de entrada. A este tipo de transacción se la conoce como **transacción coinbase** y estas generan una tarifa o recompensa para el minero por la creación del bloque.

En resumen, las principales operaciones en una blockchain son la validación de transacciones y la creación de bloques con el consenso de los participantes.

## Más alla de Bitcoin

La blockchain de Bitcoin es de código abierto y todo el código está disponible en GitHub. A principios del año 2009 este código abierto se empleo para generar diferentes criptomonedas y alrededor de 300 nuevas criptomonedas fueron generadas.

### Scripting y Smart contracts

Bitcoin admite una característica opcional y especial llamada scripts para la transferencia condicional de valores. La Blockchain de Ethereum extendió esta característica de scripting en un marco de ejecución de código completo llamado **contratos inteligentes (smart contracts)**.

Un contrato inteligente nos proporciona la capacidad poderosa de poder ejecutar cierto código e introducirlo en la lógica empresarial en la blockchain. 

### Tipos de Blockchain

Teniendo en cuenta las capacidades anteriores, podemos distinguir entre tres tipos de blockchain que emrgen de Bitcoin:

- **Tipo 1**: opera únicamente con las monedas de la blockchain, por ejemplo, Bitcoin.
- **Tipo 2**: permite criptomonedas y una capa lógica empresarial soportada por la ejecución de un código, por ejemplo, Ethereum.
- **Tipo 3**: no implica ninguna moneda, pero admite la ejecución de software para la lógica empresarial, por ejemplo, la Hyperledger de la Fundación Linux.

![](/My-Blockchain-Book/images/Types-of-blockchain.PNG "Tipos de Blockchain")

### Categorías de la Blockchain

Con la adición de la ejecución de un código, viene la seria consideración sobre el tema de acceso público a la cadena de bloques, por lo tanto, teniendo en cuenta los límites de acceso a la blockchain podemos clasificarlas en:

- **Blockchain pública**: por ejemplo Bitcoin. Ya que todo en esta cadena esta soportado por sus participantes públicos y cualquiera puede unirse e irse cuando desee. Además los bloques que contienen las transacciones y la cadena de bloques son públicamente observables a pesar de que los participantes son anónimos. Es de código abierto (ya mencionado) y también se puede crear nueva moneda digital mediante la modificación del código Bitcoin.
- **Blockchain privada**: en este tipo el acceso a la blockchain está limitado a ciertos participantes seleccionados, por ejemplo, aquellos participantes dentro de una organización. Esta restricción ayuda a simplificar las operaciones normales, como la creación de bloques y el modelo de contingencia.
- **Blockchain permisiva**: también conocida como la blockchain de consorcio. Este tipo de blockchain está destinada a un consorcio entre partes colaboradoras para realizar transacciones en una cadena de bloques para facilitar la gobernanza, la procedencia y la rendición de cuentas, por ejemplo,
un consorcio de todas las compañías de automóviles u organizaciones de salud. Esta blockchain tiene los beneficios de una cadena de bloques pública al permitir que solo los usuarios con permiso colaboren y realicen transacciones. 

En resumen, innovaciones significativas como los **contratos inteligentes** han abierto aplicaciones más amplias para la tecnología blockchain. La
cadena de bloques privada y permisiva permite el acceso controlado a la cadena de bloques, lo que permite generar diversos modelos de negocio. 

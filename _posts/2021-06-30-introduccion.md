# Introducci贸n a Bitcoin 馃嚜馃嚫
> Introducci贸n a conceptos b谩sicos de blockchain

Table of contents:

1. TOC
{:toc}

## Introducci贸n

Las dos principales contribuciones de la criptomoneda Bitcoin son:
  1. Un sistema de moneda digital que funciona continuamente.
  2. Un modelo para la tecnolog铆a aut贸noma de aplicaciones descentralizadas llamada blockchain.

Alrededor de 2008, 2009, cuando las instituciones y mercados en los que confi谩bamos se desmoronaron, y todo el mundo estaba huyendo de Wall Street, una persona misteriosa, o personas, llamada Satoshi Nakamoto, introdujo una nueva moneda digital, una criptomoneda llamada **Bitcoin**. 

| *Bitcoin habilit贸 una plataforma innovadora para la transferencia de valor entre pares sin ninguna autoridad central.* |

![](/My-Blockchain-Book/images/peer_to_peer.PNG "Transferencia de valor entre pares")

## Blockchain o Cadena de bloques

Pero... Sin una autoridad central, 驴c贸mo proporciona Bitcoin confianza y seguridad? Pues mediante la implementaci贸n de programas de software para validaci贸n, verificaci贸n y consenso en una infraestructura novedosa llamada **blockchain**. M谩s adelante, alrededor de 2012, 2013, se a帽adieron elementos de computaci贸n a la infraestructura de la blockchain que abri贸 todo un mundo de posibilidades m谩s all谩 de la simple transferencia de divisas.  
| *Blockchain trata de habilitar transacciones peer to peer en una red descentralizada (transferencia de recursos digitales sin intermediarios) estableciendo la confianza entre pares desconocidos y registrando la transacci贸n "en un libro digital" inmutable.* |

![](/My-Blockchain-Book/images/Intro-Blockchain.jpg "Cadena de bloques o Blockchain")
La cadena de bloques ha abarcado actualmente una amplia gama de aplicaciones en distintas industrias, incluyendo finanzas, salud, gobierno, fabricaci贸n y distribuci贸n.

### Que es una red descentralizada?

Consideremos un escenario en el que un cliente quiere comprar un art铆culo con su tarjeta de cr茅dito. Los intermediarios que estar谩n involucrados en la realizaci贸n de esta tarea ser谩n:

- La agencia de tarjeta de cr茅ditos.
- El banco del cliente.
- Un banco de tarjetas de cr茅dito.
- Un intercambio.
- El banco del comerciante.
- El comerciante.

Este es un ejemplo de un **sistema centralizado** al que estamos tan acostumbrados. Ahora comparemos este con un sistema donde los participantes pueden realizar transacciones directamente entre ellos, independientemente de d贸nde se encuentren. Las funciones de los intermediarios del sistema centralizado se desplazan a la periferia al participante del mismo nivel en la infraestructura blockchain. Estos participantes o tambi茅n llamados peers no son necesariamente conocidos entre s铆. **Esto es un sistema descentralizado**.

![](/My-Blockchain-Book/images/Centralized-Decentralized.png "Sistema centralizado vs descentralizado")
[Pincha para leer m谩s sobre sistemas centralizados y descentralizados](https://medium.com/hackernoon/centralization-vs-decentralization-the-best-and-worst-of-both-worlds-7bfdd628ad09)

Pero 驴c贸mo establecemos la confianza entre los participantes en un sistema tan descentralizado? Pues disponiendo de un proceso para validar, verificar y confirmar las transacciones. Para posteriormente registrar dicha transacci贸n en un "libro mayor distribuido de bloques", crear un registro de bloques a prueba de manipulaciones (cadena de bloques) e implementar un protocolo de consenso para acordar el bloque que se va a agregar a dicha cadena.

| *Por lo tanto, la validaci贸n, la verificaci贸n, el consenso y la grabaci贸n inmutable conducen a la confianza y la seguridad de la cadena de bloques* |

Vamos a ver lo comentado anteriormente a traves de un ejemplo: David le presta a Amy 10.000鈧? (esto es una 煤nica transacci贸n punto a punto) y ambos lo anotan en sus respectivos libros mayores. Pero, David es deshonesto y cambia en su libro dicha entrada de 10.000鈧? a 11.000鈧?. Amy hace lo mismo cambiando su entrada de 10.000 鈧? a 1.000鈧?. 

Para evitar esta violaci贸n de confianza, necesitamos buscar la ayuda de personas que nos rodean, por ejemplo, Lisa, Allison y Francis y le proporcionamos a todos ellos una copia v谩lida de este libro mayor. Este es el concepto b谩sico del **libro mayor distribuido inmutable** definido en un proceso blockchain. 

En este escenario, da la casualidad que todos estamos f铆sicamente presentes en un solo lugar. Ahora imaginemos que esto es una transacci贸n online entre pares desconocidos. Adem谩s, en lugar de tener una 煤nica transacci贸n tenemos 10.000 transacciones o tal vez un mill贸n de transacciones. Deber铆amos de ser capaz de realizar estas transacciones con la misma facilidad con cualquier otro participante desconocido en cualquier otro lugar. Este es el principio de un sistema descentralizado apoyado por blockchain.  

En el caso que acabamos de describir, 驴c贸mo confiamos en otros participantes desconocidos? A trav茅s de **la verificaci贸n y validaci贸n**. En nuestro ejemplo, Amy le pide a Kevin que verifique la cantidad que David acord贸 con ella. Kevin lo comprueba y encuentra que la cantidad de la transacci贸n no es 10.000, sino 300, por lo tanto la transacci贸n no es v谩lida. Kevin rechaza y anula dicha transacci贸n.

Similar a estos, la validaci贸n y los m茅todos de verificaci贸n ideados por la cadena de bloques e implementados por los pares proporcionan la confianza del colector necesaria en un sistema descentralizado.

### Estructura de la blockchain

Una transacci贸n es el elemento b谩sico de la blockchain de bitcoin.
1. Las transacciones son validadas y difundidas.
2. Varias transacciones forman un bloque.
3. Muchos bloques forman una cadena a trav茅s de un enlace de datos digital.
4. Los bloques pasan por un proceso de consenso, para seleccionar cual ser谩 el siguiente bloque que se agregar谩 a la cadena.
5. El bloque elegido se verifica y se agrega a la cadena actual.
6. El proceso de consenso y la validaci贸n son realizados por nodos especiales llamados mineros. Estos son potentes ordenadores ejecutando software definido por el protocolo de la blockchain. 

### Transacci贸n en Bitcoin

Veamos ahora cu谩les son detalles de una transacci贸n en la blockchain de bitcoin.

#### UTXO

Un concepto fundamental de una red de bitcoin es una **Unspent Transaction Output (transacci贸n de salida no gastada)**, tambi茅n conocida como UTXO. El conjunto de todas las UTXOs en una red de bitcoin define colectivamente el estado de la cadena de bloques. 

![](/My-Blockchain-Book/images/UTXO.PNG "UTXOs se referencian tanto como entradas de una transacci贸n y como salidas deneradas por esa transacci贸n. Todas esas UTXOs en un sistema, son almacenados por los nodos participantes en una base de datos") 

[Picha aqui para leer m谩s sobre UTXO (espa帽ol)](https://academy.bit2me.com/que-es-una-utxo/)

Ahora revisemos el papel de las UTXOs en una blockchain de bitcoin: una **transacci贸n** utiliza la cantidad especificada por una o m谩s UTXOs de entrada y la transmite a una o m谩s UTXOs de salida reci茅n creadas, seg煤n la petici贸n iniciada por el remitente. La estructura de una **UTXO** dada es la siguiente:
- Un identificador 煤nico de la transacci贸n que cre贸 este UTXO.
- Un 铆ndice o posici贸n de la UTXO en la lista de UTXOs de salida de la transacci贸n.
- Un valor o cantidad para la que es v谩lida.
- Y un texto opcional que indica las condiciones bajo las cuales la salida puede ser gastada.

#### Transacci贸n

Una transacci贸n a su vez incluye:
- Un n煤mero de referencia de la transacci贸n actual
- Referencias a una o m谩s UTXOs de entrada
- Referencias a una o m谩s UTXOs de salida reci茅n generadas por la transacci贸n actual, es decir, transacci贸n de salida no gastada
- Cantidad total de entrada y salida

Veamos ahora un ejemplo de una transacci贸n real

![](/My-Blockchain-Book/images/Transaction-Number.PNG "Identificador de la transacci贸n") 

Vemos que justo abajo hay tres UTXOs de entrada a dicha transacci贸n y una flecha que se帽ala a las UTXOs de salida de la transacci贸n

![](/My-Blockchain-Book/images/Input-UTXO.PNG "UTXOs de entrada") 
![](/My-Blockchain-Book/images/Output-UTXO.PNG "UTXOs de salida") 

Observa que hay tres UTXOs de entrada y solo dos de salida. Esto significa que la cantidad total de las tres UTXOs de entrada se emplean en generar dos nuevas UTXOs de salida. Justo debajo de las UTXOs de salida est谩 la cantidad total transferida en valor de Bitcoin.

![](/My-Blockchain-Book/images/BTC-total-value.PNG "Cantidad total transferida en valor de Bitcoin") 

#### Bloque

Un bloque dispone de una cabecera con informaci贸n sobre el bloque y un conjunto de transacciones v谩lidas.

![](/My-Blockchain-Book/images/Block-header.PNG "Cabecera del bloque")

Este el llamado bloque g茅nesis. Satoshi Nakamoto inici贸 la blockchain de Bitcoin con una transacci贸n de 50 BTC. Esta transacci贸n cre贸 mitad de las UTXOs de salida hacia su propia direcci贸n. La fecha de la creaci贸n de este bloque g茅nesis en la blockchain es el 3 de enero de 2009.

[Picha aqui para leer m谩s sobre el bloque g茅nesis (en espa帽ol)](https://academy.bit2me.com/que-es-bloque-genesis/)

No hab铆a ning煤n bloque anterior ya que este es el primero de la cadena, por lo que el campo **Previous Block** esta a cero. Tambi茅n se lista una recompensa de bloque o unos honorarios de minero de 50 BTC. Hablaremos de la recompensa del minero en lecciones m谩s adelante. 

![](/My-Blockchain-Book/images/Block-transaction.PNG "Conjunto de transacciones v谩lidas en el bloque g茅nesis")

Ahora, echemos un vistazo a la estructura de la Blockchain mirando en la blockchain de Bitcoin. Nuestro objetivo es entender la relaci贸n entre los bloques. Consideremos la cadena de tres bloques: #488868, #488867 y #488869.

![](/My-Blockchain-Book/images/Block-link.PNG "Bloques #488867, #488868 y #488869")

Vemos que el bloque #488868 que se muestra en el medio, tiene el hash del bloque #488867 como su hash anterior. Por otra lado, el bloque #488869 tiene el hash del #488868 como su hash anterior, formando de esta manera **los enlaces en la cadena**.

En resumen, una transacci贸n genera la transferencia de valor en la blockchain de Bitcoin. El concepto de UTXO define las entradas y salidas de dichas transacciones. Una vez que un bloque es verificado y algor铆tmicamente acordado por los mineros, se agrega a la cadena de bloques, es decir, a la blockchain.

## Operaciones b谩sicas en Blockchain

Las operaciones en una red descentralizada son responsabilidad de los participantes (peers) y de sus respectivos nodos computacionales, estos 煤ltimos pueden ser: port谩til, ordenador o bastidores de servidores. Estas operaciones incluyen:
- Validaci贸n de las transacciones
- Agrupar las transacciones en un bloque
- Publicar bloques y transacciones v谩lidas
- Llegar a un consenso para la creaci贸n del siguiente bloque de la cadena
- Encadenar bloques para crear un registro inmutable

### Participantes

Podemos distinguir entre dos tipos de participantes:
- Aquellos que inician la transferencia de valor creando una transacci贸n
- **Miners**: son aquellos que deciden realizar un "trabajos o c谩lculos" extra para verificar las transacciones y emitir transacciones. Adem谩s compiten con otros mineros para poder crear un bloque, trabajan por conseguir consenso al validar un bloque, aparte de emitir el nuevo bloque y confirmar transacciones.

![](/My-Blockchain-Book/images/participantes.PNG "Participantes en la Blockchain")

**驴Pero porqu茅 un participante se hace cargo de este trabajo adicional?**

Los mineros son **recompensados** con bitcoins (o la criptomoneda correspondiente) por sus esfuerzos en gestionar la cadena de bloques.

### Validaci贸n de transacciones

La **validaci贸n de las transacciones** se realiza de forma independiente por todos los mineros. Este proceso consiste en la validaci贸n de m谩s de 20 requisitos, incluyendo tama帽o, sintaxis, etc. Algunos de estos criterios pueden ser por ejemplo, que los UTXOs de entrada y salida de la transacci贸n son correctos o que la cantidad de entrada y la cantidad de salida emparejan correctamente. 

![](/My-Blockchain-Book/images/Transaction-Validation.PNG "Proceso de validaci贸n de las transacciones")

Las transacciones no v谩lidas se rechazan y no ser谩n transmitidas a la blockchain. Todas aquellas transacciones v谩lidas se a帽aden a un grupo de transacciones no confirmadas de las que los **mineros** proceder谩n a seleccionar un conjunto de ellas para poder crear un bloque. Pero esto genera el problema de que si cada minero agrega un bloque a la cadena, habr谩n muchas ramas en la cadena, resultando en un estado inconsistente de la misma. Recuerda que la blockchain es **una sola consistente y enlazada cadena de flujo**. Por lo tanto, necesitamos un sistema para poder superar este problema.

La soluci贸n es que los mineros van a competir para resolver un puzle para determinar qui茅n se gana el derecho a crear el siguiente bloque en la cadena. En el caso de la blockchain de Bitcoin este puzle se trata de un problema de c谩lculo que utiliza intensivamente la CPU. Una vez que un minero soluciona el puzle, el anuncio se difunde a la red y el bloque se transmite tambi茅n a la red. A continuaci贸n, otro participante verifica el nuevo bloque. Tras ello los participantes llegan a un consenso para agregar un nuevo bloque a la cadena o blockchain y adem谩s este nuevo bloque es a帽adido a su copia local de la blockchain (consistencia). Y de esta manera nuevas transacciones son **registradas y confirmadas** en la blockchain. Este algoritmo de consenso se llama **proof-of-work** puesto que implica potencia computacional para resolver el puzle y para reclamar el derecho de crear el siguiente bloque. 

### Transacci贸n Cero o Coinbase

![](/My-Blockchain-Book/images/Coinbase-Transaction.PNG "Transacci贸n Coinbase o Cero")

La transacci贸n cero, es decir, el 铆ndice cero de un bloque confirmado, es creada por el minero del bloque. Se caracteriza por tener un UTXO especial y por no tener ningun UTXO de entrada. A este tipo de transacci贸n se la conoce como **transacci贸n coinbase** y estas generan una tarifa o recompensa para el minero por la creaci贸n del bloque.

En resumen, las principales operaciones en una blockchain son la validaci贸n de transacciones y la creaci贸n de bloques con el consenso de los participantes.

## M谩s alla de Bitcoin

La blockchain de Bitcoin es de c贸digo abierto y todo el c贸digo est谩 disponible en GitHub. A principios del a帽o 2009 este c贸digo abierto se empleo para generar diferentes criptomonedas y alrededor de 300 nuevas criptomonedas fueron generadas.

### Scripting y Smart contracts

Bitcoin admite una caracter铆stica opcional y especial llamada scripts para la transferencia condicional de valores. La Blockchain de Ethereum extendi贸 esta caracter铆stica de scripting en un marco de ejecuci贸n de c贸digo completo llamado **contratos inteligentes (smart contracts)**.

Un contrato inteligente nos proporciona la capacidad poderosa de poder ejecutar cierto c贸digo e introducirlo en la l贸gica empresarial en la blockchain. 

### Tipos de Blockchain

Teniendo en cuenta las capacidades anteriores, podemos distinguir entre tres tipos de blockchain que emrgen de Bitcoin:

- **Tipo 1**: opera 煤nicamente con las monedas de la blockchain, por ejemplo, Bitcoin.
- **Tipo 2**: permite criptomonedas y una capa l贸gica empresarial soportada por la ejecuci贸n de un c贸digo, por ejemplo, Ethereum.
- **Tipo 3**: no implica ninguna moneda, pero admite la ejecuci贸n de software para la l贸gica empresarial, por ejemplo, la Hyperledger de la Fundaci贸n Linux.

![](/My-Blockchain-Book/images/Types-of-blockchain.PNG "Tipos de Blockchain")

### Categor铆as de la Blockchain

Con la adici贸n de la ejecuci贸n de un c贸digo, viene la seria consideraci贸n sobre el tema de acceso p煤blico a la cadena de bloques, por lo tanto, teniendo en cuenta los l铆mites de acceso a la blockchain podemos clasificarlas en:

- **Blockchain p煤blica**: por ejemplo Bitcoin. Ya que todo en esta cadena esta soportado por sus participantes p煤blicos y cualquiera puede unirse e irse cuando desee. Adem谩s los bloques que contienen las transacciones y la cadena de bloques son p煤blicamente observables a pesar de que los participantes son an贸nimos. Es de c贸digo abierto (ya mencionado) y tambi茅n se puede crear nueva moneda digital mediante la modificaci贸n del c贸digo Bitcoin.
- **Blockchain privada**: en este tipo el acceso a la blockchain est谩 limitado a ciertos participantes seleccionados, por ejemplo, aquellos participantes dentro de una organizaci贸n. Esta restricci贸n ayuda a simplificar las operaciones normales, como la creaci贸n de bloques y el modelo de contingencia.
- **Blockchain permisiva**: tambi茅n conocida como la blockchain de consorcio. Este tipo de blockchain est谩 destinada a un consorcio entre partes colaboradoras para realizar transacciones en una cadena de bloques para facilitar la gobernanza, la procedencia y la rendici贸n de cuentas, por ejemplo,
un consorcio de todas las compa帽铆as de autom贸viles u organizaciones de salud. Esta blockchain tiene los beneficios de una cadena de bloques p煤blica al permitir que solo los usuarios con permiso colaboren y realicen transacciones. 

En resumen, innovaciones significativas como los **contratos inteligentes** han abierto aplicaciones m谩s amplias para la tecnolog铆a blockchain. La
cadena de bloques privada y permisiva permite el acceso controlado a la cadena de bloques, lo que permite generar diversos modelos de negocio. 

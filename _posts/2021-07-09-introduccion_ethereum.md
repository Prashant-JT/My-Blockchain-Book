# Introducci贸n a Ethereum 馃嚜馃嚫
> Introducci贸n a conceptos b谩sicos de la blockchain de Ethereum

Table of contents:

1. TOC
{:toc}

## Introducci贸n
La blockchain de Bitcoin es la madre de todas las blockchains. Fue dise帽ada para la transferencia de valor entre pares y lo hace bien. Pero, alrededor de 2013 se introduj贸 un marco para la ejecuci贸n de c贸digo que fue introducido por los fundadores de Ethereum. La pieza central y el empuje de esta blockchain  de Ethereum es el llamado **contrato inteligente**. 

### Comparaci贸n Blockchain Bitcoin vs Ethereum

![](/My-Blockchain-Book/images/Ethereum-vs-Bitcoin.PNG "Comparaci贸n de la Blockchain de Bitcoin contra Ethereum")

A la **izquierda** est谩 la blockchain de Bitcoin y una aplicaci贸n de billetera para iniciar transacciones en dicha cadena. A la **derecha** est谩 Ethereum que di贸 un paso significativo hacia la transformaci贸n de la cadena de bloques en un marco computacional que abri贸 todo un mundo de oportunidades en el entorno descentralizado. Ethereum permite **contratos inteligentes y m谩quinas virtuales** en las que se ejecutan dichos contratos inteligentes. Los contratos inteligentes, a su vez, permiten aplicaciones descentralizadas que logran m谩s que una transferencia de valor. En este post, hablaremos de una visi贸n general de alto nivel sobre los contratos inteligentes en lo que se refiere a la blockchain de Ethereum. 

## Contrato Inteligente (Smart Contract)
驴Qu茅 es un contrato inteligente? Un **contrato inteligente** es un fragmento de c贸digo implementado en nodos (por ejemplo ordenadores de los participantes) de la blockchain.

### Ejecuci贸n de un Contrato Inteligente

La **ejecuci贸n de un contrato inteligente** se inicia mediante un mensaje incrustado en la transacci贸n. Para la transferencia de monedas digitales simplemente se require operaciones de suma y resta. Pero, Ethereum permite transacciones que pueden llevar a cabo operaciones m谩s sofisticadas. Por ejemplo, una transacci贸n podr铆a requerir una transferencia condicional, puede necesitar cierta evaluaci贸n, puede necesitar m谩s de una firma para la transferencia de activos o puede implicar esperar una fecha o una hora espec铆fica.

![](/My-Blockchain-Book/images/Smart-Contract-1.PNG "Ejemplo de un contrato inteligente")

Por ejemplo, un contrato inteligente de licitaci贸n de subastas podr铆a ejecutar la l贸gica de la imagen de arriba. Es decir, si la edad de un pujador es superior a 18 a帽os y la puja es mayor que la puja m铆nima, acepta la puja o rechaza la puja. Esto se puede hacer mediante un contrato inteligente.

### Estructura de un Contrato Inteligente

驴C贸mo se ve el contrato inteligente? 驴C贸mo se escribe un contrato inteligente? Estructuralmente, un contrato inteligente se asemeja a la definici贸n de una clase en un dise帽o orientado a objetos (por ejemplo en el lenguaje java). Tiene datos, funciones o m茅todos con modificadores p煤blicos o privados,
junto con getter y setter y un conjunto de funciones.Se han dise帽ado lenguajes de programaci贸n espec铆ficos para programar contratos inteligentes, entre ellos esta el lenguaje **Solidity**.

Vamos a examinar un contrato inteligente simple en Solidity para entender su estructura:

![](/My-Blockchain-Book/images/Smart-Contract-2.PNG "Estructura de un contrato inteligente en Solidity")

La primera l铆nea con "pragma" indica la versi贸n del lenguaje de solidity. Tras ello viene el nombre del contrato que est谩 en la primera l铆nea ("Simple Storage"). Este contrato en particular es para el almacenamiento de un entero. Los datos para el entero se definen con el tipo uint. Se definen dos funciones para escribir y leer los datos. 

### Ejecuci贸n del c贸digo de un Contrato Inteligente

驴D贸nde se ejecuta el c贸digo que esta en el contrato inteligente? 驴D贸nde se encuentra en un nodo? Necesitamos una infraestructura computacional para ejecutar cualquier c贸digo arbitrario. Cualquier nodo de la red de Ethereum debe ser capaz de ejecutar dicho c贸digo independientemente de su tipo subyacente de hardware o sistema operativo.

![](/My-Blockchain-Book/images/Smart-Contract-3.PNG "Ejecuci贸n del c贸digo de un Contrato Inteligente")

Para ello usamos la **m谩quina virtual de Ethereum(EVM)**. Un contrato inteligente escrito un lenguaje de programaci贸n de alto nivel se traduce a c贸digo de bytes en EVM y, a continuaci贸n, se implementa en la m谩quina virtual de Ethereum. Cada nodo de la red alojar谩 los mismos c贸digos de los contratos inteligentes en su m谩quina virtual de Ethereum.

> Resumiendo, los contratos inteligentes agregan una capa l贸gica y computacional a la infraestructura de confianza soportada por la cadena de bloques. Los contratos inteligentes permiten la ejecuci贸n de c贸digo y mejorar la capacidad b谩sica de transferencia de valor de la cadena de bloques Bitcoin. El c贸digo para este contrato inteligente est谩 escrito en un lenguaje de alto nivel como Solidity y compilado a c贸digo de bytes para posteriormente ser ejecutado en una estructura especial conocida como m谩quina virtual Ethereum.

## Estructura de Ethereum

Recordemos que el estado de la blockchain de **Bitcoin** se define en t茅rminos de salidas de transacciones no utilizadas: UTXOs. **Ethereum** introduce formalmente el concepto de una **cuenta** como parte del protocolo.

### Cuentas

- Una cuenta es tanto el origen como el destino de una transacci贸n.
- Una transacci贸n actualiza directamente los saldos de la cuenta para mantener el estado de la cadena como ocurr铆a en Bitcoin con los UTXOs.
- Permiten la transmisi贸n de valor y mensajes y datos entre las cuentas, que pueden dar lugar a las transiciones de estado.
- Estas transferencias se implementan mediante transacciones. 

![](/My-Blockchain-Book/images/Ethereum-Structure.PNG "Estructura de Ethereum")

### Tipos de cuentas

![](/My-Blockchain-Book/images/Ethereum-Account-Type.PNG "Tipos de cuentas en Ethereum")

Existen dos tipos de cuenta en Ethereum:
- Cuentas de **propiedad externa (Externally owned account or EOA)**: estas est谩n controladas por claves privadas. Adem谩s, se necesita este tipo de cuenta para poder participar en la red de Ethereum ya que esta interact煤a con la blockchain mediante transacciones.
- Cuentas de **contrato (Contract accounts or CA)**: estas est谩n controladas por un c贸digo y solo pueden ser activada mediante una cuenta de propiedad externa. Este tipo de cuenta representan a un contrato inteligente.

### Tarifa de una transacci贸n

Cada cuenta tiene un saldo de monedas. Un nodo participante puede enviar una transacci贸n ya sea para la transferencia de Ether o para invocar un c贸digo de un contrato inteligente o ambos. Ambos tipos de transacciones requieren de **tarifa o honorarios**. Por lo tanto, una cuenta debe tener un saldo suficiente para cubrir las tarifas necesarias para que las transacciones sean activadas. Las tarifas se pagan en **Wei** que es una denominaci贸n m谩s baja de **脡ther**. En la imagen siguiente se ve la correspondencia:

![](/My-Blockchain-Book/images/Ether-Wei.PNG "Correspondencia Ether-Wei")

### Estructura de las transacciones

Una transacci贸n en Ethereum incluye:
- El **destinatario** del mensaje
- La **firma digital** del remitente que autoriza la transferencia
- La **cantidad de Wei** a transferir
- Un campo de **datos opcional o una carga 煤til** que contiene un mensaje para un contrato inteligente
- **STARTGAS** que es un valor que representa el n煤mero m谩ximo de pasos computacionales para la transacci贸n
- **Precio del gas**, un valor que representa la tarifa que el remitente est谩 dispuesto a pagar por los c谩lculos.

Veamos un ejemplo de una transacci贸n en la red de Ethereum:

![](/My-Blockchain-Book/images/Ethereum-Transaction.PNG "Ejemplo de una transacci贸n en Ethereum")

Podemos apreciar el hash de la transacci贸n, la altura de la cadena, la marca de tiempo, las cuentas de origen y destino, cantidad transferida, el l铆mite de gas, el gas utilizado, estado de la transacci贸n (success en este caso) y nonce. Esta transacci贸n en particular esta invocando a un contrato inteligente. Por supuesto, para la ejecuci贸n de un contrato inteligente se incurre en ciertas tarifas y la cantidad disponible es especificada por los diversos campos de gas en la transacci贸n.

### Estructura de bloques

Los bloques en la cadena de Ethereum tienen una **cabecera**, ciertas **transacciones** y **runner-up headers**. Veamos cuales son los detalles de un bloque con el siguiente ejemplo:

![](/My-Blockchain-Book/images/Ethereum-Block.PNG "Ejemplo de un bloque en Ethereum")

Este es un bloque real de Ethereum a la altura 4446308. Vemos en la imagen la altura del bloque, la marca de tiempo, el hash de bloque, su hash anterior, dificultad y dificultad total, tama帽o, gas utilizado, l铆mite de gas, nonce y la recompensa de bloque.

## Operaciones en Ethereum

Para una simple transferencia de Ether en la blockchain de Ethereum, la cantidad a transferir y la direcci贸n de destino se especifican junto con las tarifas o puntos de gas. El importe y las tasas se transfieren a sus respectivas cuentas. Veamos esto a tr谩ves de un ejemplo:

![](/My-Blockchain-Book/images/Ethereum-Operation.PNG "Ejemplo de una operaci贸n en Ethereum")

En la imagen anterior, podemos ver una transacci贸n de transferencia de 100 Ether entre las cuentas del remitente y del destinatario. Hay que tener en cuenta que adem谩s de esta transferencia, se pagan 21.000 puntos de gas al minero que agreg贸 el bloque de transacci贸n a la cadena de bloques.

### Nodo

Un **nodo** de Ethereum es un sistema computacional que representa una entidad empresarial o un participante individual. Un **nodo completo** de Ethereum aloja el software necesario para:
- El inicio de las transacciones
- Validaci贸n de las mismas
- Miner铆a
- Creaci贸n de bloques
- Ejecuci贸n de contratos inteligentes
- La m谩quina virtual de Ethereum, EVM

### Ejecuci贸n de un contrato inteligente

![](/My-Blockchain-Book/images/Execution-SmartContract.PNG "Ejecuci贸n de un contrato inteligente")

Esta figura muestra la **implementaci贸n y invocaci贸n de un contrato inteligente**. Un contrato inteligente est谩 dise帽ado, desarrollado, compilado e implementado en el EVM y estas pueden tener m谩s de un contrato inteligente. Cuando la direcci贸n de destino en una transacci贸n es un contrato inteligente, el c贸digo de ejecuci贸n correspondiente al contrato inteligente se activa y ejecuta en el EVM. La entrada necesaria para su ejecuci贸n se extrae del campo de datos opcionales de la transacci贸n.

El **estado actual** de un contrato son los valores de las variables que est谩n definidas en 茅l, pero este se puede actualizar mediante su ejecuci贸n. Los resultados de esta ejecuci贸n se guardan en los llamados **recibos**. Una cadena de bloques mantiene tanto el hash de estado como el de recibo.

### Transacciones

Todas las transacciones son **validadas**. Esta validaci贸n implica comprobar que la marca de tiempo y la combinaci贸n nonce sean v谩lidas y la disponibilidad de honorarios o tarifas suficientes para la ejecuci贸n.

Los **nodos mineros** de la red reciben, verifican, recopilan y ejecutan transacciones. Adem谩s, el c贸digo de invocaci贸n de un contrato inteligente es ejecutado por todos los mineros. Posteriormente, las transacciones validadas se difunden y se recopilan para la creaci贸n de bloques. **El protocolo de consenso utilizado en la red de Ethereum es una prueba de trabajo basada en memoria en lugar de una CPU**. Pero... 驴Qui茅n paga todas estas operaciones de validaci贸n, verificaci贸n y consenso? Lo vemos a continuaci贸n.

## Modelo incentivo en Ethereum

Recordemos que la **miner铆a** es el proceso utilizado para proteger la red mediante la validaci贸n de los c谩lculos, la recopilaci贸n de ellos para formar un bloque, su verificaci贸n y difusi贸n. **Ethereum tambi茅n utiliza un modelo basado en incentivos para la creaci贸n de bloques**. A continuaci贸n procederemos a hablar sobre la estructura de tarifas y el modelo de incentivo en la red de Ethereum.

### Puntos de Gas (Transacci贸n)
Cualquier accci贸n en Ethereum requiere de **gas** y estos se utilizan para especificar las tarifas dentro de Ether. El **Ether**, como criptomoneda, var铆a su valor con las oscilaciones que se producen en el mercado, pero **los puntos de gas no var铆an**. Ethereum ha especificado puntos de gas para cada tipo de operaci贸n:

![](/My-Blockchain-Book/images/Gas-Fees.PNG "Tarifas o puntos de gas en Ethereum")

En el proceso de miner铆a se calculan los puntos de gas necesarios para la ejecuci贸n de una transacci贸n. Si la tarifa especificada y
el punto de gas en la transacci贸n no son suficientes, se rechaza. Esto es similar a enviar una carta con franqueo insuficiente. La carta no se entregar谩 si no tiene franqueo suficiente.

Los puntos de gas necesarios para la ejecuci贸n de una transacci贸n **deben estar disponibles en el saldo de la cuenta** para que dicha ejecuci贸n se lleve a cabo. Si queda alg煤n importe despu茅s de la ejecuci贸n de una transacci贸n, esta se devuelve a la cuenta de origen.

### Puntos de Gas (Bloque)

Hasta ahora hemos hablado sobre el gas empleado en una transacci贸n, ahora veamos el concepto de gas relacionado con un bloque.

#### L铆mite de gas y gas gastado

**L铆mite de gas** es la cantidad m谩xima de gas que un bloque podr谩 gastar. Por ejemplo, si un bloque especifica un l铆mite de 1,5 mill贸nes de unidades de gas, y una comisi贸n b谩sica de transacci贸n de Ether es de 21.000, entonces en este bloque de Ethereum en particular pueden caber alrededor de 70 transacciones simples de Ether. Adem谩s, si agregamos en este bloque transacciones de contratos inteligentes, que por lo general requieren de mayor cantidad gas, entonces el n煤mero de transacciones para este bloque disminuir谩.

El **gas gastado** es la cantidad real de gas gastada al finalizar la creaci贸n del bloque actual. 

### Modelo de incentivo minero

El minero que consiga resolver el puzle del "Proof of Work" ser谩 el encargado de crear el bloque nuevo en la blockchain. Todos los mineros que compiten para poder crear un nuevo bloque est谩n incentivados con las **tarifas b谩sicas de 3 Ethers** adem谩s de las **tarifas de una transacci贸n en la red de Ethereum**. El minero ganador tambi茅n recibe los honorarios, puntos de gas para la ejecuci贸n de una transacci贸n de contrato inteligente.

Pero... pueden haber otros mineros que tambi茅n resuelvan el rompecabezas o el puzle adem谩s del ganador. Estos mineros que tambi茅n resolvieron el puzle pero no se ganaron el derecho para poder crear el bloque en la cadena son los llamados **Ommers**. Los bloques creados por ellos se llaman **Ommer Blocks** y estos se a帽aden como bloques Ommer, o bloques laterales, a la cadena principal. Adem谩s, estos mineros Ommer tambi茅n obtienen un peque帽o porcentaje del total de puntos de gas como consuelo y para la seguridad de la red.

![](/My-Blockchain-Book/images/Mining-Incentive-Model.PNG "Modelo de incentivo minero")

Resumiendo, cualquier transacci贸n en Ethereum, incluida la transferencia de Ethers, requiere de tarifas o puntos de gas necesarios para ser especificados en las transacciones.Adem谩s, los mineros reciben honorarios o puntos de gas por seguridad, validaci贸n, ejecuci贸n de contratos inteligentes, as铆 como por la creaci贸n de bloques. 

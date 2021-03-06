# Introducción a Ethereum 🇪🇸
> Introducción a conceptos básicos de la blockchain de Ethereum

Table of contents:

1. TOC
{:toc}

## Introducción
La blockchain de Bitcoin es la madre de todas las blockchains. Fue diseñada para la transferencia de valor entre pares y lo hace bien. Pero, alrededor de 2013 se introdujó un marco para la ejecución de código que fue introducido por los fundadores de Ethereum. La pieza central y el empuje de esta blockchain  de Ethereum es el llamado **contrato inteligente**. 

### Comparación Blockchain Bitcoin vs Ethereum

![](/My-Blockchain-Book/images/Ethereum-vs-Bitcoin.PNG "Comparación de la Blockchain de Bitcoin contra Ethereum")

A la **izquierda** está la blockchain de Bitcoin y una aplicación de billetera para iniciar transacciones en dicha cadena. A la **derecha** está Ethereum que dió un paso significativo hacia la transformación de la cadena de bloques en un marco computacional que abrió todo un mundo de oportunidades en el entorno descentralizado. Ethereum permite **contratos inteligentes y máquinas virtuales** en las que se ejecutan dichos contratos inteligentes. Los contratos inteligentes, a su vez, permiten aplicaciones descentralizadas que logran más que una transferencia de valor. En este post, hablaremos de una visión general de alto nivel sobre los contratos inteligentes en lo que se refiere a la blockchain de Ethereum. 

## Contrato Inteligente (Smart Contract)
¿Qué es un contrato inteligente? Un **contrato inteligente** es un fragmento de código implementado en nodos (por ejemplo ordenadores de los participantes) de la blockchain.

### Ejecución de un Contrato Inteligente

La **ejecución de un contrato inteligente** se inicia mediante un mensaje incrustado en la transacción. Para la transferencia de monedas digitales simplemente se require operaciones de suma y resta. Pero, Ethereum permite transacciones que pueden llevar a cabo operaciones más sofisticadas. Por ejemplo, una transacción podría requerir una transferencia condicional, puede necesitar cierta evaluación, puede necesitar más de una firma para la transferencia de activos o puede implicar esperar una fecha o una hora específica.

![](/My-Blockchain-Book/images/Smart-Contract-1.PNG "Ejemplo de un contrato inteligente")

Por ejemplo, un contrato inteligente de licitación de subastas podría ejecutar la lógica de la imagen de arriba. Es decir, si la edad de un pujador es superior a 18 años y la puja es mayor que la puja mínima, acepta la puja o rechaza la puja. Esto se puede hacer mediante un contrato inteligente.

### Estructura de un Contrato Inteligente

¿Cómo se ve el contrato inteligente? ¿Cómo se escribe un contrato inteligente? Estructuralmente, un contrato inteligente se asemeja a la definición de una clase en un diseño orientado a objetos (por ejemplo en el lenguaje java). Tiene datos, funciones o métodos con modificadores públicos o privados,
junto con getter y setter y un conjunto de funciones.Se han diseñado lenguajes de programación específicos para programar contratos inteligentes, entre ellos esta el lenguaje **Solidity**.

Vamos a examinar un contrato inteligente simple en Solidity para entender su estructura:

![](/My-Blockchain-Book/images/Smart-Contract-2.PNG "Estructura de un contrato inteligente en Solidity")

La primera línea con "pragma" indica la versión del lenguaje de solidity. Tras ello viene el nombre del contrato que está en la primera línea ("Simple Storage"). Este contrato en particular es para el almacenamiento de un entero. Los datos para el entero se definen con el tipo uint. Se definen dos funciones para escribir y leer los datos. 

### Ejecución del código de un Contrato Inteligente

¿Dónde se ejecuta el código que esta en el contrato inteligente? ¿Dónde se encuentra en un nodo? Necesitamos una infraestructura computacional para ejecutar cualquier código arbitrario. Cualquier nodo de la red de Ethereum debe ser capaz de ejecutar dicho código independientemente de su tipo subyacente de hardware o sistema operativo.

![](/My-Blockchain-Book/images/Smart-Contract-3.PNG "Ejecución del código de un Contrato Inteligente")

Para ello usamos la **máquina virtual de Ethereum(EVM)**. Un contrato inteligente escrito un lenguaje de programación de alto nivel se traduce a código de bytes en EVM y, a continuación, se implementa en la máquina virtual de Ethereum. Cada nodo de la red alojará los mismos códigos de los contratos inteligentes en su máquina virtual de Ethereum.

> Resumiendo, los contratos inteligentes agregan una capa lógica y computacional a la infraestructura de confianza soportada por la cadena de bloques. Los contratos inteligentes permiten la ejecución de código y mejorar la capacidad básica de transferencia de valor de la cadena de bloques Bitcoin. El código para este contrato inteligente está escrito en un lenguaje de alto nivel como Solidity y compilado a código de bytes para posteriormente ser ejecutado en una estructura especial conocida como máquina virtual Ethereum.

## Estructura de Ethereum

Recordemos que el estado de la blockchain de **Bitcoin** se define en términos de salidas de transacciones no utilizadas: UTXOs. **Ethereum** introduce formalmente el concepto de una **cuenta** como parte del protocolo.

### Cuentas

- Una cuenta es tanto el origen como el destino de una transacción.
- Una transacción actualiza directamente los saldos de la cuenta para mantener el estado de la cadena como ocurría en Bitcoin con los UTXOs.
- Permiten la transmisión de valor y mensajes y datos entre las cuentas, que pueden dar lugar a las transiciones de estado.
- Estas transferencias se implementan mediante transacciones. 

![](/My-Blockchain-Book/images/Ethereum-Structure.PNG "Estructura de Ethereum")

### Tipos de cuentas

![](/My-Blockchain-Book/images/Ethereum-Account-Type.PNG "Tipos de cuentas en Ethereum")

Existen dos tipos de cuenta en Ethereum:
- Cuentas de **propiedad externa (Externally owned account or EOA)**: estas están controladas por claves privadas. Además, se necesita este tipo de cuenta para poder participar en la red de Ethereum ya que esta interactúa con la blockchain mediante transacciones.
- Cuentas de **contrato (Contract accounts or CA)**: estas están controladas por un código y solo pueden ser activada mediante una cuenta de propiedad externa. Este tipo de cuenta representan a un contrato inteligente.

### Tarifa de una transacción

Cada cuenta tiene un saldo de monedas. Un nodo participante puede enviar una transacción ya sea para la transferencia de Ether o para invocar un código de un contrato inteligente o ambos. Ambos tipos de transacciones requieren de **tarifa o honorarios**. Por lo tanto, una cuenta debe tener un saldo suficiente para cubrir las tarifas necesarias para que las transacciones sean activadas. Las tarifas se pagan en **Wei** que es una denominación más baja de **Éther**. En la imagen siguiente se ve la correspondencia:

![](/My-Blockchain-Book/images/Ether-Wei.PNG "Correspondencia Ether-Wei")

### Estructura de las transacciones

Una transacción en Ethereum incluye:
- El **destinatario** del mensaje
- La **firma digital** del remitente que autoriza la transferencia
- La **cantidad de Wei** a transferir
- Un campo de **datos opcional o una carga útil** que contiene un mensaje para un contrato inteligente
- **STARTGAS** que es un valor que representa el número máximo de pasos computacionales para la transacción
- **Precio del gas**, un valor que representa la tarifa que el remitente está dispuesto a pagar por los cálculos.

Veamos un ejemplo de una transacción en la red de Ethereum:

![](/My-Blockchain-Book/images/Ethereum-Transaction.PNG "Ejemplo de una transacción en Ethereum")

Podemos apreciar el hash de la transacción, la altura de la cadena, la marca de tiempo, las cuentas de origen y destino, cantidad transferida, el límite de gas, el gas utilizado, estado de la transacción (success en este caso) y nonce. Esta transacción en particular esta invocando a un contrato inteligente. Por supuesto, para la ejecución de un contrato inteligente se incurre en ciertas tarifas y la cantidad disponible es especificada por los diversos campos de gas en la transacción.

### Estructura de bloques

Los bloques en la cadena de Ethereum tienen una **cabecera**, ciertas **transacciones** y **runner-up headers**. Veamos cuales son los detalles de un bloque con el siguiente ejemplo:

![](/My-Blockchain-Book/images/Ethereum-Block.PNG "Ejemplo de un bloque en Ethereum")

Este es un bloque real de Ethereum a la altura 4446308. Vemos en la imagen la altura del bloque, la marca de tiempo, el hash de bloque, su hash anterior, dificultad y dificultad total, tamaño, gas utilizado, límite de gas, nonce y la recompensa de bloque.

## Operaciones en Ethereum

Para una simple transferencia de Ether en la blockchain de Ethereum, la cantidad a transferir y la dirección de destino se especifican junto con las tarifas o puntos de gas. El importe y las tasas se transfieren a sus respectivas cuentas. Veamos esto a tráves de un ejemplo:

![](/My-Blockchain-Book/images/Ethereum-Operation.PNG "Ejemplo de una operación en Ethereum")

En la imagen anterior, podemos ver una transacción de transferencia de 100 Ether entre las cuentas del remitente y del destinatario. Hay que tener en cuenta que además de esta transferencia, se pagan 21.000 puntos de gas al minero que agregó el bloque de transacción a la cadena de bloques.

### Nodo

Un **nodo** de Ethereum es un sistema computacional que representa una entidad empresarial o un participante individual. Un **nodo completo** de Ethereum aloja el software necesario para:
- El inicio de las transacciones
- Validación de las mismas
- Minería
- Creación de bloques
- Ejecución de contratos inteligentes
- La máquina virtual de Ethereum, EVM

### Ejecución de un contrato inteligente

![](/My-Blockchain-Book/images/Execution-SmartContract.PNG "Ejecución de un contrato inteligente")

Esta figura muestra la **implementación y invocación de un contrato inteligente**. Un contrato inteligente está diseñado, desarrollado, compilado e implementado en el EVM y estas pueden tener más de un contrato inteligente. Cuando la dirección de destino en una transacción es un contrato inteligente, el código de ejecución correspondiente al contrato inteligente se activa y ejecuta en el EVM. La entrada necesaria para su ejecución se extrae del campo de datos opcionales de la transacción.

El **estado actual** de un contrato son los valores de las variables que están definidas en él, pero este se puede actualizar mediante su ejecución. Los resultados de esta ejecución se guardan en los llamados **recibos**. Una cadena de bloques mantiene tanto el hash de estado como el de recibo.

### Transacciones

Todas las transacciones son **validadas**. Esta validación implica comprobar que la marca de tiempo y la combinación nonce sean válidas y la disponibilidad de honorarios o tarifas suficientes para la ejecución.

Los **nodos mineros** de la red reciben, verifican, recopilan y ejecutan transacciones. Además, el código de invocación de un contrato inteligente es ejecutado por todos los mineros. Posteriormente, las transacciones validadas se difunden y se recopilan para la creación de bloques. **El protocolo de consenso utilizado en la red de Ethereum es una prueba de trabajo basada en memoria en lugar de una CPU**. Pero... ¿Quién paga todas estas operaciones de validación, verificación y consenso? Lo vemos a continuación.

## Modelo incentivo en Ethereum

Recordemos que la **minería** es el proceso utilizado para proteger la red mediante la validación de los cálculos, la recopilación de ellos para formar un bloque, su verificación y difusión. **Ethereum también utiliza un modelo basado en incentivos para la creación de bloques**. A continuación procederemos a hablar sobre la estructura de tarifas y el modelo de incentivo en la red de Ethereum.

### Puntos de Gas (Transacción)
Cualquier accción en Ethereum requiere de **gas** y estos se utilizan para especificar las tarifas dentro de Ether. El **Ether**, como criptomoneda, varía su valor con las oscilaciones que se producen en el mercado, pero **los puntos de gas no varían**. Ethereum ha especificado puntos de gas para cada tipo de operación:

![](/My-Blockchain-Book/images/Gas-Fees.PNG "Tarifas o puntos de gas en Ethereum")

En el proceso de minería se calculan los puntos de gas necesarios para la ejecución de una transacción. Si la tarifa especificada y
el punto de gas en la transacción no son suficientes, se rechaza. Esto es similar a enviar una carta con franqueo insuficiente. La carta no se entregará si no tiene franqueo suficiente.

Los puntos de gas necesarios para la ejecución de una transacción **deben estar disponibles en el saldo de la cuenta** para que dicha ejecución se lleve a cabo. Si queda algún importe después de la ejecución de una transacción, esta se devuelve a la cuenta de origen.

### Puntos de Gas (Bloque)

Hasta ahora hemos hablado sobre el gas empleado en una transacción, ahora veamos el concepto de gas relacionado con un bloque.

#### Límite de gas y gas gastado

**Límite de gas** es la cantidad máxima de gas que un bloque podrá gastar. Por ejemplo, si un bloque especifica un límite de 1,5 millónes de unidades de gas, y una comisión básica de transacción de Ether es de 21.000, entonces en este bloque de Ethereum en particular pueden caber alrededor de 70 transacciones simples de Ether. Además, si agregamos en este bloque transacciones de contratos inteligentes, que por lo general requieren de mayor cantidad gas, entonces el número de transacciones para este bloque disminuirá.

El **gas gastado** es la cantidad real de gas gastada al finalizar la creación del bloque actual. 

### Modelo de incentivo minero

El minero que consiga resolver el puzle del "Proof of Work" será el encargado de crear el bloque nuevo en la blockchain. Todos los mineros que compiten para poder crear un nuevo bloque están incentivados con las **tarifas básicas de 3 Ethers** además de las **tarifas de una transacción en la red de Ethereum**. El minero ganador también recibe los honorarios, puntos de gas para la ejecución de una transacción de contrato inteligente.

Pero... pueden haber otros mineros que también resuelvan el rompecabezas o el puzle además del ganador. Estos mineros que también resolvieron el puzle pero no se ganaron el derecho para poder crear el bloque en la cadena son los llamados **Ommers**. Los bloques creados por ellos se llaman **Ommer Blocks** y estos se añaden como bloques Ommer, o bloques laterales, a la cadena principal. Además, estos mineros Ommer también obtienen un pequeño porcentaje del total de puntos de gas como consuelo y para la seguridad de la red.

![](/My-Blockchain-Book/images/Mining-Incentive-Model.PNG "Modelo de incentivo minero")

Resumiendo, cualquier transacción en Ethereum, incluida la transferencia de Ethers, requiere de tarifas o puntos de gas necesarios para ser especificados en las transacciones.Además, los mineros reciben honorarios o puntos de gas por seguridad, validación, ejecución de contratos inteligentes, así como por la creación de bloques. 

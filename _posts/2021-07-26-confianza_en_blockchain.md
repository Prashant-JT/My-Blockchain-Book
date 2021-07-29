# Confianza en la Blockchain 🇪🇸

Table of contents:

1. TOC
{:toc}

## Sistema Descentralizado

Vamos a intentar entender el concepto de **confianza** usando para ello un escenario cotidiano que se da en un **sistema centralizado**
como por ejemplo el sistema de un aeropuerto. Digamos que queremos volar desde el aeropuerto de Buffalo, para ello la autoridad
aeroportuaria habrá establecido previamente un entorno seguro para que las personas embarquen y desembarquen, esto establece la base de
confianza. Posterioemente la confianza aumenta una vez que has ingresado y tu pasaporte y documentos de viaje son verificados, validados
y tu equipaje ha sido revisado. Aún más confianza se genera cuando el personal de la aerolínea verifica su tarjeta de embarque en la
puerta de embarque y entran al avión para viajar.

Ahora, consideremos un **sistema descentralizado**. En este tipo de sistema no hay nadie que revise sus credenciales y certifique que son confiables. Entonces, ¿cómo lo hacen? Lo hacen usando los algoritmos y las técnicas discutidas en los posts anteriores.

### Confianza en sistemas descentralizados

De forma similar al escenario del aeropuerto, **la confianza en una cadena de bloques descentralizada se basa en**:

- Asegurar la cadena de bloques usando protocolos específicos
- Validar las transacciones y bloques para protegerse de las falsificaciones
- Verificar la disponibilidad de recursos necesarios para la ejecución de una transacción
- Y ejecutando y confirmando las transacciones

El proceso o el camino para generar confianza en una blockchain es el siguiente:
1. Se validan las transacciones
2. Se verifica el gas y los recursos necesarios
3. Se agrupan las transacciones para poder crear un bloque
4. Posteriormente se ejecutan las transacciones para obtener un nuevo estado
5. Se pasa a formar el nuevo bloque
6. Luego se trabaja para conseguir el consenso
7. Y finalmente todos agregan el bloque a su cadena local y confirman las transacciones

![](/My-Blockchain-Book/images/Trust-Trail.PNG "Proceso de confianza en blockchain")

Vamos a examinar cada uno de estos pasos a continuación:
- El ***paso uno*** valida la transacción y el ***dos*** comprueba los recursos. En el caso de un **Bitcoin**, hay acerca de 20 criterios que tienen que verificarse antes de validar una transacción. Similarmente en el caso de una transacción en **Ethereum**, la sintaxis, la firma de transacción, la hora, el nonce, el límite de gas, y el saldo de la cuenta del remitente se validan antes de la ejecución de la transacción. El gas, o puntos de gas, y otros recursos disponibles para la ejecución del contrato inteligente, también se validan junto con el hash y las firmas de la transacción.
- El ***paso tres*** es ejecutar las transacciones. Para ello en **Ethereum** se calcula el árbol merkle de las transacciones validadas y su raíz es situada en la cabecera del bloque (Transaction root). Todos los mineros ejecutan la transacción ya sea para transferir como para la ejecución de los contratos inteligentes. El estado resultante de dicha ejecución de la transacción es empleado para calcular el árbol merkle de los estados, cuya raíz se incluye en el encabezado de bloque (State root).

A continuación vamos a continuar hablando acerca del siguiente paso en la ruta de confianza, que es el **proceso de consenso**.

## Proceso de consenso

Una cadena segura es aquella cadena única que posee un **estado consistente**. Cada bloque que se valida, se suma al nivel de confianza de esta cadena.

Los mineros están compitiendo, para agregar su bloque a la cadena. Pero... ¿Qué pasa si todos los mineros quieren agregar su bloque candidato a la cadena? Hay que tener en cuenta que cada uno de los bloques candidatos pertenece a un minero competidor. Entonces, ¿Cuál es el siguiente bloque que se agregará a la cadena? ¿Pueden ponerse de acuerdo los mineros en el siguiente bloque a añadir? ¿Hay algún método o protocolo para elegir el siguiente bloque? Sí, lo hay. Se llama **Proof of Work** y también emplea la técnica de hashing que hemos comentado en anteriores post.

![](/My-Blockchain-Book/images/Consensus-Protocol.PNG "Proceso de consenso para añadir un nuevo bloque")

### Proof of Work en Bitcoin y Ethereum

Desde el punto de vista de un minero, que pretende añadir su bloque a la blockchain se sigue el siguiente proceso:
1. Se calcula el hash de los elementos de la cabecera del bloque, que es un valor fijo, junto con un nonce que es una variable
2. Si el valor hash es menor que 2^128 para **Bitcoin** o menor que la función de dificultad para **Ethereum**, entonces el rompecabezas o el puzle ha sido resuelto. En el caso contrario, se repite el proceso cambiando el valor nonce.

![](/My-Blockchain-Book/images/Proof-of-Work.PNG "Proof of Work en Bitcoin y Ethereum")

Si el reto o el puzle ha sido resuelto, se emite el bloque ganador por el minero que será verificado por otros mineros. Además, los nodos mineros no ganadores agregan este nuevo bloque a su copia local de la cadena y pasan a trabajar en el siguiente bloque que se añadira a la cadena.

![](/My-Blockchain-Book/images/Proof-of-Work-1.PNG "Proof of Work en Bitcoin y Ethereum")

El minero ganador recibe un incentivo por crear el bloque en la cadena. ***Proof of Work*** es un protocolo de consenso utilizado por la
blockchain de Bitcoin y también por la versión actual de Ethereum. El protocolo puede ser el mismo, pero las implementaciones en estas dos cadenas de bloques son diferentes. Muchos otros enfoques, como Proof of Stake, Proof of Elapsed Time, han sido propuestos. Este es un área muy debatida entre los desarrolladores de blockchain. 

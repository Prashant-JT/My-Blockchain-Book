# Algoritmos y Técnicas 🇪🇸
> Hoy en día se emplean dos técnicas para asegurar la blockchain y para una validación y verificación eficientes:
> **Hashing** y **cifrado de claves asimétricas**. Estas técnicas dependen de varios complejos algoritmos probados.
> En este post proporcionamos una visión de alto nivel de la aplicación de estos algoritmos, y el papel crítico que desempeñan
> estos en la seguridad de la cadena descentralizada.

Table of contents:

1. TOC
{:toc}

## Criptografía

Recordemos que los participantes de una red descentralizada, no necesariamente son conocidos entre sí. Las credenciales no se pueden verificar por medios convencionales, como por ejemplo, verificar quién es usted con su carnet de conducir. Además, los participantes pueden unirse y salir de la cadena cuando deseen, es decir, operan más allá de los límites de la confianza. Teniendo en cuenta este contexto: ¿Cómo identificamos a los participantes del mismo nivel o de la red? ¿ Cómo autorizamos y autenticamos las transacciones? ¿Cómo se detectan transacciones falsas o defectuosas? Podemos conseguir todas estas cosas empleando algoritmos de criptografía de clave pública que comentaremos a continuación. 

### Criptografía Simétrica o de Clave Secreta

En la criptografía de clave simétrica o cifrado simétrico  **la misma clave** se utiliza tanto para el **cifrado** como para el **descifrado**, es por ello que se le llama **clave simétrica**. Por ejemplo, en el cifrado simétrico de Cesar, que es el más simple ya que los alfabetos de un mensaje se desplazan por un número fijo, y este número en este caso se denomina **la clave**.

![](/My-Blockchain-Book/images/Cesar-Encryption.PNG "Cifrado simétrico de Cesar")

En este ejemplo "F" es una función definida por el desplazamiento del alfabeto en tres posiciones. Considera el ejemplo: «Meet me at the cinema». Por ejemplo, la letra M se sustituye por la P (desplazada en 3 posiciones) para poder cifrar y tu receptor lo descifra haciendo el proceso alreves. En este ejemplo, **el número tres es la clave**. Dado que la misma clave (el número 3 en el ejemplo) se utiliza para el cifrado y el descifrado, es una **clave simétrica o secreta**. Hay que tener en cuenta que la clave simétrica y las funciones de cifrado y descifrado suelen ser mucho más complejas en una aplicación real. Además, debemos tener en cuenta que esta clave secreta solo la conoceran el emisor y el receptor del mensaje.

Pero el cifrado simétrico presenta dos problemas graves:
- Es **fácil obtener la clave secreta** a partir de los datos cifrados
- La **distribución de claves**, ¿cómo le pasamos la clave al participante con el que queremos realizar transacciones? 

Estos problemas se pueden solucionar con la criptografía de clave pública.

### Criptografía Asimétrica o de Clave Pública

En lugar de una sola clave secreta, **emplea dos claves diferentes** que se ocupan de los problemas del cifrado de claves simétricas. Veamos esto a tráves de un ejemplo:

![](/My-Blockchain-Book/images/Public-Key-Cryptography.PNG "Claves Públicas y Privadas")

Supongamos, que **b** y **B** son los pares de clave privada y pública para un participante situado en Buffalo New York USA. Y que **k** y **K** son para un participante situado en Katmandú Nepal. La clave pública (B o K) se publica, la clave privada (b o k) se mantiene en seguro y bloqueada normalmente, por una contraseña. Estas dos claves funcionan de la siguiente manera:

> Un dato cifrado con la clave privada de un participante, por ejemplo con la clave privada **b**, solo puede ser descifrado con su correspondiente clave pública, es decir la clave pública **B** y viceversa.

Veamos un ejemplo muy común de cifrado asimétrico que nos permitirá autenticar tanto al remitente como al receptor:

![](/My-Blockchain-Book/images/Public-Key-Cryptography-1.PNG "Ejemplo de Cifrado Asimétrico")

Digamos que un participante en Buffalo quiere realizar transacciones con el participante en Katmandú. En lugar de enviar un mensaje simple, este participante en Buffalo enviará los datos de la transacción cifrados primero con la clave privada de Buffalo **b** (es decir con su clave privada), y luego cifrados por la clave pública de Katmandú **K**, que la dispondrá ya que dijimos que estas se publican.

![](/My-Blockchain-Book/images/Public-Key-Cryptography-2.PNG "Ejemplo de Cifrado Asimétrico")

El participante de Katmandú primero descifrará los datos utilizando su propia clave privada **k** y, a continuación, utilizará la clave pública de Buffalo **B** para descifrar los datos firmados de la transacción. Estos nos garantiza lo siguiente:
- Sólo el participante de Katmandú puede descifrar y recibir los datos cifrados, ya que solo el tiene la clave privada asociada a la clave pública B.
- Y que solo el participante de Bufalo puede haber enviado estos datos cifrados, ya que los datos habrán sido cifrados por la clave privada de Bufalo, clave privada b, que es el único que lo tiene.

#### Algoritmos de Cifrados Asimétricos: Rivest Shamir Adleman (RSA)

Una implementación popular de clave pública y clave privada es el algoritmo **Rivest Shamir Adleman (RSA)**. La aplicación más común de RSA es en la autenticación de usuario sin contraseña, por ejemplo para acceder a una máquina virtual en la nube de Amazon. Aunque RSA se usa muy comúnmente en muchas aplicaciones, las blockchain necesitan un algoritmo más eficiente y fuerte. La **eficiencia** es un requisito crítico ya que el par de claves públicas se utiliza con frecuencia en muchas operaciones diferentes en el protocolo de cadena de bloques.

#### Algoritmos de Cifrados Asimétricos: Criptografía de Curvas Elíptica (ECC)

La criptografía de curvas elípticas, o la familia de algoritmos ECC se utiliza en la blockchain de Bitcoin, así como en la de Ethereum para generar el par de claves pública y privada. Pero... ¿Porqué ECC y no RSA? ECC es más fuerte que RSA para un número dado de bits. Por ejemplo, ¿Sabías que el par de claves ECC de 256 bits es igual en fuerza a unos 3072 bits de par de claves de RSA? Tanto bitcoin como Ethereum utilizan algoritmos basados en ECC para sus necesidades de cifrado. 

## Hashing

**¿Por qué debemos aprender acerca de cifrado por hashes?** El par de claves privada y pública es como un pasaporte metafórico para participar en las transacciones en la blockchain. Por ejemplo, es similar a cómo aprendemos a usar una tarjeta de crédito, asegurarla y protegerla. Necesitamos **proteger nuestra clave privada** para la seguridad de nuestros activos en la blockchain. A continuación, aprenderemos el papel fundamental que juega **hashing** en la blockchain, y también en la **integridad de la transacción y confidencialidad de los datos**.

### ¿Qué es Hashing?

![](/My-Blockchain-Book/images/Hashing.PNG "Concepto de Hashing")

Una función de **hash o hashing** transforma y mapea una longitud arbitraria del valor de datos de entrada a un valor único de **longitud fija**. Los datos de entrada puede ser un documento, un árbol de datos o un bloque de datos. Además, **una ligera diferencia en los datos de entrada produciría un valor de salida de hash completamente diferente**.

Todas las funciones de hash deben cumplir con los dos siguientes requisitos:
- El algoritmo elegido para la función de hash debe ser una **función unidireccional**. Este requisito es para asegurar que nadie puede obtener el valor original de los datos de entrada (cifrada por la función de hash) a partir del valor de la función de hash. Por ejemplo, ¿Puedes hacer papas partiendo de un puré de papas?
- Y debe de ser **libre de colisión**, o tener muy baja probabilidad de colisión. Este requisito es para asegurar de que el valor de hash representa únicamente la información cifrada. Es decir, debe de haber muy baja probabilidad de que dos diferentes conjuntos de datos  de entrada se mapeen con el mismo valor de hash.

### Tamaño y funciones de hash

Los requisitos anteriores se cumplen al escoger un **algoritmo fuerte** como por ejemplo un hash seguro, y utilizando **gran número de bits** en el valor que se obtiene de la función de hash.

El tamaño de hash más común actualmente es de 256 bits y las funciones más comunes son **SHA-3, SHA-256 y Keccak**. Pero... ¿Qué tan bueno es el valor hash de 256 bits? Un espacio de valor de hash de 256 bits es, efectivamente, uno bastante grande. Es decir hay 2^256 posibles combinaciones de valores. Eso es aproximadamente 10^77. Incluso, las probabilidades de que un meteoro golpee nuestra casa son mas altas que generar dos valores de hash idénticos de 256 bits cuando se aplica este algoritmo.

Ahora precederemo a explorar algunas técnicas comunes de hash. Compararemos dos enfoques diferentes para cifrar según cómo estén organizados los elementos constitutivos: **simple hash o merkle tree hash**

### Hash Simple

![](/My-Blockchain-Book/images/Simple-Hash.PNG "Hash Simple")

En la imagen de arriba se muestra un ejemplo de **hashing simple** y con la operación de "SUMA" como la función de hash, en este caso.
Usaremos los datos de entrada 10, 4, 6, 21 y 19. En la actualidad, las funciones de hashing son mucho más complejas que la función de hash del ejemplo mencionado y normalmente son variaciones de SHA-3, y los valores de datos de sálida son mucho más grandes, principalmente valores de 256 a 512 bits. **En este enfoque hashing simple, todos los elementos de datos son linealmente ordenados y cifrados**.

### Hash de Árbol Merkle

![](/My-Blockchain-Book/images/Merkle-Tree-Hash.PNG "Merkle Tree Hash")

En el enfoque de hashing de un **árbol**, los datos estan situados en los nodos hoja del árbol y a las hojas de dicho árbol se le calcula el valor de hash por pares para llegar al mismo valor de hash que el hash simple.

Pero... **¿Cuándo se utiliza un Hash de Árbol Merkle? y ¿Cuándo se utiliza un Hash Simple?**
- **Hash Simple**: Cuando tenemos un número fijo de elementos a ser cifrados, como los elementos de la cabecera de un bloque y cuando estamos verificando la integridad del bloque y no la integridad del elemento por separado, utilizamos el hashing simple.
- **Hash Árbol Merkle**: Por ejemplo, cuando el número de elementos difiere entre bloques, como el número de transacciones, número de estados, número de recibos, entonces utilizamos una estructura de árbol para calcular el hash. Hay que tener en cuenta que, el estado es una variable que puede ser modificada por la ejecución de un contrato inteligente, y el resultado de dicha ejecución puede ser devuelto en un recibo (lo veremos en futuros posts). 

> Resumiendo, en Ethereum, las funciones de hash son utilizadas para generar direcciones de cuentas, firmas digitales, hash de las transacciones, hash de estados, hash de recibos y hash de encabezado de bloque. SHA-3, SHA-256, Keccak-256 son algunos de los algoritmos comúnmente utilizados para generar hashes en blockchains.

## Integridad de las Transacciones

Para gestionar la **integridad** de una transacción en la blockchain necesitamos:
- Asegurar una **dirección de cuenta única**. Es decir, un enfoque estándar para identificar de manera única a los participantes en la red descentralizada
- Autorización de una transacción por su remitente a través de la **firma digital**
- Verificación de que el contenido de una transacción no está modificado. 

Se utilizan una combinación de **hashing y criptografía de clave pública**, que mencionamos anteriormente, para resolver estos problemas.

### Obtención de Direcciones de Cuenta

Las direcciones de las cuentas se generan usando la pareja de claves pública y privada. Para ello se realizan los siguientes pasos:
1. Se genera un número aleatorio de 256 bits y se asigna como la clave privada de la cuenta que se debe mantener protegida por una contraseña.
2. Posteriormente, se aplica un algoritmo ECC a la clave privada, para obtener una clave pública única. A este paso ya tenemos el par de clave privada y pública.
3. A continuación, se aplica una función hash a la clave pública para obtener la dirección de la cuenta. Esta dirección es más corta en tamaño, solo 20 bytes o 160 bits.

Ahora que sabemos como se obtiene la dirección de la cuenta, veamos una transacción iniciada por esta dirección. Una transacción para transferir activos tendrá que ser: **autorizada, no repudiable e inmodificable**. Todo ello se logra a través de la **firma digital** que comentaremos a continuación.

### Firma Digital
Cuando los datos han sido pasados por una función de hash y posteriomente han sido cifrados con la clave privada del remitente, esto es lo que se conoce como **firma digital**. Cuando el receptor obtiene los datos originales y el hash seguro firmado digitalmente (hash de los datos + cifrado) este puede volver a calcular el hash de los datos originales recibidos y compararlo con el hash recibido para verificar la integridad del documento.

Veamos esto a través de un ejemplo sencillo. Considera que una transacción son esos datos que mencionabamos justo antes, entonces el proceso que se sigue es el siguiente:

Paso 1: Obtenemos el hash de los datos que están incluidos en la transacción.

![](/My-Blockchain-Book/images/Digital-Signature-1.PNG "Paso 1: Obtención del hash de la transacción")

Paso 2: Ciframos el hash obtenido con la clave privada del participante que esta generando la transacción. Esto es la **firmar digitalmente** la transacción para autorizar y hacer que la transacción no sea repudiable. 

![](/My-Blockchain-Book/images/Digital-Signature-2.PNG "Paso 2: Cifrado del hash de la transacción con la clave privada")

Paso 3: Este hash firmado se agrega a la transacción y puede ser verificado por otros participantes descifrando este hash seguro usando la clave pública del remitente de la transacción (que la deben tener), y volver a calcular el hash de la transacción.

![](/My-Blockchain-Book/images/Digital-Signature-3.PNG "Paso 3: Verificación del hash firmado")

Paso 4: A continuación, se compara el hash calculado por el receptor y el hash recibido en la firma digital. Si ambos coinciden pues se acepta la transacción en el caso contrario, se rechaza. Además, hay que tener en cuenta que para una verificación completa de la transacción, también se verifican la marca de tiempo, los "nonce", los saldos de la cuenta y la suficiencia de las tarifas. 

![](/My-Blockchain-Book/images/Digital-Signature-4.PNG "Paso 4: Verificación de la transacción")

## Seguridad de la blockchain

Algunos de los componentes principales de un bloque de Ethereum son:
- El encabezado
- Las transacciones, incluyendo el hash de la transacción o la raíz de transacción
- Y el estado, es decir, el hash de estado o la raíz de estado

### Integridad de un bloque

La **integridad de un bloque** en la blockchain se gestiona asegurando los siguientes conceptos:
- Que el contenido de la cabecera del bloque no se haya alterado
- Que las transacciones no se hayan alterado
- Y que las transiciones de estado se calculen eficientemente, se calcule su hash y se verifiquen

#### Hash del bloque

En Ethereum, el **hash de bloque** se calcula a partir de todos los elementos presentes en el encabezado del bloque, entre los que se incluyen el hash de la raíz de transacción y el hash de la raíz del estado. Este hash del bloque se calcula aplicando una variante del algoritmo SHA-3 llamado **Keccak** a todos los elementos del encabezado del bloque, como dijimos anteriormente.

![](/My-Blockchain-Book/images/Block-Hash.PNG "Elementos para el cálculo del hash de un bloque")

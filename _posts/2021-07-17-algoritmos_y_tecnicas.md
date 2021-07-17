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
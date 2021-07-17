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

### Criptografía de Clave Simétrica o Secreta

En la criptografía de clave simétrica o cifrado simétrico  **la misma clave** se utiliza tanto para el **cifrado** como para el **descifrado**, es por ello que se le llama **clave simétrica**. Por ejemplo, en el cifrado simétrico de Cesar, que es el más simple ya que los alfabetos de un mensaje se desplazan por un número fijo, y este número en este caso se denomina **la clave**.

![](/My-Blockchain-Book/images/Cesar-Encryption.PNG "Cifrado simétrico de Cesar")

En este ejemplo "F" es una función definida por el desplazamiento del alfabeto en tres posiciones. Considera el ejemplo: «Meet me at the cinema». Por ejemplo, la letra M se sustutiye por la P (desplazada en 3 posiciones) para poder cifrar y tu receptor lo descifra haciendo el proceso alreves. En este ejemplo, **el número tres es la clave**. Dado que la misma clave (número 3 en el ejemplo) se utiliza para el cifrado y el descifrado, es una clave simétrica. Hay que tener en cuenta que la clave simétrica y las funciones de cifrado y descifrado
suelen ser mucho más complejas en una aplicación real. 

Pero el cifrado simétrico presenta dos problemas graves:
- Es **fácil obtener la clave secreta** a partir de los datos cifrados
- La **distribución de claves**, ¿cómo le pasamos la clave al participante con el que queremos realizar transacciones? 

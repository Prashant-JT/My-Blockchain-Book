# Introducción a Bitcoin
Table of contents:

1. TOC
{:toc}

## Introducción

Las dos principales contribuciones de la criptomoneda Bitcoin son:
  1. Un sistema de moneda digital que funciona continuamente.
  2. Un modelo para la tecnología autónoma de aplicaciones descentralizadas llamada blockchain.

Alrededor de 2008, 2009, cuando las instituciones y mercados en los que confiábamos se desmoronaron, y todo el mundo estaba huyendo de Wall Street,
una persona misteriosa, o personas, llamada Satoshi Nakamoto, introdujo una nueva moneda digital, una criptomoneda llamada **Bitcoin**. 

| *Bitcoin habilitó una plataforma innovadora para la transferencia de valor entre pares sin ninguna autoridad central.* |
![](/My-Blockchain-Book/images/peer_to_peer.png "Transferencia de valor entre pares")

## Blockchain

Pero... Sin una autoridad central, ¿cómo proporciona Bitcoin confianza y seguridad? Pues mediante la implementación de programas de software para validación, verificación y consenso en una infraestructura novedosa llamada **blockchain**. Más adelante, alrededor de 2012, 2013, se añadieron elementos de computación a la infraestructura de la blockchain que abrió todo un mundo de posibilidades más allá de la simple transferencia de divisas.  

| * Blockchain se trata de habilitar transacciones peer to peer en una red descentralizada (trasnferencia de recursos digitales sin intermediarios) estableciendo la confianza entre pares o participantes desconocidos y registrando la transacción "en un libro digital" inmutable.* |

![](/My-Blockchain-Book/images/Intro-Blockchain.jpg "The Blockchain")

La cadena de bloques ha abarcado actualmente una amplia gama de aplicaciones en muchas industrias, incluyendo finanzas, salud, gobierno, fabricación y distribución.

## What is a decentralized network?

Consider a scenario where a customer wants to buy an item using his credit card. The intermediaries involved in accomplishing this task will be: 
- A credit card agency
- The customer's bank
- A credit card bank
- An exchange
- The merchant's bank
- The merchant

This is an example of a **centralized network** that we are all used to.
A **decentralized network** is a system where peers can transact directly with each other irrespective of where they are located. Functions of the intermediaries are shifted to the periphery to the peer participant in the blockchain infrastructure. Peers are not necessarily known to each other. 

![](/My-Blockchain-Book/images/Centralized-Decentralized.png "Centralized vs decentralized system")
[Click to read more about centralized and decentralized systems](https://medium.com/hackernoon/centralization-vs-decentralization-the-best-and-worst-of-both-worlds-7bfdd628ad09)

Now, how do we establish trust among the peers in such a decentralized system? By having a process in place to validate, verify, and confirm transactions. Record the transaction in a distributed ledger of blocks, create a tamper-proof record of blocks (chain of blocks) and implement a consensus protocol for agreement on the block to be added to the chain.

| *Validation, verification, consensus, and immutable recording lead to the trust and security of the blockchain* |

Let's see this in action: David leds Amy $10,000 (this is one single peer to peer transaction) and both make a note of it in a ledger (book). But, David is a cheater and he writes in his ledger that he lent Amy $12,000. Alternatively, Amy also changes her note from $10,000 to $1,000. So where is the trust?

To prevent this trust violation, we need to seek the help of people around, for example, Lisa, Allison, and Francis, providing all of them a valid copy of this ledger. This is the basic concept of an **immutable distributed ledger** defined in a blockchain process. 

In this scenario, they were all physically present in one location. Now imagine this to be an online transaction to an unknown peer. Also, scale up the one transaction to 10,000 transactions or about a million transactions. You should be able to transact with equal ease to any unknown peer in Australia, India or Albania. 
This is the tenet/principle of a decentralized system supported by blockchain. 

In the case just described, how do we trust our unknown peers? Through **verification and validation**. Amy requests Kevin to verify the amount David transacted with her. Kevin checks it and... oops, Kevin finds the amount of the transaction is not $10,000, but $300, so it's not valid. Kevin rejects and nullifies the transaction.

Similar to these, validation, then verification methods devised by the blockchain and implemented by the peers provide the collector trust needed in a decentralized system.  

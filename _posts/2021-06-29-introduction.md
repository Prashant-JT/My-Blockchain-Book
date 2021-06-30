# Introduction to Bitcoin
Table of contents:

1. TOC
{:toc}

## Introduction

Two major contributions of cryptocurrency Bitcoin are:
  1. A continuously working digital currency system
  2. A model for autonomous decentralized application technology called the blockchain.

Around 2008 & 2009, when the institutions and markets we trusted went crumbling down, and everybody was running away from the Wall Street, a mysterious person, or persons, called Satoshi Nakamoto, introduced a new digital currency, a cryptocurrency called **Bitcoin**. 

> *Bitcoin enabled an innovative platform for peer to peer transfer of value without any central authority*

## The Blockchain

But... With no central authority, how did Bitcoin realize trust and security? By implementing software programs for validation, verification, consensus in a novel infrastructure called the **blockchain**. 
Later on in about 2012 & 2013, computation elements were added to the blockchain infrastructure that has opened up a whole world of possibilities beyond simple currency transfer.

> Blockchain is about enabling peer to peer transaction in a decentralized network (transfer of digital assets without any intermediaries), establishing trust among unknown peers (a collective trust model) and recording the transaction in an immutable distributed ledger

![](/My-Blockchain-Book/images/Intro-Blockchain.jpg "The Blockchain")

The blockchain by itself has taken a life of its own and permeated a broad range of applications across many industries, including finance, healthcare, government, manufacturing, and distribution. 


### What is a decentralized network?

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

> *Validation, verification, consensus, and immutable recording lead to the trust and security of the blockchain*

Let's see this in action: David leds Amy $10,000 (this is one single peer to peer transaction) and both make a note of it in a ledger (book). But, David is a cheater and he writes in his ledger that he lent Amy $12,000. Alternatively, Amy also changes her note from $10,000 to $1,000. So where is the trust?

To prevent this trust violation, we need to seek the help of people around, for example, Lisa, Allison, and Francis, providing all of them a valid copy of this ledger. This is the basic concept of an **immutable distributed ledger** defined in a blockchain process. 

In this scenario, they were all physically present in one location. Now imagine this to be an online transaction to an unknown peer. Also, scale up the one transaction to 10,000 transactions or about a million transactions. You should be able to transact with equal ease to any unknown peer in Australia, India or Albania. 
This is the tenet/principle of a decentralized system supported by blockchain. 

In the case just described, how do we trust our unknown peers? Through **verification and validation**. Amy requests Kevin to verify the amount David transacted with her. Kevin checks it and... oops, Kevin finds the amount of the transaction is not $10,000, but $300, so it's not valid. Kevin rejects and nullifies the transaction.

Similar to these, validation, then verification methods devised by the blockchain and implemented by the peers provide the collector trust needed in a decentralized system.  

### Blockchain Structure

Transaction is the basic element of the Bitcoin Blockchain.
1. Transactions are validated and broadcast.
2. Many transactions form a block.
3. Many blocks form a chain through a digital data link.
4. Blocks go through a consensus process, to select the next block that will be added to the chain. 
5. Chosen block is verified, and added to the current chain. 
6. Validation and consensus process are carried out by special peer nodes called miners. These are powerful computers executing software defined by the blockchain protocol.

### Bitcoin transaction

Let's discuss the details of a single transaction in bitcoin.

#### UTXO

A fundamental concept of a bitcoin network is an **Unspent Transaction Output** (UTXO). The set of all UTXOs in a bitcoin network collectively defined the state of the Bitcoin Blockchain. 

![](/My-Blockchain-Book/images/UTXO.PNG "UTXO's are referenced as inputs in a transaction. UTXO's those are also outputs generated by a transaction. All of that UTXO's is in a system, are stored by the participant nodes in a database.") 

[Click to read more about UTXO (in Spanish)](https://academy.bit2me.com/que-es-una-utxo/)

Now let's review the role of the UTXO's in a Bitcoin Blockchain: the transaction uses the amount specified by one or more UTXOs and transmits it to one or more newly created output UTXOs, according to the request initiated by the sender. A structure of a given UTXO includes:
- A unique identifier of the transaction that created this UTXO
- An index or the position of the UTXO in the transaction output list
- A value or the amount it is good for
- Optional: conditions under which the output can be spent 

#### Transaction

The transaction itself includes:
- A reference number of the current transaction
- References to one or more input UTXOs
- References to one or more output UTXOs newly generated by the current transaction
- Total input amount and output amount

Let's see an example of a transaction:

![](/My-Blockchain-Book/images/Transaction-Number.PNG "Transaction number") 

There are three input UTXOs referenced and an arrow points to the references of the two output UTXOs:

![](/My-Blockchain-Book/images/Input-UTXO.PNG "Input UTXOs") 
![](/My-Blockchain-Book/images/Output-UTXO.PNG "Output UTXOs") 

Note that there are three input UTXOs and only two output UTXOs. This means that the total amount in three input UTXOs are spent to generate two new output UTXOs. Below the output UTXOs is a total amount transferred in the Bitcoin value:

![](/My-Blockchain-Book/images/BTC-total-value.PNG "Total amount transferred in Bitcoin value") 

#### Block

A block is composed of a header of information about the block, and a set of valid transaction. 

![](/My-Blockchain-Book/images/Block-header.PNG "Header of information")

This is the genesis block. Satoshi Nakamoto initiated the Bitcoin Blockchain with one transaction of 50 BTC. The data the Blockchain creation is January third, 2009.
There was no previous block so the *Previous Block* field is all zeros. It also list a block reward or minus fees of 50 BTC. We'll discuss minus reward in a later blog.

![](/My-Blockchain-Book/images/Block-transaction.PNG "Set of valid transaction")

Now, let's look at the structure of the Blockchain by peeking into the Bitcoin Blockchain. Our goal is to understand the link between the blocks.
Let's consider the chain of three blocks: #488867, #488868 and #488869. 

![](/My-Blockchain-Book/images/Block-link.PNG "Blocks #488867, #488868 and #488869")

#488868 shown in the middle, has the hash of #488867 as its previous hash. The block #488869 has the hash of #488868 as its previous hash, forming the links in the chain.

To summarize, transaction bring about transfer of value in the Bitcoin Blockchain. The concept of UTXO defines the inputs and outputs of such a transaction.
Once a block is verified an algorithmically agreed upon by the miners, it is added to the chain of blocks, called the Blockchain. 

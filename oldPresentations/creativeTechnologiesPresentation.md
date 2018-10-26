# Blockchain Technology and the Internet of Things

by Steve Huckle

![](images/bitcoin.png)

_Source: bitcoin.org_

- - -

## Presentation Objectives

> 1. Give a brief history of blockchain technology
> 2. Provide an overview of blockchain Design
> 3. Look at blockchain types
> 4. Draw some conclusions about possible future directions of blockchain technology

# Blockchain History

![](images/silk_road.png)

_Source: dev1.ryot.org_

- - -

## A Timeline of Blockchain Technology

> + Blockchain technology, in the form of Bitcoin, began life on 31st October 2008, with the publication of a [2008 white paper by Satoshi Nakamoto](https://bitcoin.org/bitcoin.pdf "Bitcoin White Paper")
> + The first transaction of Bitcoin, in block 170, took place On 12th January 2009
> + On 6th February 2010, the first Bitcoin currency exchange was established
> + On 22nd May 2010, the first real-world transaction took place when the Jacksonville programer Laszlo Hanyecz paid 10,000 Bitcoin for a pizza

## A Timeline of Blockchain Technology (cont'd)

> + The notorious online Bitcoin marketplace, Silk Road, known as the ‘eBay for drugs’, opened its doors for business in early 2011. The FBI finally shut the service down in October 2013
> + On 6th December 2012, Bitcoin Central becomes the first Bitcoin exchange to be licensed as a European bank
> + On 2nd May 2013, the world’s first Bitcoin ATM is unveiled in San Diego, California
> + Ripple Labs is incorporated on 26th September 2013. It immediately issues a release of its open source software; **blockchain technology** designed to enable seamless currency transfers.

## A Timeline of Blockchain Technology (cont'd)

> + On 18th November 2013, The U.S. Senate Committee on Homeland Security and Governmental Affairs hold a hearing, discussing Bitcoin, called “Beyond Silk Road: Potential Risks, Threats, and Promises of Virtual Currencies”
> + In September 2014, the U.S. Commodity Futures Trading Commission become the first U.S. regulatory agency to approve a Bitcoin financial product
> + On 11th May 2015, Nasdaq launches a blockchain initiative with the aim of enhancing its equity management capabilities

## A Timeline of Blockchain Technology (cont'd)

> + 30th July 2015, saw the first live release of the Ethereum project, a smart contract platform based on blockchain technology
> + On 17th December 2015, The Linux Foundation announced a collaborative effort to “develop an enterprise grade, open source distributed ledger framework.” There are thirty founding corporates collaborating on the project, including companies such as **The London Stock Exchange Group**, **JP Morgan**, **Deutsch Börse**, and **ANZ Bank**
> + On 17th February 2016, IBM release a white paper on their Open Blockchain Initiative
> + [Blockstars.io](https://www.blockstars.io/ecosystem/) currently lists 267 blockchain based projects on its _"blockchain ecosystem"_

## The Blockchain Eco-System

![](images/BlockchainEcoSystem.png)

_Source: Blockstars.io_


# Blockchain Design

![](images/BTCNetwork.png)

_Source: The IMF_

- - -

## Blockchain Transactions

![](images/BTCTransactions.png)

_Source: [Bitcoin: A Peer-to-Peer Electronic Cash System by Satoshi Nakamoto](https://bitcoin.org/bitcoin.pdf "Bitcoin White Paper")_

## The Blockchain As a State Transition System

Given an original state **S**, a transaction **TX**, and a new state **S'**, we have:

	APPLY(S,TX) -> S’ or ERROR

Algorithmically, each transaction is a function that takes a state consisting of the collection of all unspent transaction outputs (UTXO) that are changed to a different state in the  form of new UTXO:

	For each input in TX:
		If the referenced UTXO is not in S:
			return ERROR.
     		else if the cryptographic signature does not match
			the owner of the UTXO: 					
				return ERROR.
    		else if the sum of all input UTXO is less than the
			sum of all output UTXO:
				return ERROR.
    		else:
				remove all input UTXO.
				add all output UTXO.
		return S'.

## Valid Blockchain Transactions

1. **Authorised**: They should be authorised so that only _user x_ can perform
transactions under the guise of _user x_. This is achieved through public key cryptography
2. **Read-only**: Once on the system, transactions cannot be modified. Again, achieved through cryptography
3. **Final**: Transactions cannot be deleted. The time stamping and hashing functions of workers on the blockchain network help ensure finality
4. **Uncensored**: As long as the transaction conforms to the blockchain’s protocol,
it should be added to the ledger.
5. **Consistent** : Conformance to the present state of the blockchain is achieved by encoding transactions into a time-stamped Merkle Tree.

## Validating Transactions

A fundamental concept of blockchain technologies is that validators must prove that they've completed _something difficult_.

## Overview of the Validation Process

Bitcoin validates transactions using **Proof of Work** (PoW) consensus. That's a scheme based on a **SHA-256** hashing algorithm, which produces a hash with a value less than a target **nonce**. Calculating the hash, known as **mining**, takes approximately ten minutes.

. . .

The validation process produces a block that contains a **timestamp**, a **nonce** and the root hash of a **Merkle Tree** of all transactions for that block.

. . .

Finally, the block is broadcast so that network nodes can decide on its validity.

![](images/PooledMining.png)

_Source: bitcoin.org_

## Bitcoin Consensus

_Satoshi Nakamoto_, in the [original Bitcoin white paper](https://bitcoin.org/bitcoin.pdf "Bitcoin White Paper"), describes the consensus process by which the blockchain is formed:

1. All nodes receive a broadcast of new transactions.
2. Each node collects new transactions into a block.
3. Each node (miner) tries to find a PoW for its block.
4. When a node finds a PoW, it broadcasts the new block to all nodes.
5. Nodes accept the block only if all of the transactions it contains are valid.
They must not have been spent already.
6. Nodes express their acceptance of the block by working on creating the
next block.
7. Nodes use the hash of the accepted block as the previous hash (thus forming
the chain).

## The Blockchain

![](images/LongestChain.png)

_Source: [Bitcoin: A Peer-to-Peer Electronic Cash System by Satoshi Nakamoto](https://bitcoin.org/bitcoin.pdf "Bitcoin White Paper")_

## Summarising Blockchain Design

_Jonathan Chester_, writing in [Forbes Magazine](http://www.forbes.com/sites/jonathanchester/2016/04/14/the-blockchain-wars-how-startups-and-enterprises-are-competing-to-create-the-web-2-0/), says this:

_"Think of the blockchain as a spool of Kevlar tape kept in the middle of the town square, and consensus about a block is equivalent to writing on the tape with indelible ink."_

. . .

A blockchain represents an irrevocable representation of the truth because it's a permanent and complete record of every transaction that’s ever taken place.

. . .

The [Bitcoin Website FAQ](https://bitcoin.org/en/faq) puts it this way:

_"Blockchains are the most prominent **triple entry bookkeeping system** in existence."_





# Types of Blockchain

![](images/Decentralised.png)

_Source: Bitnation_

- - -

## Overview of Blockchain Types

There are, essentially, three types of blockchain:

1. Public
2. Consortium
3. Private

## Public Blockchains

Public blockchains are most often _permissionless_ because they have no read or write restrictions:

> + Fully decentralised ledger readable by all participants
> + Any node can take part in the consensus process for block addition and transaction verification

## Consortium Blockchains

Vitalik Buterin, the founder of [Ethereum](https://www.ethereum.org/), describes [consortium blockchains](https://blog.ethereum.org/2015/08/07/on-public-and-private-blockchains/) as _"partially decentralised"_. These are often permissioned:

> + A limited set of nodes will participate in the consensus process
> + However, the ledger may be readable by all nodes
> + [Ripple](https://ripple.com/) is perhaps the best example of a consortium blockchain

## Private Blockchains

Private blockchains resemble a centralised system with an infusion of cryptographic audit-ability. They are _permissioned_ because they grant access only to a predefined list of entities:

> + Write permissions are centralised
> + Read permissions may be partially restricted

## Comparative Analysis

![](images/DegreesofCentralisation.png)

_Source: UK Government Office for Science_


# Conclusion

![](images/TheEconomistCoverOctober31st2015.jpeg)

_Source: The Economist Front Cover, 31st October 2015_

- - -

## The Impact of Blockchain Technology

_"At the very least, blockchain technology could provide an economic layer for the Internet, allowing for seamless asset transfer and contract exchange on a much larger scale than has hitherto been possible."_

_Swan: Blockchain: Blueprint for a New Economy_

## Unexpected Uses

_"Any tool should be useful in the expected way, but a truly great tool lends itself to uses you never expected."_

_Eric S. Raymond: The Cathedral and the Bazaar_

## Blockchain Classes

**1.0**: The cryptocurrency class - [Bitcoin](https://bitcoin.org/en/).

. . .

**2.0**: The provenance class - market services, such as bond trading, deed transfer, or smart contracts - [Ethereum](https://www.ethereum.org/).

. . .

**3.0**: Classes beyond finance - health, science, arts or culture.

## Blockchain Technology and the Internet of Things (IoT)

Blockchain technology could become the backbone of the Internet of Things, able to track device history and allowing smart systems to become autonomous agents.

. . .

Imagine an electricity metre which records energy use on a blockchain that forms a contract with the supplier, thus automating billing. Furthermore, the blockchain can regulate consumption; for instance, it delays turning on devices, such as a washing machine, until the sun is shining and the solar panels on the roof are generating the most energy.

. . .

Now imagine Performing Rights Management based on blockchain technology, where each play of a piece of music records an entry on a ledger that triggers a payment to the artist concerned.

# Thank You

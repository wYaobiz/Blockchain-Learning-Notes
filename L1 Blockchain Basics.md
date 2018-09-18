# L1 Blockchain Basics

![](L1%20Blockchain%20Basics/A052AA32-65B8-4376-9686-F02473CF78EC.png)

## Hashing 
### Hashing Overview 
**Hash Value**
A digital fingerprint for information. It’s a unique string of letters and numbers that represent a set of data. 

**Hashing Function**
Maps a group of data to a unique hash value. It will take in the information you give it and create a completely unique hash value. 

![](L1%20Blockchain%20Basics/24C190BD-C136-4584-AA4A-71E0D16ABDA4.png)

Bitcoin uses SHA256 to create a unique hash value for each block on the blockchain. The reason for this is to create a unique identifier for every block chat exists on the chain.  

## Blocks
### Blocks Overview 
**Block**
A block is a container that holds a list of transactions to be added to the blockchain. 
**Blockchain**
Shared digital ledger that records a list of transactions. It is containing a list of all records that happen throughout the network. 
**Block Header**
- Previous Blocks Hash: the hash value for the block that comes directly before the given block in the chain. 
- Time: the time of block was created. We know exactly when each block was made. That helps us know when certain transactions took place and can help us catch things like when someone may have tried to spend the same money twice. With this information, we can decide which transactions were based on which happened first. This timestamp is the blockchain solution to the double-spending problem. 
- Merkle Root: a hash that represent every transaction inside the block. 
- Nonce: An arbitrary number that can only be used once. 
- Block size: the amount of space a block has to hold information. 

## Blockchain 
The blockchain is specifically the place where data is stored. 
### Blockchain Overview
**Blockchain**
Digital ledger that contains the entire history of transactions made on the network. It’s an accumulation of linked blocks joined together by hash values that have been created over time. 
All information on a Blockchain is permanent and can’t be changed. This means that the data is immutable. 
When using blockchain, you have a permanent unchanging history of information, which is useful for many different applications. 
To construct a Blockchain, you need two main things, blocks and hash values. 

To construct a Blockchain, we need two main things, blocks and hash values. 
![](L1%20Blockchain%20Basics/CD97D809-4447-445E-BFE7-0A6EC856F1EF.png)

Every block contains its own hash plus the hash of the previous block. These hash values chain the blocks together in order from recent block made all the  way to the first block ever created. The fact that these blocks are connected by hash values gives them some pretty interesting qualities. 

![](L1%20Blockchain%20Basics/361EA56A-56A1-41F4-8998-E26B0F248C4D.png)
![](L1%20Blockchain%20Basics/8322463C-6675-4474-8E21-D49BE7B660A9.png)


If we change the data on a block that it will create a new hash value for that block.  That will invalidate the block and we’ll know it’s been changed.  If we look into what happened to the blockchain, it also changes the hash for this block that exists on the next block.  This changes the data in that block changing the hash value, and now this gets invalidated too. 
![](L1%20Blockchain%20Basics/268FDBA3-7361-4E39-A009-1F31C7C82146.png)
![](L1%20Blockchain%20Basics/FADC663E-AFB8-4122-A3A9-CA238199C509.png)
![](L1%20Blockchain%20Basics/F221F583-8BF5-448B-A2BA-67C9187A7E11.png)
The set of blocks effectively breaking the entire chain. 

We can identify any block on the chain by where it is located using its block number. 

**Block Number**
The block number is just the umber for where on the chain that block falls. The third block will have a block number three, and the first block will be called block number one. It also goes by another name, the genesis block.  
![](L1%20Blockchain%20Basics/FFACF8CC-AF03-4985-A3DB-BC914F21D05C.png)

## Distributed Peer-to-Peer Network 
The blockchain is supported by a network more specifically known as a distributed peer-to-peer network. 

**Peer-to-Peer Network**
A network of computers that allows information to be shared across users.
It allows uses known as node to send information directly 

**Distributed Network**
A network that allows information to spread out across many users. 

![](L1%20Blockchain%20Basics/D2D5CE8F-9DE5-48FB-8B28-765639741436.png)

In a distributed system, everyone gets a copy of the information with the same access and control as anyone else. There’s no centralization of the information at all.  This gives everyone equal access to whatever information that they need. 

For Blockchain, on a distributed network. Everyone downloads a copy of the blockchain to their local computer. They interact with this copy of the blockchain and have full access to all the information it contains. 

![](L1%20Blockchain%20Basics/A773CDBB-401B-4FCC-B744-E2A39D467683.png)


## Memory Pool 
The **memory pool** is the waiting place for transactions before they enter the blockchain. The blockchain can only handle so much information at once, and the backlog of information goes here.

A transaction would leave the memory pool if:
- The transaction expired by timeout (by default 14 days after entering).
- The transaction was at the bottom of the memory pool  (when sorted by fee per size), the memory pool had reached its size limit, and a new higher-fee transaction was accepted, evicting the transaction at the bottom. 
- The transaction was included in a block. 
- The transaction or on of its unconfirmed ancestors conflicts with a transaction that was included in a block. 


## Consensus
**Consensus** is how the blockchain makes decisions. Basically consensus is an idea, but the idea is implemented through many different algorithms. These algorithms are all different ways to try and achieve consensus more effectively. Things like **proof of work**, **proof of stake**,  **DBFT**. 

**Consensus**
How the network reaches agreement about which transaction are most trustworthy. Or we can say, it is the name for a group of algorithms we can use to create a voting process for the network. This voting process helps make decisions about information on the blockchain. 

**Byzantine Generals’ Problem**
This challenge has been around for a while - achieving consensus in a distributed system with suboptimal communication between participants who do not necessarily trust each other isn’t new.

## Proof of Work 
### Proof of Work (PoW)
Bitcoin use PoW to solve the consensus. 

### How Does it Work?
PoW involves miner nodes, or miners, to solve a math puzzle that requires a lot of computation power. Whichever miner is able to solve the puzzle the fastest is able to add a block of transactions to the blockchain, and in return, they are paid the transaction fees from all the transactions included in the block as well as paid by the network with bitcoins that were newly created upon the “mining” of the block.

### Potential Issues
2 Commonly discussed issues with Proof of Work are:
1. Extremely High-Energy Consumption 
2. A Monopoloy of Miners which Leads to a Concern for System Centralizations

## Proof of Stake 
In the Proof-of-Stake Consensus Protocol, there are no more miners; instead, there are Validators. These validators, or stakeholders, determine which block makes it onto the blockchain. In order to validate transactions and create blocks, validators put up their own coins as “stake”. Think of it as placing a bet - if they validate a fraudulent transaction, they lose their holdings as well as their rights to participate as a validator in the future. In theory, this check incentivizes the system to validate only truthful transactions.

### Potential Issues
“Nothing At Stake” problem in which a bad acting Validator places bets on multiple forks so they theoretically always win out in the end.

![](L1%20Blockchain%20Basics/4D10ABFD-7FC1-42AB-8BE4-4C7BD55A7E1A.png)

### Proposed Solutions 
**Slasher** Strategy which entails penalizing validators if they simultaneously create blocks on multiple chains.

![](L1%20Blockchain%20Basics/37369BC4-95A1-492C-A4AE-2B6FE6F9BA49.png)

Additionally there’s the **Punisher** Strategy which simply punishes validators for creating blocks on the wrong chain. In this method, Validators will be motivated to be selective and conscious about the blockchain in which they put their stake.

![](L1%20Blockchain%20Basics/13AE7F11-7037-4CE1-AF9F-FF206C2A5EDC.png)

### Who’s Using It? 
Ethereum, DASH, and LISK. 


## Delegated Byzantine Fault Tolerance (dBFT)
dBFT uses a system similar to a democracy where Ordinary Nodes the system vote on representative Delegate Nodes to decide which blocks should be added to the blockchain. When it’s time to add a block, a Speaker is randomly assigned from the group of Delegates to create a new block and propose the new block. 66.66% of delegates need to approve on the block for it to pass.

### Potential Issues
- **Dishonest Speaker**
There is always a chance the Speaker, who is randomly selected from the Delegates, could be dishonest or malfunction. In this situation, the network needs to rely on honest delegates to vote the proposed block down so it doesn’t reach 66% approval. It is up to users of protocol who vote on Delegates, to find out which delegates are not trustworthy and vote on other delegates that are truthful.
- **Dishonest Delegate**
In this case, the chosen Speaker is honest but there are Dishonest Delegates in the system meaning even if they receive a proposal for new block that is faulty, they can say it is valid. If it is a minority of delegates that are dishonest, the block will not make it and new speaker is elected.

### Who’s Using it?
NEO 


# L2 Blockchain Transaction
## Blockchain Identity 
 A Bitcoin Wallet:
- **Private Key**: A secret number that allows you to spend your bitcoin from your wallet.  There are randomly generated number that your wallet creates. Wallet contains one or more these private keys and these should not be shared with anyone. 
- **Public Key**: A public key is derived from your private key and gives you a publicly shareable key that cannot be used to spend bitcoin, you can share with anyone, they can use it for send you bitcoin. 
- **Wallet Address**: A unique identifier for your wallet. 
Wallet Address is public to see for everyone, we use wallet address in the transaction details. 
![](L2%20Blockchain%20Transaction/785FB847-830C-419A-82B7-E207D538F86B.png)

We can share our public key without worrying about the security of our private key. The private key has to been linked with a public key, so that the private key can track the public key. 
![](L2%20Blockchain%20Transaction/C2695F85-A94F-492B-BBC6-5D834519C732.png)

Use ECDSA (Elliptic Curve Digital Signature Algorithm) algorithm: 
![](L2%20Blockchain%20Transaction/EC800B5E-5087-4D36-BBA7-932D5DB0A27C.png)

We run SHA-256 and RIPEMD160, for generating Wallet address by public key, the 160 bit number is the Wallet Address: 
![](L2%20Blockchain%20Transaction/CB3B9E17-E101-4250-95B5-7ADDD392ADB9.png)


![](L2%20Blockchain%20Transaction/975FB6E1-E3EB-4190-9DF3-467C2C1B8C22.png)

We use BASE50CHECK algorithm to take the 0 or O, to get the shorter Base58 number Wallet Address. 
![](L2%20Blockchain%20Transaction/4A721F4F-117E-4066-BF4D-4EC811402B1C.png)

The finally shareable wallet address is the one based on Base50 number. 
![](L2%20Blockchain%20Transaction/D6F311AB-DB40-469B-BE74-C875E7C01A65.png)


### Wallet Overview 
![](L2%20Blockchain%20Transaction/BAC64D24-9DD5-4898-818F-70CAFB0030D2.png)

**Deterministic wallet** 
![](L2%20Blockchain%20Transaction/ADA32A5F-3A12-4A72-812B-8B9774022575.png)

**Hierarchical Deterministic wallet**
![](L2%20Blockchain%20Transaction/BC6F4CDD-CB19-4DEC-9624-781B72ABC371.png)

**Non-deterministic Wallet**
(random wallets) A wallet where private keys are generated from random numbers.

**Deterministic Wallet**
A wallet where addresses, private keys, and public keys can be traced back to their original seed words.

**Hierarchical Deterministic Wallet**
An advanced type of deterministic wallet that contains keys derived in a tree structure. 

## Wallet Types 
**Non-deterministic Wallet**
![](L2%20Blockchain%20Transaction/C6EDC878-E6EF-4F0E-957C-1C67B030CF88.png)
All the private keys are generated from random numbers, cannot be traced back to the original random numbers unless you backup it. 
All the private keys are randomly generated, that have no association with each other. 

**Deterministic Wallet**
All the private keys, and public keys can be traced back to the original seed.  Nothing is random, they can be determined. 

![](L2%20Blockchain%20Transaction/FCC890DE-DD9A-4D24-882F-E66FAB268CEE.png)
 
HD wallets came about in the Bitcoin Improvement Proposal 32 also known as BIP32 and that’s viewable online in the BIP32 GitHub repo. 
![](L2%20Blockchain%20Transaction/7A0B58AF-013A-4F14-82CE-415F5CCDA017.png)
![](L2%20Blockchain%20Transaction/B542829A-12F0-484D-8EA7-42D20ACB5F98.png)
The Master Key needs strong backup. 


## Private Keys 
A private key is just a 256-bit random number between 1 and 2^256. 

Different Formats:
![](L2%20Blockchain%20Transaction/82445E23-7EC8-4011-AB04-B0211BE2DB52.png)

**Def: Entropy** 
Lack of order or predictability. It’s the degree of disorder or randomness in the system. 

**What’s the purpose of a Private Key**
Private keys generate Public Keys and Wallet Address that allow us to interact with the blockchain 

**What makes a Private Key secure?**
A Private Key is a 256-bit random number between 1 and 2^256

**How to generate a Private Key?**
- Paper, pencil, coin, dice
- OS with source of entropy or library with cryptographic secure number generator 
- Bitcoin address generating websites 
- Software wallets 


## Restoring Blockchain Identity 
**Ways to Restore a Wallet**
- Use a seed 
- Use a Private Key 
	1. Import a Private Key 
	2. Sweep a Private Key 

## Sign a Transaction 
**Signature**
Establishes proof of ownership for each transaction on the blockchain 
A valid transaction, the sender must sign it before sending the transaction by using his private key, with the private key, the sender can sign his transaction with his digital signature. 

In Bitcoin, the transaction message is broadcasted to the chain as an unspent transaction output known as UTXO. 

Each transaction input has a condition.  The transaction input will need to be converted to an output which contains the condition to prove ownership using your private key. 

With your private key, you can sign your transaction with your digital signature proving you own the address containing the transaction inputs. 

To create a transaction output you need to have the sum of the input transactions which are equal to, or, greater than the value you are sending. 


![](L2%20Blockchain%20Transaction/B58866E7-3F19-47CA-B17D-0D0514EA571C.png)

![](L2%20Blockchain%20Transaction/76CF248C-F6F6-4F3C-BD56-DFAF38E93460.png)


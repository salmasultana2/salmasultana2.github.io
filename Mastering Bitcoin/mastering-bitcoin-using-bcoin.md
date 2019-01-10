---
layout: default
---

# Mastering Bitcoin Examples using Bcoin

In this post, we are rewriting some of the examples from the book [Mastering Bitcoin](https://github.com/bitcoinbook/bitcoinbook) by Andreas Antonopoulos using Javascript. Most of these programs require a bitcoin library to execute and for that we will use [bcoin](https://bcoin.io/). For string encodings, we will use [bstring](https://www.npmjs.com/package/bstring) and for cryptographic hash functions, we will use [bcrypto](https://www.npmjs.com/package/bcrypto).


### bcoin functions used

1. `bcoin.HDPrivateKey.generate()` - generates an object containing private key, public key, and other attributes.
2. `bcoin.Address.fromScripthash()` - returns an address from a script hash.
3. `bcoin.Script.fromAddress()` - returns a script from a base58 encoded bitcoin address.
4. `bcoin.util.revHex()` - returns the reverse of a hex string.

### bcrypto functions used

1. `bcrypto.RIPEMD160.digest()` - returns the RIPEMD160 cryptographic hash. 
2. `bcrypto.SHA256.digest()` - returns the SHA256 cryptographic hash.

### bstring functions used

1. `base58.encode()` - encodes a string into base58 format. 

## Overview

1. [addr.js](./addr.html) - to generate a base58 encoded bitcoin address.

2. [extract-from-pk-script.js](./extract-from-pk-script.html) - extracts a P2SH address from a pubKey script.

3. [get-block.js](./get-block.html)* - displays the information of a block specified via it's blockHeight.

4. [get-utxo.js](./get-utxo.html)* - displays the unspent transaction outputs of an address.

5. [hash-example.js](./hash-example.html) - finds a phrase that produces a hexadecimal starting with a zero.

6. [key-to-address-ecc](./key-to-address.html) - generates a compressed bitcoin address from a compressed public key.

7. [max-money.js](./max-money.html) - calculates the maximum amount of bitcoin that can be mined.

8. [merkleroot-two-txs.js](./merkleroot-two-txs.html) - generates the merkleroot of two transaction hashes.

9. [p2wpkh.js](./p2wpkh.html) - creates P2SH address from a base58 encoded bitcoin address.

10. [pay-to-addr-script.js](./pay-to-addr-script.html) - creates a script which pays to a base58 encoded bitcoin address.

11. [satoshi-words.js](./satoshi-words.html)* - extracts the script of the genesis block and decodes it.

12. [vanity-miner.js](./vanity-miner.html) - creates a base58 encoded bitcoin address that contains a human readable message.

13. [verify-merkleroot-of-block.js](./verify-merkleroot.html)* - fetches the merkle root of a block, fetches the list of transactions in that block and calculates the merkle root, verifying that the calculated merkle root is the same as the fetched one.


*Require running a full node.


<br>

## [Generate bitcoin address -->](./)

[back](./)


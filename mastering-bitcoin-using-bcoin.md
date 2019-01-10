---
layout: default
---

# Mastering Bitcoin Examples using Bcoin

In this post, we are rewriting some of the examples from the book [Mastering Bitcoin](https://github.com/bitcoinbook/bitcoinbook) by Andreas Antonopoulos using Javascript. Most of these programs require a bitcoin library to execute and for that we will use [bcoin](https://bcoin.io/). For string encodings, we will use [bstring](https://www.npmjs.com/package/bstring) and for cryptographic hash functions, we will use [bcrypto](https://www.npmjs.com/package/bcrypto).

### bcoin functions used

1.  `bcoin.HDPrivateKey.generate()` - generates an object containing private key, public key, and other attributes.
2.  `bcoin.Address.fromScripthash()` - returns an address from a script hash.
3.  `bcoin.Script.fromAddress()` - returns a script from a base58 encoded bitcoin address.
4.  `bcoin.util.revHex()` - returns the reverse of a hex string.

### bcrypto functions used

1.  `bcrypto.RIPEMD160.digest()` - returns the RIPEMD160 cryptographic hash.
2.  `bcrypto.SHA256.digest()` - returns the SHA256 cryptographic hash.

### bstring functions used

1.  `base58.encode()` - encodes a string into base58 format.

<br>

## [List of Programs --> ](./list-of-programs.html)

[back](./)

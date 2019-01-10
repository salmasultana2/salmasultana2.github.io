---
layout: default
---

## Generating a bitcoin address

The sequence of steps to generate a bitcoin address are:

1.  Generate a private key - A private key is a 32 bit number picked at random.
2.  Generate the public key - Public key is calculated from private key using elliptic curve multiplication.
    Note: In bcoin, we can directly get the public key using the `bcoin.HDPrivateKey.generate()` method.
3.  Generate the public key hash -
    * Hash the public key using SHA256 cryptographic hashing algorithm.
    * Hash the result with RIPEMD160 cryptographic hashing algorithm. The end result is the public key hash
4.  Base58Check encoding -
    * Add version byte as prefix to the public key hash.
    * Generate the version byte hash by hashing the result with SHA256 cryptographic hashing algorithm twice.
    * Get the first four bytes of the version byte hash. This is the checksum.
    * Concatenate the checksum with the public key hash.
5.  Encode the result in base58 encoding. The result is the base58 encoded bitcoin address and it always starts with '1'.

## Code

```js
"use strict"

const { base58 } = require("bstring")
const bcoin = require("bcoin")
const bcrypto = require("bcrypto")

// Generate public key using bcoin
const publicKey = bcoin.HDPrivateKey.generate().publicKey

// Generate publicKeyHash
const publicKeyHash = bcrypto.RIPEMD160.digest(bcrypto.SHA256.digest(publicKey))

// Base58 check encoding
const addressVersionByte = Buffer.concat([Buffer.alloc(1), publicKeyHash])
const addressVersionByteHash = bcrypto.SHA256.digest(
  bcrypto.SHA256.digest(addressVersionByte)
)

const checksum = addressVersionByteHash.slice(0, 4)

const address25Byte = Buffer.concat([addressVersionByte, checksum])

// Base58 encoded bitcoin address, starts with '1'
const addressBase58Encoded = base58.encode(address25Byte)

console.log(`Public key: ${publicKey.toString("hex")}`)
console.log(`Address: ${addressBase58Encoded}`)
```

<br>
## [Extract P2SH address from a pubKey script -->](./extract-from-pk-script.html)

[back](./mastering-bitcoin-using-bcoin.html)

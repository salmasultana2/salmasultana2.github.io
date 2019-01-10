---
layout: default
---

## Generate a compressed bitcoin address from a compressed public key

## Code

```js
"use strict"

const { base58 } = require("bstring")
const bcoin = require("bcoin")
const bcrypto = require("bcrypto")

// A compressed public key has length 33 bytes and starts with
// 02 or 03 in hex format
const publicKey = bcoin.HDPrivateKey.generate().publicKey

const publicKeyHash = bcrypto.RIPEMD160.digest(bcrypto.SHA256.digest(publicKey))

const addressVersionByte = Buffer.concat([Buffer.alloc(1), publicKeyHash])

const addressVersionByteHash = bcrypto.SHA256.digest(addressVersionByte)

const checksum = addressVersionByteHash.slice(0, 4)

const address25Byte = Buffer.concat([addressVersionByte, checksum])

const compressedBitcoinAddress = base58.encode(address25Byte)

console.log(`Compressed Public Key: ${publicKey.toString("hex")}`)
console.log(`Compressed Bitcoin Address: ${compressedBitcoinAddress}`)
```

<br>
## [Calculate the maximum amount of bitcoin that can be mined](./max-money.html)

[back](./hash-example.html)

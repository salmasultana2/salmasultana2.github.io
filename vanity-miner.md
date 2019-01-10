---
layout: default
---

## Generate a bitcoin address that contains a human readable message

## Code

```js
"use strict"

const { base58 } = require("bstring")
const bcoin = require("../bcoin")
const bcrypto = require("bcrypto")

// '1' represents the first character of a base58 encoded bitcoin address
// and the human readable part is 'Kid'
const searchString = "1Kid"

// Initialize address as empty string
let addressBase58Encoded = ""

// Generate and test i private keys, until a bitcoin address with the
// desired pattern is found
let i = 0
do {
  if (addressBase58Encoded.startsWith(searchString)) {
    console.log(addressBase58Encoded)
    break
  } else {
    getAddress()
    i++
  }
} while (i < 1000000)

// Function to get a bitcoin address from scratch
function getAddress() {
  const publicKey = bcoin.HDPrivateKey.generate().publicKey
  const publicKeyHash = bcrypto.RIPEMD160.digest(
    bcrypto.SHA256.digest(publicKey)
  )
  const addressVersionByte = Buffer.concat([Buffer.alloc(1), publicKeyHash])
  const addressVersionByteHash = bcrypto.SHA256.digest(addressVersionByte)
  const checksum = addressVersionByteHash.slice(0, 4)
  const address25Byte = Buffer.concat([addressVersionByte, checksum])
  addressBase58Encoded = base58.encode(address25Byte)
}
```

<br>

## [Verify merkle root of a block](./verify-merkleroot.html)

[back](./satoshi-words.html)

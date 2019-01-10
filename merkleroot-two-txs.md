---
layout: default
---

## Generate merkle root of two transaction hashes

## Code

```js
"use strict"

const bcrypto = require("bcrypto")
const bcoin = require("bcoin")

// From block blockHeight = "100009"
const merkleRoot =
  "9a0a7e4bac70a372bdb3d2049a8f5675f192ab2efd064a65747e827fa2c7984f"

const left = Buffer.from(
  "c4a186bf7e0ec470679e3ffe63c70aa5eb35fb69b3a30c8508a216da6c74ccc8",
  "hex"
)

const right = Buffer.from(
  "e278b5d80d96e7ecc3b7feb57652bb9bc1547cc3bbcac3c5c1e2a6b2ea130893",
  "hex"
)

const node = bcrypto.SHA256.digest(
  bcrypto.SHA256.digest(Buffer.concat([left, right]))
)

const root = bcoin.util.revHex(node.toString("hex"))

console.log(`Merkle root from block: ${merkleRoot}`)
console.log(`Merkle root calculated: ${root}`)
```

<br>
## [Generate a P2SH address from a base58 encoded bitcoin address](./p2wpkh.html)

[back](./max-money.html)

---
layout: default
---

## Create P2SH address from base58 encoded bitcoin address

## Code

```js
"use strict"

const bcoin = require("bcoin")
const bcrypto = require("bcrypto")

const address = "1Ek9S3QNnutPV7GhtzR8Lr8yKPhxnUP8iw"

const addressBuffer = Buffer.from(address)

const prefix = Buffer.from("0014", "hex")

const segwitP2PKH = Buffer.concat([prefix, addressBuffer])

const p2shHash = bcrypto.RIPEMD160.digest(bcrypto.SHA256.digest(segwitP2PKH))

const p2shAddress = bcoin.Address.fromScripthash(p2shHash)

// p2sh address begins with 3
const newAddress = p2shAddress.toString()

console.log(`Base58 bitcoin address: ${address}`)
console.log(`P2SH address: ${newAddress}`)
```

<br>

## [Create a script which pays to a bitcoin address](./pay-to-addr-script.html)

[back](./merkleroot-two-txs.html)

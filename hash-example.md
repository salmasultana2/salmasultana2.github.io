---
layout: default
---

## Find a phrase that produces a hash starting with 0

## Code

```js
"use strict"

const bcrypto = require("bcrypto")

const text = "I am Satoshi Nakamoto"

const target =
  "Find a phrase that produces a hexadecimal hash that starts with a zero"

let input, inputData, hash

hash = null

console.log("\n")
console.log(`Target: ${target}\n`)

console.log(`Phrase : ${text}\n`)
console.log("Starting with nonce = 0\n")
for (let nonce = 0; nonce <= 20; nonce++) {
  input = `${text}${nonce}`
  inputData = Buffer.from(input)
  hash = bcrypto.SHA256.digest(inputData)
  console.log(`${text}${nonce} : ${hash.toString("hex")}`)
  if (hash.toString("hex").startsWith("0")) {
    console.log(`\nTarget is found for the nonce value : ${nonce}`)
    break
  }
}
```

<br>
## [Generate a compressed bitcoin address from a compressed public key](./key-to-address.html)

[back](./get-utxo.html)

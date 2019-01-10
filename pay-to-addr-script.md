---
layout: default
---

## Create a script which pays to a bitcoin address

## Code

```js
"use strict"

const bcoin = require("bcoin")

const address = "12gpXQVcCL2qhTNQgyLVdCFG2Qs2px98nV"

const script = bcoin.Script.fromAddress(address)

console.log(`Address: ${address}`)
console.log(`Script: ${script}`)
```

<br>

## [Extract and decode the script of the genesis block](./satoshi-words.html)

[back](./p2wpkh.html)

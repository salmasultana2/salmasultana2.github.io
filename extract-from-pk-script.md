---
layout: default
---

## Extracting a P2SH address from a public key script

1.  Public key script : A script included in outputs which sets the conditions that must be fulfilled for those satoshis to be spent.

2.  P2SH Address:

## Code

```js
"use strict"

const bcoin = require("bcoin")
const bcrypto = require("bcrypto")

const script = "76a914128004ff2fcaf13b2b91eb654b1dc2b674f7ec6188ac"

// Convert script to buffer as bcrypto hash functions only input buffer as an
// argument.
const scriptBuffer = Buffer.from(script)

// Script hash = RIPEMD160(SHA256(script)) and result is 20 bytes in size
const scriptHash = bcrypto.RIPEMD160.digest(bcrypto.SHA256.digest(scriptBuffer))

// P2SH addresses begin with '3'
const P2SHAddress = bcoin.Address.fromScripthash(scriptHash).toString()

console.log(`P2SH Address: ${P2SHAddress}`)
```

<br>
## [Get information of a block -->](./get-block.html)

[back](./addr.html)

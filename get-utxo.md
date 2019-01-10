---
layout: default
---

## Getting information of the unspent transaction outputs of an address

## Code

```js
"use strict"

const { WalletClient } = require("bclient")
const { Network } = require("../bcoin")
const network = Network.get("main")

const address = ["1PtWAUtjWoJp3kFnELcbmjNSPddYkoCekp"]
const minconf = 0
const maxconf = 20

const walletOptions = {
  network: network.type,
  port: network.walletPort,
  apiKey: "api-key",
}

const walletClient = new WalletClient(walletOptions)
;(async () => {
  const result = await walletClient.execute("listunspent", [
    minconf,
    maxconf,
    address,
  ])
  console.log(result)
  if (result.length === 0) {
    console.log("There are no unspent outputs")
  }
})()
```

<br>
## [Find a phrase that produces a hash starting with 0 -->](./hash-example.html)

[back](./get-block.html)

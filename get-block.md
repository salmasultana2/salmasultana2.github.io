---
layout: default
---

## Getting information of a block, specified via it's block height

## Code

```js
"use strict"

const { NodeClient } = require("bclient")
const { Network } = require("../bcoin")
const network = Network.get("main")

const blockHeight = "406267"

const clientOptions = {
  network: network.type,
  port: network.rpcPort,
  apiKey: "api-key",
}

const client = new NodeClient(clientOptions)
;(async () => {
  const blockByHeight = await client.getBlock(blockHeight)
  console.log("By height: \n", blockByHeight)
})()
```

<br>
## [Get information of unspent transaction outputs -->](./get-utxo.html)

[back](./extract-from-pk-script.html)

---
layout: default
---

## Extract and decode the script of the genesis block

## Code

```js
"use strict"

const blockHeight = "0"

const { NodeClient } = require("bclient")
const { Network } = require("../bcoin")
const network = Network.get("main")

const clientOptions = {
  network: network.type,
  port: network.rpcPort,
  apiKey: "api-key",
}

const client = new NodeClient(clientOptions)
;(async () => {
  const blockByHeight = await client.getBlock(blockHeight)
  const script = blockByHeight.txs[0].inputs[0].script
  const scriptBuffer = Buffer.from(script, "hex")
  const message = scriptBuffer.toString()
  console.log(message)
})()
```

<br>

## [Generate a bitcoin address that contains a human readable message](./vanity-miner.html)

[back](./pay-to-addr-script.html)

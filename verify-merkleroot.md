---
layout: default
---

## Verify merkle root of any block specified via it's block height

## Code

```js
"use strict"

const bcoin = require("../bcoin")
const bcrypto = require("bcrypto")

const { NodeClient } = require("bclient")
const { Network } = require("../bcoin")
const network = Network.get("main")

const blockHeight = process.argv[2]

const clientOptions = {
  network: network.type,
  port: network.rpcPort,
  apiKey: "api-key",
}

const client = new NodeClient(clientOptions)

const transactions = []

const merkleTree = []

let level = [],
  merkleRoot
;(async () => {
  const blockByHeight = await client.getBlock(blockHeight)
  const blockMerkleRoot = blockByHeight.merkleRoot
  console.log(`Block Merkle Root: ${blockMerkleRoot}`)
  for (let i = 0; i < blockByHeight.txs.length; i++) {
    transactions.push(
      Buffer.from(
        bcoin.util.revHex(Buffer.from(blockByHeight.txs[i].hash, "hex")),
        "hex"
      )
    )
  }
  console.log(`Merkle Root calculated: ${findMerkleRoot(transactions)}`)
})()

function findMerkleRoot(txs) {
  if (txs.length === 1) {
    merkleRoot = txs[0]
  } else if (txs.length > 1 && txs.length % 2 !== 0) {
    dupLastElement(txs)
  }
  if (txs.length > 1 && txs.length % 2 === 0) {
    const numberOfLevels = Math.ceil(Math.log2(txs.length))
    for (let i = 0; i <= numberOfLevels; i++) {
      if (level.length === 0) {
        txs.forEach((item, index) => {
          if (index % 2 === 0) {
            level.push(
              bcrypto.SHA256.digest(
                bcrypto.SHA256.digest(
                  Buffer.concat([txs[index], txs[index + 1]])
                )
              )
            )
          }
        })
        merkleTree.push(level)

        if (level.length > 1 && level.length % 2 !== 0) {
          const treeIndex = merkleTree.indexOf(level)
          const oddLevel = level.slice(0)
          dupLastElement(level)
          merkleTree.splice(treeIndex + 1, 0, oddLevel)
        }
      } else if (level.length > 1 && level.length % 2 === 0) {
        const levelCopy = level.slice(0)
        level = []
        levelCopy.forEach((item, index) => {
          if (index % 2 === 0) {
            level.push(
              bcrypto.SHA256.digest(
                bcrypto.SHA256.digest(
                  Buffer.concat([levelCopy[index], levelCopy[index + 1]])
                )
              )
            )
          }
        })
        merkleTree.push(level)
        if (level.length > 1 && level.length % 2 !== 0) {
          const treeIndex = merkleTree.indexOf(level)
          const oddLevel = level.slice(0)
          dupLastElement(level)
          merkleTree.splice(treeIndex + 1, 0, oddLevel)
        }
      } else if (level.length === 1) {
        merkleRoot = level[0]
      }
    }
  }
  return bcoin.util.revHex(merkleRoot).toString("hex")
}

function dupLastElement(arr) {
  if (arr.length > 1 && arr.length % 2 !== 0) {
    arr.push(arr[arr.length - 1])
  }
  return arr
}
```

<br>

## [Implementing an interactive Merkle Tree using Vue Material ---> ](./Merkletree-VUEJS/merkle-tree-vuejs.html)

[back](./vanity-miner.html)

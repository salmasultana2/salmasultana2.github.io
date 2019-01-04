---
layout: default
---

# Merkle Tree Full Code in Javascript

```js
const sha256 = require("js-sha256").sha256

const txs = [
  "tx1",
  "tx2",
  "tx3",
  "tx4",
  "tx5",
  "tx6",
  "tx7",
  "tx8",
  "tx9",
  "tx10",
  "tx11",
  ]
let hashedtxs = [],
  branches = [],
  branchCounter = 0,
  merkleRoot

if (txs.length == 0) {
  console.log(`There are no transactions to be summarized`)
} else {
  console.log(`Transactions to be summarized: ${txs}`)
  makeEvenElements(txs)
  console.log(`Leaf nodes: ${txs}`)

  for (const tx of txs) {
    hashedtxs.push(sha256(sha256(tx)))
  }
  console.log("Leaf nodes hashed using double-SHA256 algorithm:")
  console.log(hashedtxs)

  const rep = Math.ceil(Math.log2(txs.length))

  for (let i = 0; i <= rep; i += 1) {
    if (hashedtxs.length == 1) {
      merkleRoot = hashedtxs[0]
      console.log(`The Merkle Root is ${merkleRoot}`)
    } else if (branches.length == 1) {
      merkleRoot = branches[0]
      console.log(`The Merkle Root is ${merkleRoot}`)
    } else if (hashedtxs.length > 1 && branches.length == 0) {
      hashedtxs.forEach((item, index) => {
        if (index % 2 == 0) {
          branches.push(
            sha256(sha256(hashedtxs[index].concat(hashedtxs[index + 1])))
          )
        }
      })
      console.log(`Branch: ${(branchCounter += 1)}`)
      console.log(branches)
      if (branches.length > 1 && branches.length % 2 != 0) {
        makeEvenElements(branches)
        console.log(`Now, Branch ${branchCounter} is: `)
        console.log(branches)
      }
    } else if (branches.length > 0) {
      let branchesCopy = Array.from(branches)
      branches = []
      branchesCopy.forEach((item, index) => {
        if (index % 2 == 0) {
          branches.push(
            sha256(sha256(branchesCopy[index].concat(branchesCopy[index + 1])))
          )
        }
      })
      console.log(`Branch: ${(branchCounter += 1)}`)
      console.log(branches)
      if (branches.length > 1 && branches.length % 2 != 0) {
        makeEvenElements(branches)
        console.log(`Now, Branch ${branchCounter} is: `)
        console.log(branches)
      }
    }
  }
}

function makeEvenElements(arr) {
  if (arr.length > 1 && arr.length % 2 != 0) {
    console.log(`Cannot build Merkle Tree for odd number of data elements.`)
    console.log(`Duplicating the last transaction to achieve an even number of data elements.`)
    arr.push(arr[arr.length - 1])
  }
}
```


<br>

## [Merkle Tree Demo -->](./merkle-tree-demo.html)

[back](./)




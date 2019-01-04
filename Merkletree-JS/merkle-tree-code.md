---
layout: default
---

# Merkle Tree Code in JS

## Variables

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
```

1. The constant `sha256` loads the `js-sha256` modules via the `require()` function.
2. The `txs[]` array contains a list of transactions to be summarized.
3. The `hashedtxs[]` array contains the double-SHA256 hash of each element in `txs[]` array. The `hashedtxs[]` can also be said to contain the leaf nodes.
4. The `branches[]` array contains a list of results obtained by concatenating and hashing two consecutive nodes. 
5. The `branchCounter` counts the number of branches calculated in order to reach the merkle root.
6. The `merkleRoot` variable is a string representing a 32 byte alphanumeric hash. 
<br>

## Workflow

```js
if (txs.length == 0) {
  console.log(`There are no transactions to be summarized`)
} else {
  console.log(`Transactions to be summarized: ${txs}`)
  makeElementsEven(txs)
  console.log(`Leaf nodes: ${txs}`)

```

We first check the `txs.length` to ensure that we have some transactions to summarize. If `txs.length` is zero, then a message is printed to the console stating that there are no transactions to be summarized.

If there are some transactions to be summarized, we check that we have an even number of elements.

+ If yes, we may proceed to hashing the transactions using double-SHA256 cryptographic hashing algorithm.

+ If there are odd number of transactions, then we duplicate the last transaction to achieve an even number of elements. This is checked by `makeElementsEven()` method shown below.

```js
function makeElementsEven(arr) {
  if (arr.length > 1 && arr.length % 2 != 0) {
    console.log(`Cannot build Merkle Tree for odd number of data elements.`)
    console.log(`Duplicating the last transaction to achieve an even number of data elements.`)	
    arr.push(arr[arr.length - 1])
  }
}
```

Each element from the `txs[]` array is hashed using double-SHA256 cryptographic hashing algorithm and is stored in the `hashedtxs[]` array. 

```js
  for (const tx of txs) {
    hashedtxs.push(sha256(sha256(tx)))
  }
  console.log("Leaf nodes hashed using double-SHA256 algorithm:")
  console.log(hashedtxs)
```

For _n_ number of transactions, a merkle tree needs to produce log2(_n_) 32-byte hashes, to reach the merkle root. So, we calculate that using:

```js
const rep = Math.ceil(Math.log2(txs.length))
```

We repeat the concatenating and hashing process of n & n+1 nodes for _`rep`_ number of times using a `for loop`

If there is only one hash in `hashedtxs[]` array or in `branches[]` array, we can say that, that element is the `merkleRoot`. So, we check that condition with the following code and print the merkle root to the console.

```js
  for (let i = 0; i <= rep; i += 1) {
    if (hashedtxs.length == 1) {
      merkleRoot = hashedtxs[0]
      console.log(`The Merkle Root is ${merkleRoot}`)
    } else if (branches.length == 1) {
      merkleRoot = branches[0]
      console.log(`The Merkle Root is ${merkleRoot}`)
    } 
```
If the `hashedtxs[]` array contains more than one element & the elements of `branches[]` array have not been calculated yet, i.e. `branches[]` array is empty, then we concatenate the n & n+1 nodes from `hashedtxs[]` array, hash the result, and push the hash to `branches[]` array. 

Once the n-1 & n nodes in the `hashedtxs[]` array have been concatenated, hashed and pushed to `branches[]` array, the `branchCounter` value is incremented. The branch along with its number and its elements is printed to the console.

```js
else if (hashedtxs.length > 1 && branches.length == 0) {
      hashedtxs.forEach((item, index) => {
        if (index % 2 == 0) {
          branches.push(
            sha256(sha256(hashedtxs[index].concat(hashedtxs[index + 1])))
          )
        }
      })
      console.log(`Branch: ${(branchCounter += 1)}`)
      console.log(branches)
```

We need to check whether the calculated branch has even number of elements. If not, then make the elements even by duplicating the last element. 

```js
      if (branches.length > 1 && branches.length % 2 != 0) {
        makeElementsEven(branches)
        console.log(`Now, Branch ${branchCounter} is: `)
        console.log(branches)
      }
    } 
```
If a branch is calculated, then we need to concatenate and hash the elements of that branch. This is done by cloning the `branches[]` array to a `branchesCopy[]` array, clear the `branches[]` array, and then concatenating n & n+1 nodes from `branchesCopy[]` array, hashing them using double-SHA256 and pushing the hash to `branches[]` array. 

```js
else if (branches.length > 0) {
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
```

Again, check whether the resulting branch has even number of elements or odd number of elements. If odd, then make it even by duplicating the last element of 

```js
      if (branches.length > 1 && branches.length % 2 != 0) {
        makeElementsEven(branches)
        console.log(`Now, Branch ${branchCounter} is: `)
        console.log(branches)
      }
    }
  }
}
```

Repeat the process for _rep_ number of times
<br>

## [See Full Code -->](./merkle-tree-full-code.html)

[back](./)


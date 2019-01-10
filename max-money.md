---
layout: default
---

## Calculate the maximum amount of bitcoin that can be mined

## Code

```js
"use strict"

const yearStart = 2009

const rewardInterval = 210000

let totalBitcoin = 0,
  reward = 50,
  currentYear = null

console.log("Mining Reward according to years")
console.log(`${yearStart} : ${reward} BTC`)
totalBitcoin += rewardInterval * reward

for (let i = 4; i <= 150; i += 4) {
  reward = reward / 2
  currentYear = yearStart + i
  totalBitcoin += rewardInterval * reward
  if (currentYear > 2140) {
    console.log(`There will be no mining reward after 2140`)
    break
  }
  console.log(`${currentYear} : ${reward} BTC`)
}
console.log(`Total BTC to ever be created: ${totalBitcoin}`)
```

<br>
## [Generate merkle root of two transaction hashes](./merkleroot-two-txs.html)

[back](./key-to-address.html)

---
layout: default
---

# Merkle Tree Demo

You can run a Javascript program in the terminal using the command:

```js
node filename.js
```

The following is a merkle tree output summarizing 11 transactions and finding the merkle root.

```js
➜  MerkleTreeJS git:(master) ✗ node merkletree.js 
Transactions to be summarized: tx1,tx2,tx3,tx4,tx5,tx6,tx7,tx8,tx9,tx10,tx11
Cannot build Merkle Tree for odd number of data elements. Duplicating the last transaction to achieve an even number of data elements.
Leaf nodes: tx1,tx2,tx3,tx4,tx5,tx6,tx7,tx8,tx9,tx10,tx11,tx11
Leaf nodes hashed using double-SHA256 algorithm:
[ '83e37c5c6cf954dfc81c9dde56d423572b6f915be52029a77a3388b4c1610267',
  'eec1f8fc0431545080ed56a13ec11e46be820738afe1bde6d7764dc16e89399c',
  'ef31d773d3f504b7eb2ec598c8a7c5a9c7df0df0afdd6288aca5a47ecbcc6dc6',
  'ee209230c54111328e2f6c0f303747333cdeda8c32e2633a4e55fe2bc3f2fafa',
  'a1e86fa54fbc5d72b999cc3b119cf91d8c76354889b68447748d0546261c4dfd',
  'df4d7e5adf1b30512611fed582459e4845c9440caafb59a5a9401fec9bc5fc70',
  '12cd549f476cd4c5aafaf69f2619c87ae6508bc8dc46bf1b5f584e677738004d',
  '5809128497c38e11d6aed9e7539d20920f268fb5593058e4218e494ea48e2e3c',
  'bb04d6f98a33e103fb0ba6f41bb2cae771cb585d5a07185bf0d72c27db9d94d3',
  '5de3cbb9b6b24e3ba5b52f7b9259bc42c8e03ad1584e12dcd8a1ede0fea2c832',
  '77aebc5ad3cef696a5bd9b5fa3939345b1b8d63f2f21e8f4367424e33b9caee3',
  '77aebc5ad3cef696a5bd9b5fa3939345b1b8d63f2f21e8f4367424e33b9caee3' ]
Branch: 1
[ '5ed021a3c0c7ecf74ea85af9842adfabd1b8a59424c00378ed1e0656a61321fc',
  '9191b67cc19467fb8d3aae6766a8411ee4e359838feac7fafd6fa31390946cdb',
  '6254bc006ae9822ceef7268d35c6587d483105b6edbb203737dd2cae773f4898',
  '7733e24e0f492bdfe9b9b82a83094f6e70dfa2e1259de69c0fa587f098065c9d',
  '17c22ac0239a7afe386c8d8a8e77fa643d85623e2848ff22850e18d9ee5360c4',
  '90fae060d052f6e16ee1903e5d40ce5d5ce148f2f8d84fa70a6ef2af573eb093' ]
Branch: 2
[ '6e4dcfd6e76c49f811a87929e8341785c621b4efaacd1d0cc2692b21fd466498',
  '8006d6dedd9786b9a9d2343ca5352ace695417c6fc4f1d9dab4367902bb0a514',
  '461e436ba4eb0123b41092ea685995c0d8ae55146a4a5d3b6dc8fb1147d9dca0' ]
Cannot build Merkle Tree for odd number of data elements. Duplicating the last transaction to achieve an even number of data elements.
Now, Branch 2 is: 
[ '6e4dcfd6e76c49f811a87929e8341785c621b4efaacd1d0cc2692b21fd466498',
  '8006d6dedd9786b9a9d2343ca5352ace695417c6fc4f1d9dab4367902bb0a514',
  '461e436ba4eb0123b41092ea685995c0d8ae55146a4a5d3b6dc8fb1147d9dca0',
  '461e436ba4eb0123b41092ea685995c0d8ae55146a4a5d3b6dc8fb1147d9dca0' ]
Branch: 3
[ '964bc6ecafc0a0dd8c0a87272cf08980d46b07c9b90a7db66000f8d1e49ee05c',
  '8477d01493b1fa93ed42292960d361335b93bc89564cfe9dc73a7c62d6127e77' ]
Branch: 4
[ '0fca21bafe193765ed98116b3145f66696b9c4a55f59e38c55d772bbfe9ae710' ]
The Merkle Root is 0fca21bafe193765ed98116b3145f66696b9c4a55f59e38c55d772bbfe9ae710

```

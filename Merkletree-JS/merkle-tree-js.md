---
layout: default
---

# Implementing a Merkle Tree in Javascript

In this post, you will find the implementation of a Merkle Tree summarizing _n_ transactions. 

A Merkle Tree produces a root, aka merkle root, by recursively concatenating and hashing pairs of nodes until there is only one node left.

The hashes are obtained by applying a cryptographic hashing algorithm, known as SHA256, twice to each element. This is also known as double-SHA256 hashing algorithm.

## [Merkle Trees in Detail](./merkle-tree-js.html)

### Definition of a Merkle Tree

A merkle tree is a data structure used for efficiently summarizing and verifying the integrity of large sets of data. The nodes of a merkle tree contain cryptographic hashes. A merkle tree is represented upside down with the "root" at the top and the "leaves" at the bottom.

### Merkle Trees in Bitcoin

Merkle trees are used in bitcoin to summarize all the transactions in a block, producing an overall digital fingerprint of the entire set of transactions, providing a very efficient process to verify whether a transaction is included in a block.

### Constructing a Merkle Tree 

A merkle tree is constructed by recursively concatenating and hashing pairs of nodes until the merkle root is reached

A merkle tree is constructed bottom-up, placing the leaf nodes at the bottom, and the merkle root at the top. The number of leaf nodes that have to be summarized is counted. Let's call this number _n_.

+ If _n_ is an even number, then we start by concatenating the first node and the second node, and hash the result using double-SHA256 cryptographic hashing algorithm. The hash is called the _parent node_. Similarly, parent nodes of all the leaf nodes are computed.

+ If _n_ is an odd number, then the last element is duplicated to achieve an even number of elements. Then, the _n_<sup>th</sup> node is concatenated with the _n+1_ node and the result is hashed using double-SHA256 cryptographic hashing algorithm. The parent nodes of all the leaf nodes are computed in this way.

The concatenating and hashing steps are repeated for the parent nodes, and repeated again for the next set of parent nodes and this process of recursively concatenating, hashing, and duplicating the last element for odd number of nodes, is continued till there is only one hash left in the tree. This hash is known as a root, or a merkle root.

The merkle root is a 32 byte hash summarizing all the transactions.

### Example of a Merkle Tree Containing 16 leaf nodes 
<br>
![Merkle Tree summarizing many data elements](https://raw.githubusercontent.com/bitcoinbook/bitcoinbook/develop/images/mbc2_0904.png)

<br>
## [SHA256 in detail -->](./sha-256-description.html)

[back](./)


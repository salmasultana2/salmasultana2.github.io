---
layout: default
---

# [SHA256 Cryptographic Hashing Function in detail](./sha-256-description.html)

### Definition of a cryptographic hash function

A cryptographic hash function is a function that takes an input and returns a fixed-size alphanumeric string. The string may be called as the `hash value`, `message digest`, `digital fingerprint`, `digest` or `checksum`.

### Properties of a cryptographic hash function

Some of the properties of an ideal cryptographic hash function are: 

+ it returns a 32 byte alphanumeric string for every input, no matter the length and content of the input. 
+ its collision resistance: No two strings can produce the same hash.
+ it preserves the integrity of the input. Even a slight change in the input will produce a completely different hash.

### Applications of cryptographic hash function

Some common applications of cryptographic hash functions include:

+ Message integrity checks
+ Digital signatures
+ Authentication

### SHA256 Integrity Example 

The SHA256 cryptographic hash function produces a different output for every input. Even two similar looking inputs will produce two different hashes if either one contains a small change.

For example, let's consider `stringA` to be "Complete a task" and `stringB` to be "complete a task". The difference between both the strings is only the case of the first character `C`, but their cryptographic hashes will be completely different from each other. In Javascript, this can be seen as follows.

```js
> const sha256 = require('js-sha256').sha256;

> let stringA = "Complete a task"

> let stringB = "complete a task"

> let hashA = sha256(stringA)

> let hashB = sha256(stringB)

> hashA == hashB
false
> hashA
'1289c056b057deb5cc1234ddc7cf0f2d0f0cccbcc0f79f3d327507fd71e85adb'
> hashB
'a85e9f04905461bc8b3ff12825af868c6097149f7719c620e05bd279e6b360ad'

```

Evidently, the value of `hashA` is completely different from that of `hashB`. Therefore, using this cryptographic hashing algorithm a person can determine the integrity of the data.

If the hash of some previously published data is different than the hash of the current data, we can conclude that the data has been tampered with.

<br> 

## [Node JS and SHA256 JS Module Installation -->](./node-js-installation.html)

[back](./merkle-tree-js.html)

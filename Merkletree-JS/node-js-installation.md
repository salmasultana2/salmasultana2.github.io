---
layout: default
---

## [Node JS Installation](./node-js-installation.html)

In this section, we will take a look at installation of Node JS on different platforms. If node is already installed on your computer, you may skip this section and move to SHA256 JS module installation.

### Node JS Installation on Ubuntu

1. To install Node.js on Ubuntu, run the command:

```js
sudo apt-get install nodejs
```

This command will install node.js, along with NPM and many other dependent packages on your system.

### Node JS Installation on Windows

1. Download the Windows installer (.msi file) from the [Nodes.js ®](https://nodejs.org/en/download/) web site.
2. Run the installer.
3. Accept the license agreement, click next and accept the default installation settings.
4. Restart your computer.

Please note that you will not be able to use node.js until you restart your computer.

### Node JS Installation of Mac OS

1. The prerequisite to install nodejs on Mac OS is to have XCode and Homebrew downloaded on your computer.
2. If the prerequisites are met, open the Terminal. To install node.js and npm using Homebrew, run tshe command: 

```js
brew install node
```

Note: The instructions to install XCode and Homebrew can be found [here](https://www.moncefbelyamani.com/how-to-install-xcode-homebrew-git-rvm-ruby-on-mac/)

## Verify the installed versions

The next step after installing nodejs and npm is to check and verify the installed versions. You may run the following commands on any of the previously mentioned platforms:

+ To check node version
 
```js
node -v
``` 

+ To check npm version

```js
npm -v
```

You can find more details about current versions on [node.js official website](https://nodejs.org).

<br>

## [SHA-256 JS Module Installation](./node-js-installation.html)

To install a simple SHA-256 hash function for JavaScript which supports UTF-8 encoding, run the command: 

```js
npm install js-sha256
```

To use this SHA256 hashing algorithm in your program, open your javascript code and load the `js-sha256` modules using the `require()` function.

```js
const sha256 = require("js-sha256").sha256;
```

Now, you can hash any string or variable by passing it as a parameter to `sha256()` function. Example: 

```js
sha256('abc');
``` 
The result should be a 32 byte hash value equal to  'ba7816bf8f01cfea414140de5dae2223b00361a396177a9cb410ff61f20015ad'

In our construction of a merkle tree, we are using double-SHA256 cryptographic hashing algorithm which is simply SHA256 applied twice. 

You can compute the double-SHA256 hash value of any string or variable, using the following statement in Javascript. 

```js
> sha256(sha256('abc'));
```

The result should always be a 32 byte hash value equal to 'dfe7a23fefeea519e9bbfdd1a6be94c4b2e4529dd6b7cbea83f9959c2621b13c'


<br>

## [Merkle Tree Code in JS -->](./merkle-tree-code.html)

[back](./)


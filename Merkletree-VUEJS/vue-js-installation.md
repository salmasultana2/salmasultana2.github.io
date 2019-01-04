---
layout: default
---

# Constructing a Merkle Tree using Vue Material

In the [last post](./Merkletree-JS/merkle-tree-js.html), we constructed a Merkle Tree with a predefined set of transactions in `txs[]` array. The merkle root was calculated successfully and all the nodes in each branch were displayed. But, the output did not have a tree structure. 

In this post, we aim at constructing a Merkle Tree in the form of a visual tree with merkle root at the top and leaf nodes at the bottom. 

We will also be taking the number of transactions and list of transactions as input from the user.

## [Vue Material Installation](./Merkletree-VUEJS/vue-js-installation.html)

Install vue-cli using the command:
```js
sudo npm install -g vue-cli
```

Then, download the webpack-based Vue.js project template using the command:
```js
vue init webpack todo-list
```

You would be prompted to enter your project details as shown below:
```js
? Project name: merkletreevue <br>
? Project description: a visual implementation of a merkle tree using vue material <br>
? Author: Salma Sultana <mailto:<salsultana04@gmail.com>> <br>
? Vue build standalone <br>
? Install vue-router? No <br>
? Use ESLint to lint your code? No <br>
? Set up unit tests No <br>
? Setup e2e tests with Nightwatch? No <br>
? Should we run npm install for you after the project has been created? (recommended) npm<br>
```
Now, change into the directory of your newly created project using:
```js
cd todo-list
```

And complete the project setup by installing the dependencies via:

```js
npm install
```

```js
npm run dev
```

Install Vue Material library to the project using:

```js
npm install vue-material --save
```

Open `index.html` file and include the following link elements into the _<head> </head>_ section:

```js
<link rel="stylesheet" href="//fonts.googleapis.com/css?family=Roboto:300,400,500,700,400italic"> <br>
<link rel="stylesheet" href="//fonts.googleapis.com/icon?family=Material+Icons">
```

Open `src/main.js` file and include the below `import` statements to make vue-material accessible in the project

```js
import VueMaterial from "vue-material"
import "vue-material/dist/vue-material.css"
```

Finally, activate Vue Material by executing the `Vue.use()` method in the same file.

```js
Vue.use(VueMaterial)
```

<br>

## [Vue Material Components -->](./vue-material-components.html)

[back](./)


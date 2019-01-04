---
layout: default
---

# Constructing an interactive Merkle Tree using Vue Material

In the [last post](./Merkletree-JS/merkle-tree-js.html), we constructed a Merkle Tree with a predefined set of transactions in `txs[]` array. The merkle root was calculated successfully and all the nodes in each branch were displayed. But, the branches did not have a tree structure. 

In this post, we aim at constructing a Merkle Tree in the form of a visual tree with **merkle root at the top** and **leaf nodes at the bottom**. 

We will also be taking the total number of transactions and the list of transaction IDs which have to be summarized as input from the user.

## [Vue Material Installation](./vue-js-installation.html)

Install vue-cli using the command:
```js
sudo npm install -g vue-cli
```

Then, download the webpack-based Vue.js project template using the command:
```js
vue init webpack merkle-tree
```

You would be prompted to enter your project details as shown below:
```js
? Project name: merkle-tree
? Project description: a visual implementation of a merkle tree using vue material
? Author: Salma Sultana <mailto:<salsultana04@gmail.com>>
? Vue build standalone
? Install vue-router? No 
? Use ESLint to lint your code? No
? Setup unit tests No
? Setup e2e tests with Nightwatch? No
? Should we run npm install for you after the project has been created? (recommended) npm
```
Now, change into the directory of your newly created project using:
```js
cd merkle-tree
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

Open `index.html` file and include the following link elements into the **<head> </head>** section:

```js
<link rel="stylesheet" href="//fonts.googleapis.com/css?family=Roboto:300,400,500,700,400italic"> <br>
<link rel="stylesheet" href="//fonts.googleapis.com/icon?family=Material+Icons">
```

Open `src/main.js` file and include the below `import` statements to make Vue Material accessible in the project.

```js
import VueMaterial from "vue-material"
import "vue-material/dist/vue-material.css"
```

Finally, activate Vue Material by calling the `Vue.use()` method in the same file.

```js
Vue.use(VueMaterial)
```

## [Vue Material Components -->](./vue-material-components.html)

[back](./)

---
layout: default
---

# Building an application using Vue Material

This article assumes prior knowledge of [Vue JS 2.0](https://vuejs.org/v2/guide/) and [Vue Material](https://vuematerial.io/components/app)

Let's build a simple application using Vue Material. You would first need to install Vue Command Line Interface from terminal.

## [Installation](./vue-material-app.html) 

Install vue-cli using the command:
	
**sudo npm install -g vue-cli**

Then, you need to download the webpack-based Vue.js project template by running the following command:

**vue init webpack todo-list**


Once the project template is downloaded, you would be required to enter your project details as shown below:

**? Project name: todo <br>
? Project description: a simple todo list using vue material <br>
? Author: Salma Sultana <<salsultana04@gmail.com>> <br>
? Vue build standalone <br>
? Install vue-router? No <br>
? Use ESLint to lint your code? No <br>
? Set up unit tests No <br>
? Setup e2e tests with Nightwatch? No <br>
? Should we run npm install for you after the project has been created? (recommended) npm** <br>


Now, change into the directory of your newly created project using: 

**cd todo-list**


And complete the project setup by installing the dependencies via: 

**npm install** <br>
**npm run dev**


Add _vue-material_ library to the project by running the command: 

**npm install vue-material --save**


Open _index.html_ file and include the following link elements into the _<head> </head>_ section:

```js
<link rel="stylesheet" href="//fonts.googleapis.com/css?family=Roboto:300,400,500,700,400italic"> <br>
<link rel="stylesheet" href="//fonts.googleapis.com/icon?family=Material+Icons">
```

Open _src/index.js_ file and include the below 'import' statements to make vue-material available in the project

```js
import VueMaterial from 'vue-material'
import 'vue-material/dist/vue-material.css'
```

Finally, activate VueMaterial by executing the _Vue.use()_ method in the same file.

```js
Vue.use(VueMaterial)
```

## [Coding and Documentation -->](./vue-material-app-coding.html)

[back](./)

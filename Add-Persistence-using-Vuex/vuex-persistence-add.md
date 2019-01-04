---
layout: default
---

# Adding persistence to a Vue JS app using Vuex

This article assumes prior knowledge of [Vue JS 2.0](https://vuejs.org/v2/guide/) and [Vuex](https://vuex.vuejs.org/)

I have previously built an app using Vue Material - a simple to-do list app which allows a user to add, edit, complete and clear to-dos.

A key property which was missing in that application was Local Storage. Once I reopened the browser or even refreshed the page, all my to-dos would be gone.

To retain the tasks and their status (whether completed or pending), I added persistence via [Vuex Persistence](https://github.com/robinvdvleuten/vuex-persistedstate)

## [Installation](./vue-persistence-add.html)

Update nodejs to version 0.10.21 using:

```
sudo npm cache clean -f

sudo npm install -g n

sudo n stable
```

Update vue-cli to version 3.0 using the command:
**npm install -g @vue-cli**

Then, you need to create a vuex project but running the command:

**vue create to-do-list-with-persistence**

Before the project is created, you will be presented with the following prompt:

\*\*Vue CLI v3.0.0-beta.6 <br>
? Please pick a preset: <br>
default (babel, eslint) <br>

> Manually select features\*\*

Go ahead and select "Manually select features" using the keyboard up and down keys. Upon selecting that, you will encounter:

? Check the features needed for your project:
( ) TypeScript
( ) Progressive Web App (PWA) Support
(\*) Router

> (\*) Vuex
> ( ) CSS Pre-processors
> ( ) Linter / Formatter
> ( ) Unit Testing
> ( ) E2E Testing

From the list, select "Router" and "Vuex" and hit enter.

**? Project name: todo <br>
? Project description: a simple todo list using vue material <br>
? Author: Salma Sultana <mailto:<salsultana04@gmail.com>> <br>
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
import VueMaterial from "vue-material"
import "vue-material/dist/vue-material.css"
```

Finally, activate VueMaterial by executing the _Vue.use()_ method in the same file.

```js
Vue.use(VueMaterial)
```

## [Coding and Documentation -->](./vuex-persistence-app-coding.html)

[back](./)

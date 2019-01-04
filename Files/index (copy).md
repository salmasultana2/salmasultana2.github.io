---
layout: default
---

# Building a simple app using Vue Material

This article assumes prior knowledge of [Vue JS 2.0](https://vuejs.org/v2/guide/) and [Vue Material](https://vuematerial.io/components/app)

Let's build a simple application using Vue Material. You would first need to install Vue Command Line Interface.

Install vue-cli using the command:
	
**sudo npm install -g vue-cli**


Then, you need to download the webpack-based Vue.js project template by running the following command:

**vue init webpack todo-list**


Once the project template is downloaded, you would be required to enter your project details

**? Project name: todo**
**? Project description: a simple todo list using vue material**
**? Author: Salma Sultana <<salsultana04@gmail.com>>**
**? Vue build standalone**
**? Install vue-router? No**
**? Use ESLint to lint your code? No**
**? Set up unit tests No**
**? Setup e2e tests with Nightwatch? No**
**? Should we run npm install for you after the project has been created? (recommended) npm**


Now, change into the directory of your newly created project

**cd todo-list**


And complete the project setup by installing the dependencies 

**npm install**
**npm run dev**


Add vue-material library to the project by running the command: 

**npm install vue-material --save**


Include the following link elements into the 'head' section of index.html

**<link rel="stylesheet" href="//fonts.googleapis.com/css?family=Roboto:300,400,500,700,400italic">**
**<link rel="stylesheet" href="//fonts.googleapis.com/icon?family=Material+Icons">**


Include the below 'import' statements in src/index.js file to make vue-material available in the project

**import VueMaterial from 'vue-material'**
**import 'vue-material/dist/vue-material.css'**


Finally, activate VueMaterial by executing the Vue.use() method in the same file 

**Vue.use(VueMaterial)**





Text can be **bold**, _italic_, or ~~strikethrough~~.

[Link to another page](./another-page.html).

There should be whitespace between paragraphs.

There should be whitespace between paragraphs. We recommend including a README, or a file with information about your project.

# Header 1

This is a normal paragraph following a header. GitHub is a code hosting platform for version control and collaboration. It lets you and others work together on projects from anywhere.

## Header 2

> This is a blockquote following a header.
>
> When something is important enough, you do it even if the odds are not in your favor.

### Header 3

```js
// Javascript code with syntax highlighting.
var fun = function lang(l) {
  dateformat.i18n = require('./lang/' + l)
  return true;
}
```

```ruby
# Ruby code with syntax highlighting
GitHubPages::Dependencies.gems.each do |gem, version|
  s.add_dependency(gem, "= #{version}")
end
```

#### Header 4

*   This is an unordered list following a header.
*   This is an unordered list following a header.
*   This is an unordered list following a header.

##### Header 5

1.  This is an ordered list following a header.
2.  This is an ordered list following a header.
3.  This is an ordered list following a header.

###### Header 6

| head1        | head two          | three |
|:-------------|:------------------|:------|
| ok           | good swedish fish | nice  |
| out of stock | good and plenty   | nice  |
| ok           | good `oreos`      | hmm   |
| ok           | good `zoute` drop | yumm  |

### There's a horizontal rule below this.

* * *

### Here is an unordered list:

*   Item foo
*   Item bar
*   Item baz
*   Item zip

### And an ordered list:

1.  Item one
1.  Item two
1.  Item three
1.  Item four

### And a nested list:

- level 1 item
  - level 2 item
  - level 2 item
    - level 3 item
    - level 3 item
- level 1 item
  - level 2 item
  - level 2 item
  - level 2 item
- level 1 item
  - level 2 item
  - level 2 item
- level 1 item

### Small image

![Octocat](https://assets-cdn.github.com/images/icons/emoji/octocat.png)

### Large image

![Branching](https://guides.github.com/activities/hello-world/branching.png)


### Definition lists can be used with HTML syntax.

<dl>
<dt>Name</dt>
<dd>Godzilla</dd>
<dt>Born</dt>
<dd>1952</dd>
<dt>Birthplace</dt>
<dd>Japan</dd>
<dt>Color</dt>
<dd>Green</dd>
</dl>

```
Long, single-line code blocks should not wrap. They should horizontally scroll if they are too long. This line should be long enough to demonstrate this.
```

```
The final element.
```

---
layout: default
---

## [Coding and Documentation](./vue-material-app-coding.html)

Once the installation is completed successfully, change into the _todo-list/src_ directory to open the file _App.vue_. This is where we need to make the necessary changes. You may remove all the content which is in the _<div> </div>_  tag. 

We are using the following Vue Material components in our application.

<ol> 
<li> Card </li>
<li> Input </li>
<li> List </li>
<li> Checkbox </li>
<li> Button </li>
</ol>

### Features of our application 

Our application is a simple to-do list. It allows the user to: 

<ul>
<li> Add a task from textfield. </li>
<li> Modify an existing task by double-clicking on that task. </li>
<li> Mark a single task as complete by checking the checkbox OR </li>
<li> Mark all tasks as complete at once by clicking the "Mark all as complete" Button. </li>
<li> Clear the list by clicking the "Clear List" Button. </li>
</ul>


I started by adding the card component and then inserted the rest of the components inside the card. Below is a code snippet used in my todo-list app. You may modify the theme and the components to customize your application.

[View my full project on github](https://github.com/Sultaness/Todo-List-using-Vue-Material-)
<br>

```
<template>
  <div id="app">
    <md-card md-with-hover>
      <md-card-header>
        <div class="md-title">  card.title </div>
        <div class="md-subhead"> card.subTitle </div>
      </md-card-header>
      <md-card-content>
      	<md-input-container id="newTaskContainer">
          <md-field>
            <md-input ref="newTask" id="newTask" v-model="newTask" @keyup.enter.native="addTask()" placeholder="What needs to be done?"></md-input>
          </md-field>
        </md-input-container>   
        <md-list>
          <md-list-item v-for="(task, index) in tasks" :key="task.id">
            <div v-show="task.edit == false" v-bind:class="klass(task.completed)">
              <label @dblclick="task.edit=true"> {{task.text}} </label>
            </div>
            <input v-show="task.edit == true" v-model="task.text" v-on:blur= "task.edit=false; $emit('update')" @keyup.enter="task.edit=false; $emit('update')" />
            <md-checkbox ref="markTaskAsComplete" id="markTaskAsComplete" v-model="task.completed"></md-checkbox>
          </md-list-item>
        </md-list>
        <md-button class="md-raised md-primary" @click.native="completeAll()"> Mark all as completed </md-button>
        <md-button class="md-raised md-primary" @click.native="clearList()"> Clear List </md-button>
      </md-card-content>
    </md-card> 
    <p> Double click to edit an existing todo </p>
  </div>
</template>
```
<br>
I added the hover effect to my card using the `md-with-hover` property. The card is divided into two self-explanatory sub-components `md-card-header` and `md-card-content`.

The `md-card-header` is to display the title and subtitle using `classes` and the `md-card-content` contains the rest of the components. 

For input, we are using `md-input` element of `md-field` component. Each element should have an **id**, **v-model**, and **event**. The event of our textfield is `@keyup.enter.native` which will allow the to-do item to get added in the list once the user hits the enter key.

The `md-list` component allows us to view the to-dos added in a list format using the `md-list-item` element. To display the to-dos added by the user, we are using the `v-for` directive. Each item in the list has an event `@dblclick` and a directive `v-show` which will allow the user to edit the to-do item. 

The `md-checkbox` element of `form` component is used to mark a to-do item as completed.

The `md-button` component has been used twice in our application. One button is to mark all items as completed and the other is to clear the list. The button's event is `@click.native` which point to their respective functions. 

## [Script and Style -->](./vue-material-app-script.html)

[back](./vue-material-app.html) <br>
[home](./)


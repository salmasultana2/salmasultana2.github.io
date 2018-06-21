---
layout: default
---

## [Script](./vue-material-app-script.html)

Let's move on to the script section of our _App.vue_ file.

Our script should clearly define the variables and event handler methods. 

For example, in our app, the to-do items get stored in an array called `tasks[]` which has variables of its own - id, text, completed and edit with their initial values. 

Each todo-item stored in the `tasks[]` array will have an id, some text, completed, and edit values. Other than `tasks`, we have `newTask`, `nextID` to store the to-do items entered by the user.

In methods, we have `addTask()` which takes the input from `md-input`, stores it in `tasks[]` and displays the same in the `md-list-item` element.

The `completeAll()` is a simple method to mark all items in the list as completed. The strike-through property is obtained by the class `.strike-through` which is included in our [style](./vue-material-app-style.html) section.

`clearList()` too is a simple method to clear the items of a array.

Below is the complete script which was used in my application: 

```
<script>
export default {
  name: "App",
  data: function() {
    return {
      title: "",
      card: {
        title: "A simple todo list using Vue material",
        subTitle: "by Salma Sultana"
      },
      tasks: [
        {
          id:0,
          text:"Add your first todo",
          completed: false,
          edit: false
        },
      ],
      newTask: "",
      nextId: 1,
     }
  },
  methods: {
    addTask: function() {
      if (this.newTask.trim() === "")
        return;
      this.tasks.push(
        {
          id: this.nextId,
          text: this.newTask,
          completed: false,
          edit: false
        }
      );
      this.newTask = "";
      this.nextId++;
    },
    completeAll: function () {
      for (const task of this.tasks)
        task.completed = true;
    },
    clearList: function () {
      this.tasks.splice(0,this.tasks.length);
    },
    mounted: function() {
      this.$nextTick(function () {
        var newTask = document.getElementById("newTask");
        newTask.focus();
      })
    }
  }
}
</script>
```

## [Live Demo -->](./vue-material-app-live-demo.html)

[back](vue-material-app-coding.html) <br>
[home](./)

<template>
<div>
 <h2 style="text-align: center;">{{title}}</h2>
        <form @submit.prevent="addtodo">
            <label  for="TodoList">Add a Task</label>
            <input v-model="TodoList" type="text" name="Add a TodoList" id="TodoList" >
            <button type="submit" name="button">Add</button>
        </form>
        <ul>
            <li v-for="todo in todos" :key="todo.id">
             <input type="checkbox" v-model="todo.done" >
            <span :class="{ check: todo.done}">{{todo.title}}</span>
                <button @click="deleteTodo(todo)" type="button" name="button">Delete</button>
            </li>

        </ul>
</div>
</template>

<script>
export default {
  name: 'Todo List',
  data () {
    return {
     title: "Todo List",
        TodoList: '',
        todos: [] 
    }
    },
    methods: {
        addtodo() {
            this.todos.push({
                title: this.TodoList,
                done: false
            });
            this.TodoList='';
        },
        deleteTodo(todo) {
            const todoIndex = this.todos.indexOf(todo);
            this.todos.splice(todoIndex, 1);
          }
           
    
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style>
body{
    background-color: antiquewhite;
    font-family: sans-serif;
    padding-top: 1em;
    padding-bottom: 1em;
    font-size: 2em;
    width: 70%;
    margin: 0 auto;
    }
input, textarea, button, p, div, section, article, select {
    display: 'block';
    width: 100%;
    font-family: sans-serif;
    font-size: 1em;
    margin: 0.5em;
}
.check{
    text-decoration: line-through;
}
</style>

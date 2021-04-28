<template>
  <div class="hello">
    <h1>To-Do List</h1>
    <input type="text" class="todo-input" placeholder="What do I need to do?" 
    v-model="newTodo" @keyup.enter="addTodo" >
    <div v-for="(todo, index) in todos" :key="todo.id" class="todo-item">
      <div class="todo-item-left">
      <div v-if="!todo.editing" @dblclick="editTodo(todo)" class="todo-item-label"> {{todo.title}} </div>
      <input v-else class="todo-item-edit" type="text" v-model="todo.title" 
      @blur="doneEdit(todo)" @keyup.enter="doneEdit(todo)">
      </div>
      <div class="remove-item" @click="removeTodo(index)">
        &times;
      </div>
    </div> 
    </div>
</template>

<script>
export default {
  name: 'todo-list',

 data () {
   return {
     newTodo: '',
     idForTodo: 5,
     todos: [
       {
         'id': 1,
         'title': 'Build first Vue project',
         'completed': false,
         'editing': false,
       },
         {
         'id': 2,
         'title': 'Grocery shopping',
         'completed': false,
         'editing': false,
       },
        {
         'id': 3,
         'title': 'Tidy up the studio',
         'completed': false,
         'editing': false,
       },
         {
         'id': 4,
         'title': 'Promote synergy',
         'completed': false,
         'editing': false,
         }
       ]
      }
 },
 methods: {
   addTodo() {
     if (this.newTodo.trim().length == 0) {
       return
     }
     this.todos.push({
       id: this.idForTodo,
       title: this.newTodo,
       completed: false,
     });

     this.newTodo=''
     this.idForTodo++
   },
   editTodo(todo) {
     todo.editing = true;
   },
   doneEdit(todo) {
     todo.editing = false;
   },
   removeTodo(index) {
     this.todos.splice(index, 1)
   }
 }
 }

</script>

<style lang="scss">
  .todo-input {
    width: 100%;
    padding: 10px 18px;
    font-size: 18px;
    margin-bottom: 16px;
    &:focus {
      outline: 0;
    }
  }

  .todo-item {
    margin-bottom: 12px;
    display: flex;
    align-items: center;
    justify-content: space-between;
  }

  .remove-item {
    cursor: pointer;
    margin-left: 14px;
    &:hover {
      color: black;
    }
  }

  .todo-item-edit {
    font-size: 16px;
    color: rgb(0, 92, 128);
    width: 100%;
    padding: 10px;
    border: 1px solid bisque;

    &:focus {
      outline: none;
    }
  }
  </style>
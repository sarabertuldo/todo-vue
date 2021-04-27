<template>
  <div class="hello">
    <input type="text" class="todo-input" placeholder="What do we need to do?" 
    v-model="newTodo" @keyup.enter="addTodo" >
    <div v-for="todo in todos" :key="todo.id" class="todo-item">
         {{ todo.title}}
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
       },
         {
         'id': 2,
         'title': 'Grocery shopping',
         'completed': false,
       },
        {
         'id': 3,
         'title': 'Tidy up the studio',
         'completed': false,
       },
         {
         'id': 4,
         'title': 'Promote synergy',
         'completed': false,
         }
       ]
      }
 },
 methods: {
   addTodo() {
     this.todos.push({
       id: this.idForTodo,
       title: this.newTodo,
       completed: false,
     });

     this.newTodo=''
     this.idForTodo++
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
  </style>
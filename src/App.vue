<template>
  <div id="app" class="container">
    <img alt="Vue logo" src="./images/charlie.jpg">
    <TodoList> </TodoList>
    <a href="https://github.com/sarabertuldo/"><img alt="made by sara bertuldo" src="./images/madebysb.png"></a>
  </div>
</template>

<script>
import TodoList from './components/TodoList.vue'

export default {
  name: 'App',
  components: {
    TodoList
  }
}
</script>

<style>

* {
  box-sizing: border-box;
}

.container {
  max-width: 600px;
  margin: 0 auto;
}

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>

<template>
  <div id="app">
    <h1>My Todo App!</h1>
    <todo-list></todo-list>
    <router-view />
  </div>
</template>

<script>
import TodoList from "./components/TodoList.vue";
export default {
  components: {
    TodoList
  }
};
</script>
<style lang="scss">
*,
*::before,
*::after {
  box-sizing: border-box;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
h1 {
  text-align: center;
}
</style>

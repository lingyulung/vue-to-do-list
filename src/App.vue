<script>
  import Input from "./components/Input.vue"
  import List from "./components/List.vue";

  export default {
    components: {
      Input,
      List
    },
    data() {
      return {
        list: []
      }
    }
  }
  
</script>

<template>
  <div class="appContainer">
  <h1>My To-Do List</h1>
  <Input @toDo="(item) => list.push(item)" />
    <List :list="list" />
  </div>
</template>

<style>
  .appContainer {
    width: 80vw;
  }
</style>
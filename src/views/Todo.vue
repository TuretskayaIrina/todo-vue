<template>
  <div class="todo">
    <h1 class="todo__title">ToDo</h1>
    <form class="todo__form">
      <label class="todo__label" for="createTodo">New ToDo</label>
      <input
        class="todo__input"
        id="createTodo"
        type="text"
        placeholder="Enter task..."
        autocomplete="off"
        v-model="newTodo"
      >
      <button class="todo__botton" v-on:click="addTodo">+</button>
    </form>

    <h2 class="todo__subtitle"></h2>
    <ul class="todo__list">
      <li class="todo__item">
        <span class="todo__item-span"></span>
        <button class="todo__item-bth" v-on:click="removeTodo">done</button>
      </li>
    </ul>
    <p class="todo__list-discription">task list is empty &#128077;</p>
  </div>
</template>

<script>
export default {
  data() {
    return {
      newTodo: '',
    };
  },
  methods: {
    addTodo() {
      console.log('add');
    },

    removeTodo() {
      console.log('remove');
    },
  },
};
</script>

<style lang="css" scoped>
  .todo {

  }
  .todo__title {

  }
  .todo__form {

  }
  .todo__label {

  }
  .todo__input {

  }
  .todo__botton {

  }
  .todo__subtitle {

  }
  .todo__list {

  }
  .todo__item {

  }
  .todo__item-span {

  }
  .todo__item-bth {

  }
  .todo__list-discription {

  }
</style>

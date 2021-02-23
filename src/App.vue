<template>
  <div class="todo">
    <h1 class="todo__title">ToDo</h1>
    <form id="formTodo" class="todo__form" @submit.prevent="addTodo">
      <input
        class="todo__input"
        id="createTodo"
        type="text"
        placeholder="Enter task..."
        autocomplete="off"
        v-model="newTodo"
        name="newTodo"
        required
      >
      <button class="todo__botton">+</button>
    </form>

    <h2 class="todo__subtitle">Your to-do list</h2>
    <ul class="todo__list">
      <li class="todo__item" v-for="(todo, index) in todos" :key="index">
        <p class="todo__item-description">{{ todo.description }}</p>
        <button class="todo__item-bth" @click="removeTodo(todo)">&#10004;</button>
      </li>
    </ul>
    <p v-if="todos.length === 0" class="todo__list-discription">
      Everything is done for today &#128077;
    </p>
  </div>
</template>

<script>
export default {
  data() {
    return {
      newTodo: '',
      todos: [
        {
          description: 'test',
        },
      ],
    };
  },
  methods: {
    addTodo(e) {
      this.todos.push({
        description: this.newTodo,
      });
      this.newTodo = '';
      e.target.reset();
    },
    removeTodo(deletedTodo) {
      this.todos = this.todos.filter((todo) => todo !== deletedTodo);
    },
  },
};
</script>

<style>
  .todo {
    display: flex;
    flex-direction: column;
    align-items: center;
    width: 90%;
    margin: 0 auto;
    color: white;
  }

  .todo__title {}

  .todo__form {
    width: 100%;
    display: flex;
    justify-content: space-between;
  }

  .todo__input {
    padding: 10px 15px;
    border: none;
    border-bottom: 1px solid white;
    width: 100%;
    background: none;
    color: white;
  }

  .todo__botton {
    background: none;
    border: none;
    font-size: 40px;
    line-height: 1;
    color: white;
    padding: 0 10px;
    border-bottom: 1px solid white;
  }

  .todo__botton:hover {
    cursor: pointer;
    color: rebeccapurple;
  }

  .todo__subtitle {}

  .todo__list {
    list-style-type: none;
    margin: 0;
    padding: 0;
    width: 100%;
  }

  .todo__item {
    display: flex;
    justify-content: space-between;
    margin-bottom: 5px;
    border-bottom: 1px dotted;
  }

  .todo__item-description {
    margin: 0;
    word-break: break-word;
    white-space: nowrap;
    overflow: hidden;
    text-overflow: ellipsis;
  }

  .todo__item-bth {
    background: none;
    border: 1px dotted;
    color: white;
  }

  .todo__item-bth:hover {
    cursor: pointer;
    border: 1px solid;
  }

  .todo__list-discription {}
</style>

<template>
  <div>
    <h1>Todoリスト</h1>
    <todo-form @handleParentAddTodo="handleParentAddTodo" />
    <todo-list
      :todos="todos"
      @handleParentDeleteTodo="handleParentDeleteTodo"
      @handleParentCompleteTodo="handleParentCompleteTodo"
    />
  </div>
</template>

<script>
/* eslint-disable */
import TodoForm from "@/components/TodoForm";
import TodoList from "@/components/TodoList";

export default {
  name: "Todo",
  components: {
    TodoForm,
    TodoList
  },
  data() {
    return {
      todos: []
    };
  },
  methods: {
    handleParentAddTodo(value) {
      if (value) {
        this.todos.unshift({ text: value, complete: false });
      }
    },
    handleParentDeleteTodo(index) {
      this.todos.splice(index, 1);
    },
    handleParentCompleteTodo(index) {
      this.todos[index].complete = !this.todos[index].complete;
    }
  }
};
</script>

<style scoped></style>

<template>
  <b-container>
    <b-row :key="index" v-for="(todo, index) in todos" class="mt-2">
      <b-col cols="8" :class="[{ line: todo.complete }, 'text-start']">
        <h5>{{ todo.text }}</h5>
      </b-col>
      <b-col cols="4" class="text-end">
        <b-button
          @click="handleCompleteTodo(index)"
          :variant="todo.complete ? '' : 'success'"
        >
          {{ todo.complete ? "完了" : "未完了" }}
        </b-button>
        <b-button @click="handleDeleteTodo(index)" variant="danger"
          >削除</b-button
        >
      </b-col>
    </b-row>
  </b-container>
</template>

<script>
/* eslint-disable */
export default {
  name: "TodoList",
  props: ["todos"],
  methods: {
    handleDeleteTodo(index) {
      this.$emit("handleParentDeleteTodo", index);
    },
    handleCompleteTodo(index) {
      this.$emit("handleParentCompleteTodo", index);
    }
  }
};
</script>

<style scoped>
.line {
  text-decoration: line-through;
}
</style>

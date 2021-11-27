<template>
  <b-container>
    <b-input-group>
      <b-form-input type="text" v-model="value" />
      <b-input-group-append>
        <b-button variant="info" @click="handleAddTodo()">送信</b-button>
      </b-input-group-append>
    </b-input-group>
  </b-container>
</template>

<script>
/* eslint-disable */
export default {
  name: "TodoForm",
  data() {
    return {
      value: ""
    };
  },
  methods: {
    handleAddTodo() {
      this.$emit("handleParentAddTodo", this.value);
      this.value = "";
    }
  }
};
</script>

<style scoped></style>

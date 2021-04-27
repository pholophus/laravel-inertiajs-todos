<template>
  <app-layout>
    <template #header>
      <h2 class="font-semibold text-xl text-gray-800 leading-tight">Todo</h2>
    </template>

    <todo-form />
    <todo-list :tasks="tasks" />
  </app-layout>
</template>

<script>
import AppLayout from "@/Layouts/AppLayout";
import TodoForm from "./TodoForm.vue";
import TodoList from "./TodoList.vue";

export default {
  components: {
    AppLayout,
    TodoForm,
    TodoList,
  },
  props: {
    tasks: Array,
  },
};
</script>

    TodoForm

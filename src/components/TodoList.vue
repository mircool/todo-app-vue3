<template>
  <div class="todo-list">
    <!-- todo 项目，外层容器用于显示背景、圆角边框 -->
    <TodoListItem
        v-for="todo in todos"
        :key="todo.id"
        v-bind="todo"
        @change-state="todo.completed = $event.target.checked"
    >
    </TodoListItem>

  </div>
</template>

<script setup>
import {defineProps} from "vue";
import TodoListItem from "@/components/TodoListItem.vue";

defineProps(["todos"]);
</script>

<style scoped>

.todo-list {
  display: grid;
  row-gap: 14px;
}

</style>
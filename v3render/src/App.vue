<template>
  <div class="app-container">
    <todo-list></todo-list>
    <todo-list-jsx></todo-list-jsx>
  </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue'
import TodoList from '@/components/TodoList.vue'
import TodoListJsx from '@/components/TodoListJsx.vue'

export default defineComponent({
    name: 'App',
    components: {
        TodoList,
        TodoListJsx,
    }
})
</script>

<style>
.app-container {
  display: flex;
  flex-direction: row;
  justify-content: space-around;
  padding: 20px;

}

</style>

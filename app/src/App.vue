<script setup lang="ts">
import AppHeader from './components/AppHeader.vue';
import TodoList from './components/TodoList.vue';
</script>

<template>
  <AppHeader/>
  <TodoList/>
</template>

<style scoped>
header {
  line-height: 1.5;
}



@media (min-width: 1024px) {
  header {
    display: flex;
    place-items: center;
    padding-right: calc(var(--section-gap) / 2);
  }

 
}
</style>

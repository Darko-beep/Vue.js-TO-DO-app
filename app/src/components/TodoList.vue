<script lang="ts" setup>
// Import the 'ref' function to create reactive state
import { ref } from 'vue'

// Import the 'Ref' type for TypeScript typing of reactive variables
import type { Ref } from 'vue'

// Import the ListItem component (assumed to be a presentational component)
import ListItem from './ListItem.vue'

// Define a TypeScript type for individual items in the list
type Item = {
  title: string // Title or label of the task
  checked?: boolean // Optional boolean indicating if task is completed
}

// Define a reactive list of items using ref() and type annotation
const listItems: Ref<Item[]> = ref([
  { title: 'make an app', checked: true },
  { title: 'go for a vacation', checked: false },
  { title: 'attend lectures', checked: false },
  { title: 'Organize a program', checked: false },
])

const updateItem = (item: Item): void => {
  const updatedItem = findItemInList(item)
  if (updatedItem) {
    toggleItemChecked(updatedItem)
  }
}
const findItemInList = (item: Item): Item | undefined => {
  return listItems.value.find((itemInList: Item) => itemInList.title === item.title)
}
const toggleItemChecked = (item: Item): void => {
  item.checked = !item.checked
}
</script>

<template>
  <ul>
    <li :key="key" v-for="(item, key) in listItems">
      <ListItem :is-checked="item.checked" v-on:click.prevent="updateItem(item)">{{
        item.title
      }}</ListItem>
    </li>
  </ul>
</template>

<style scoped>
ul {
  list-style: none;
}
li {
  margin: 0.4rem 0;
}
</style>

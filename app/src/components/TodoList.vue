<script lang="ts" setup>
import ListItem from './ListItem.vue';

type Item={
    title:string,
    checked?: boolean
}
const ListItems: Item[]=[
    {
        title:"make an app",
        checked:true
    },
    {
        title:"go for a vacation",
        checked:false
    },
    {
        title:"attend lectures ",
        checked:false
    },
    {
        title:"Organize a program",
        checked:false
    }
]
</script>

<template>
    <ul>
        <li :key="key" 
        v-for="(item,key) in ListItems "
        >
        <ListItem :is-checked="item.checked">{{item.title}}</ListItem>

        </li>
    </ul>
</template>

<style scoped>
ul{
    list-style: none;
}
li{
    margin: 0.4rem 0;
}
</style>
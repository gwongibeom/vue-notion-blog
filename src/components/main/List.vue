<template>
  <ul>
    <li v-for="post of list" key="post.id">
      <span>[{{ post.category }}] </span>
      <span>{{ post.title }}</span>
    </li>
  </ul>
</template>

<script setup>
import { ref } from 'vue'
import { getPageTable } from 'vue-notion'

const list = ref([])

getPageTable('a42275a32e4a4277ac22165d9404e4ab').then((value) => {
  list.value = value
})
</script>
<style scoped>
li {
  list-style-type: none;
  text-decoration: underline;
  text-underline-offset: 5px;
  margin-bottom: 0.5rem;
}
</style>

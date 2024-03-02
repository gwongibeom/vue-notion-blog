<template>
  <main>
    <button @click="name = 'List'">List</button>
    <button @click="name = 'Post'">Post</button>
    <component :is="comp[name]" />
  </main>
</template>

<script setup>
import { ref, defineAsyncComponent } from 'vue'

const name = ref('')

const List = defineAsyncComponent(() => import('@/components/main/List.vue'))
const Post = defineAsyncComponent(() => import('@/components/main/Post.vue'))

const comp = { List, Post }
</script>

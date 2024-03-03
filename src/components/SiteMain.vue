<template>
  <main>
    <button @click="name = 'List'">List</button>
    <button @click="name = 'Post'">Post</button>
    <List v-if="name == 'List'" />
    <Post v-if="name == 'Post'" :postId="id" />
  </main>
</template>

<script setup>
import { ref, defineAsyncComponent } from 'vue'

const name = ref('')
const id = ref('b37bedee3cea4ad491d2e8f9bf8f48c0')

const List = defineAsyncComponent(() => import('@/components/main/List.vue'))
const Post = defineAsyncComponent(() => import('@/components/main/Post.vue'))

const comp = { List, Post }
</script>

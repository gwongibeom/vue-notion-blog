<template>
  <main>
    <List
      v-if="name == 'List'"
      @changeId="
        (newId) => {
          id = newId;
        }
      "
      :keyword="keyword"
    />
    <Post v-if="name == 'Post'" :BlockId="id" />
  </main>
</template>

<script setup>
import { ref, defineAsyncComponent, inject } from 'vue';

const { name } = inject('name');
defineProps(['keyword']);

const id = ref('b37bedee3cea4ad491d2e8f9bf8f48c0');

const List = defineAsyncComponent(() => import('@/components/main/List.vue'));
const Post = defineAsyncComponent(() => import('@/components/main/Post.vue'));

const comp = { List, Post };
</script>

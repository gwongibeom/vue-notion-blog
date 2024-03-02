<template>
  <NotionRenderer :blockMap="blockMap" fullPage />
</template>

<script setup>
import { ref } from 'vue'
import { getPageBlocks, NotionRenderer } from 'vue-notion'

const blockMap = ref(null)

getPageBlocks('b37bedee3cea4ad491d2e8f9bf8f48c0').then((value) => {
  blockMap.value = value
})
</script>
<style>
/* optional Notion-like styles */
@import 'vue-notion/src/styles.css';
</style>

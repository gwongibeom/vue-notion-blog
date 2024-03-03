<template>
  <NotionRenderer :blockMap="blockMap" fullPage />
</template>

<script setup>
import { ref } from 'vue'
import { getPageBlocks, NotionRenderer } from 'vue-notion'

const props = defineProps({
  BlockId: {
    required: true,
    type: String,
  },
})

const blockMap = ref(null)

getPageBlocks(props.BlockId).then((value) => {
  blockMap.value = value
})
</script>

<style>
/* optional Notion-like styles */
@import 'vue-notion/src/styles.css';
</style>

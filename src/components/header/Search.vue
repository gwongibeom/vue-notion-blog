<template>
  <input ref="search" />
</template>

<script>
import { onMounted, ref } from 'vue'

export default {
  setup() {
    const search = ref(null)

    onMounted(() => {
      search.value.focus()
    })
    return {
      search,
    }
  },
}
</script>

<style scoped>
input {
  margin-top: 1rem;
}
</style>

<template>
  <ul>
    <li
      v-for="post of filteredList"
      key="post.id"
      @click="$emit('changeId', post.id)"
    >
      <span>{{ post.category }}</span>
      <span>{{ post.title }}</span>
    </li>
  </ul>
</template>

<script setup>
import { ref, computed } from 'vue'
import { getPageTable } from 'vue-notion'

const list = ref([])
const props = defineProps(['category'])

const filteredList = computed(() => {
  if (props.category == '') {
    return list.value
  } else {
    const result = []
    for (const item of list.value) {
      if (item.category == props.category) {
        result.push(item)
      }
    }
    return result
  }
})

getPageTable('a42275a32e4a4277ac22165d9404e4ab').then((value) => {
  list.value = value
})
</script>
<style scoped>
li {
  list-style-type: none;
  margin-bottom: 0.5rem;
  margin-bottom: 1rem;
  cursor: pointer;
}

li span:nth-child(1) {
  background-color: #191919;
  color: #fff;
  margin-right: 5px;
  padding: 6px 10px;
  border-radius: 4px;
}
li span:nth-child(2) {
  font-weight: bold;
  text-decoration: underline 0.15em rgba(0, 0, 0, 0);
  text-underline-offset: 2px;
  transition: text-decoration-color 444ms, text-underline-offset 444ms;
}

li span:nth-child(2):hover {
  text-decoration-color: rgb(0, 0, 0, 1);
  text-underline-offset: 4px;
}
</style>

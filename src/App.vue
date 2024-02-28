<template>
  <SiteHeader />
  <div v-show="isLoading" class="my_loader">
    <Loading />
  </div>
</template>

<script setup>
import SiteHeader from './components/SiteHeader.vue'
import Loading from './components/Loading.vue'
import { onMounted, ref } from 'vue'

const isLoading = ref(true)

onMounted(() => {
  setTimeout(() => {
    isLoading.value = false
  }, 2000)
})
</script>

<style>
.my_loader {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background-color: rgba(0, 0, 0, 0.3);

  display: flex;
  justify-content: center;
  align-items: center;
}
</style>

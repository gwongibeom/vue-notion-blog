<template>
  <SiteHeader @change-category="changeCategory" />
  <SiteMain :name="name" :category="category" @change-id="name = 'Post'" />
  <SiteFooter />
  <div v-show="isLoading" class="my_loader">
    <Loading />
  </div>
</template>

<script setup>
import SiteHeader from './components/SiteHeader.vue'
import Loading from './components/Loading.vue'
import SiteMain from './components/SiteMain.vue'
import { onMounted, ref } from 'vue'
import SiteFooter from './components/SiteFooter.vue'

const isLoading = ref(true)
const name = ref('List')
const category = ref('')

const changeCategory = function (newCate) {
  name.value = 'List'
  category.value = newCate
}

onMounted(() => {
  setTimeout(() => {
    isLoading.value = false
  }, 0)
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

main {
  width: 80%;
  margin: 10px auto;
}
</style>

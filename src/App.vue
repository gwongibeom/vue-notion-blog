<template>
  <SiteHeader v-model="keyword" />
  <SiteMain :keyword="keyword" />
  <SiteFooter />
  <div v-show="isLoading" class="my_loader">
    <Loading />
  </div>
</template>

<script setup>
import { onMounted, ref, provide } from 'vue';
import SiteHeader from './components/SiteHeader.vue';
import SiteMain from './components/SiteMain.vue';
import SiteFooter from './components/SiteFooter.vue';
import Loading from './components/Loading.vue';

const isLoading = ref(true);
const name = ref('List');
const category = ref('');
const keyword = ref('');

provide('name', {
  name,
  updateName(newName) {
    name.value = newName;
  },
});

provide('category', {
  category,
  updateCategory(newCate) {
    category.value = newCate;
  },
});

onMounted(() => {
  setTimeout(() => {
    isLoading.value = false;
  }, 0);
});
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

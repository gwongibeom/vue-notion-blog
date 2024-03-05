<template>
  <div class="search">
    <img src="@/assets/search.svg" />

    <input
      placeholder="Search"
      :value="search"
      @input="
        if (searchModifiers?.trim) {
          $emit('update:search', $event.target.value.trim());
        } else {
          $emit('update:search', $event.target.value);
        }
      "
    />
  </div>
</template>

<script setup>
defineProps(['search', 'searchModifiers']);
defineEmits(['update:search']);
</script>

<style scoped>
.search {
  display: flex;
  justify-items: start;
  align-items: center;
  margin-top: 1rem;
  border: 1px solid #191919;
  padding: 2px 6px;
}

img {
  height: 16px;
}

input {
  border: 0;
}
</style>

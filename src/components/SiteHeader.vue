<template>
  <header>
    <img src="@/assets/profile_normal.png" class="profile_pic" />
    <nav>
      <a v-for="item of menu" key="item">{{ item }}</a>
    </nav>
  </header>
</template>

<script setup>
const menu = ['개발', '일상']
</script>

<style scoped>
header {
  display: flex;
  flex-direction: column;
  align-items: center;
}

nav {
  display: flex;
  gap: 0.3rem;
  margin-top: 1rem;
  background-color: #191919;
  padding: 0.8rem;
  border-radius: 9px;
}

nav a {
  color: #fff;
  cursor: pointer;
  font-weight: bold;
}

.profile_pic {
  width: 6rem;
  min-width: 180px;
  border-radius: 100vh;
  border: solid #191919 3px;
}
</style>

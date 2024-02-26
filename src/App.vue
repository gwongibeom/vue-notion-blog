<template>
  <SiteHeader />
  <SiteMain />
  <SiteFooter />
</template>

<script>
import SiteHeader from './components/SiteHeader.vue'
import SiteMain from './components/SiteMain.vue'
import SiteFooter from './components/SiteFooter.vue'

export default {
  components: { SiteHeader, SiteMain, SiteFooter },
}
</script>

<style>
h2 {
  color: red;
}
</style>

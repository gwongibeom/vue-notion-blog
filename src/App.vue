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
@import url('https://cdn.jsdelivr.net/gh/orioncactus/pretendard@v1.3.8/dist/web/variable/pretendardvariable-dynamic-subset.css');
:root {
  font-family: Pretendard Variable;
  font-weight: 400;

  color-scheme: light dark;
  color: #191919;
  background-color: #fff;

  font-synthesis: none;
  text-rendering: optimizeLegibility;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  -webkit-text-size-adjust: 100%;
}
</style>

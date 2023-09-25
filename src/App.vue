<script setup>
import { RouterView } from 'vue-router'
import PageHeader from './components/PageHeader.vue'
import PageFooter from './components/PageFooter.vue'
</script>

<template>
  <header class="pageHeader">
    <page-header></page-header>
  </header>
  <RouterView />
  <footer class="pageFooter">
    <page-footer></page-footer>
  </footer>
</template>

<style scoped>
.pageHeader {
  display: grid;
  align-items: center;
  justify-items: center;
  min-height: 100px;
}
.pageFooter {
  display: grid;
  align-items: center;
  justify-items: center;
  min-height: 150px;

}
</style>

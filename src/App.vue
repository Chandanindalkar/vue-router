<script setup>
import { RouterView } from 'vue-router'
import Nav from './components/Nav.vue'

</script>

<template>
  {{ somestate }}
  <div>
    <Nav />
    <RouterView /> 
  </div>
</template>

<style scoped>

</style>
<template>
  <Navbar />
  <router-view/>
</template>

<script>
import Navbar from './components/Navbar.vue'

export default {
  components: {
    Navbar
  }
}
</script>

<style>
html, body{
  padding: 0;
  margin: 0;
  color: black;
}
</style>

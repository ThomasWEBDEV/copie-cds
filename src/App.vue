<template>
  <v-app style="background-color: #07080c;">
    <v-main class="pa-0">
      <Login />
    </v-main>
  </v-app>
</template>

<script>
import Login from './components/Login.vue'

export default {
  name: 'App',
  components: {
    Login
  }
}
</script>

<style>
html, body {
  margin: 0;
  padding: 0;
  background-color: #07080c !important;
  font-family: 'Inter', -apple-system, BlinkMacSystemFont, sans-serif;
  overflow: hidden;
}
</style>

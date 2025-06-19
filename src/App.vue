<template>
  <div id="app">
    <!-- Renders the current route's view -->
    <router-view />
  </div>
</template>

<script>
export default {
  name: 'App'
}
</script>

<style>
/* Global resets for consistent layout */
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

html, body, #app {
  height: 100%;
  width: 100%;
  font-family: 'Segoe UI', sans-serif;
}
</style>

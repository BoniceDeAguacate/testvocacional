<template>
  <div id="app">
    <TestVocacional />
  </div>
</template>

<script>
import TestVocacional from './components/TestVocacional.vue'

export default {
  name: 'App',
  components: {
    TestVocacional
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  background: linear-gradient(135deg, #f5f7fa 0%, #c3cfe2 100%);
  min-height: 100vh;
  padding: 20px 0;
}

* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

body {
  margin: 0;
}
</style>

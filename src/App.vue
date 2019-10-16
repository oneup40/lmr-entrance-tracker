<template>
  <div id="app">
    <lmr-entrance-tracker/>
  </div>
</template>

<script>
import LMREntranceTracker from './components/LMREntranceTracker.vue'

export default {
  name: 'app',
  components: {
    'lmr-entrance-tracker': LMREntranceTracker
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>

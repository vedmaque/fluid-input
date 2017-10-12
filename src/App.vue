<template>
  <div id="app">
    <h2>Input with moving currency after value</h2>
    <FluidInput />
  </div>
</template>

<script>
import FluidInput from './components/FluidInput'

export default {
  name: 'app',
  components: {
    FluidInput
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
}
</style>

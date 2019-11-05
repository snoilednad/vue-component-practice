<template>
  <div id="app">
    <h-input v-model="inputVal"></h-input>
  </div>
</template>

<script>
import HInput from './components/HInput.vue'
export default {
  name: 'app',
  components: {
    HInput
  },
  data () {
    return {
      inputVal: '1000'
    }
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

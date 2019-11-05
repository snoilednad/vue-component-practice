<template>
  <div id="app">
    <h-form-item label="用户名">
      <h-input v-model="form.userName"></h-input>
    </h-form-item>
    <h-form-item label="密码">
      <h-input v-model="form.password" type="password"></h-input>
    </h-form-item>
  </div>
</template>

<script>
import HFormItem from './components/HFormItem.vue'
import HInput from './components/HInput.vue'
export default {
  name: 'app',
  components: {
    HFormItem,
    HInput
  },
  data () {
    return {
      form: {
        userName: 'snoilednad',
        password: '123456'
      }
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

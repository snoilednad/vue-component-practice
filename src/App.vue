<template>
  <div id="app">
    <h-form :model="form" :rules="rules" ref="loginForm">
      <h-form-item label="用户名" prop="userName">
        <h-input v-model="form.userName"></h-input>
      </h-form-item>
      <h-form-item label="密码" prop="password">
        <h-input v-model="form.password" type="password"></h-input>
      </h-form-item>
      <h-form-item>
        <button @click="submitForm">登录</button>
      </h-form-item>
    </h-form>
  </div>
</template>

<script>
  import HForm from './components/HForm.vue'
  import HFormItem from './components/HFormItem.vue'
  import HInput from './components/HInput.vue'
  export default {
    name: 'app',
    components: {
      HForm,
      HFormItem,
      HInput
    },
    data () {
      return {
        form: {
          userName: '',
          password: ''
        },
        rules: {
          userName: [{required: true, message: '请输入用户名'}],
          password: [{required: true, message: '请输入密码'}]
        }
      }
    },
    methods: {
      submitForm () {
        this.$refs['loginForm'].validate((valid) => {
          console.log(valid, 'valid')
          if (valid) {
            console.log('请求登录')
          } else {
            console.log('校验失败')
          }
        })
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

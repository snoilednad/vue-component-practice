<template>
  <div>
    <slot></slot>
  </div>
</template>
<script>
  export default {
    provide() {
      return {
        form: this
      }
    },
    props: {
      model: Object,
      rules: Object // 规则
    },
    data () {
      return {
      }
    },
    created () {
    },
    methods: {
      validate (cb) { // 全局校验
        const validates = this.$children
          .filter(item => item.prop) // 过滤掉不存在prop的，例如button
          .map(item => item.validate())
        Promise.all(validates)
          .then(() => cb(true)) // 校验成功返回true
          .catch(() => cb(false)) // 校验失败返回false
      }
    }
  }
</script>
<style scoped lang="scss">
</style>

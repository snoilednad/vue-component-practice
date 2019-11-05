<template>
  <div>
    <span v-if="label">{{label}}</span>
    <slot></slot>
    <p style="color: red;" v-if="errMsg">{{errMsg}}</p>
  </div>
</template>
<script>
export default {
  props: {
    label: {
      type: String,
      default: ''
    }
  },
  components: {
  },
  data () {
    return {
      errMsg: '' // 错误信息
    }
  },
  created () {
  },
  methods: {}
}
</script>
<style scoped lang="scss">
</style>

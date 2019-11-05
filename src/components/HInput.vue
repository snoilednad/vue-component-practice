<template>
  <input :value="$attrs.value" @input="handleInput" v-bind="$attrs"/>
</template>

<script>
  export default {
    name: 'HInput',
    methods: {
      handleInput (e) {
        this.$emit('input', e.target.value)
        // 当值变化时，通知校验。注意：谁触发，谁监听
        this.$parent.$emit('validate')
      }
    }
  }
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
</style>

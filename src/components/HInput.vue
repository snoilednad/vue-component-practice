<template>
  <input :value="$attrs.value" @input="handleInput" v-bind="$attrs"/>
</template>

<script>
export default {
  name: 'HInput',
  methods: {
    handleInput (e) {
      this.$emit('input', e.target.value)
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
</style>

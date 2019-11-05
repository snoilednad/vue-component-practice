<template>
  <div>
    <span v-if="label">{{label}}</span>
    <slot></slot>
    <p style="color: red;" v-if="errMsg">{{errMsg}}</p>
  </div>
</template>
<script>
  import Schema from 'async-validator'
  export default {
    inject: ['form'], // 注入，由HForm提供
    props: {
      label: {
        type: String,
        default: ''
      },
      prop: { // 字段属性名
        type: String,
        default: ''
      }
    },
    data () {
      return {
        errMsg: '' // 错误信息
      }
    },
    mounted () {
      // 实时校验
      this.$on('validate', () => {
        this.validate()
      })
    },
    methods: {
      validate () { // 对每个formItem进行校验
        // 当前属性名
        const attr = this.prop
        // 获取对应formItem的校验规则
        const currentRule = this.form.rules[attr]
        // 获取校验值
        const currentValue = this.form.model[attr]
        // 获取校验描述对象
        const descriptor = {[attr]: currentRule}
        // 创建校验器
        const schema = new Schema(descriptor)
        return schema.validate({[attr]: currentValue}, error => {
          if (error) {
            this.errMsg = error[0].message
          } else { // 校验通过
            this.errMsg = ''
          }
        })
      }
    }
  }
</script>
<style scoped lang="scss">
</style>

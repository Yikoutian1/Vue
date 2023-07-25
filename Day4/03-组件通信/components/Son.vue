<template>
  <div class="son" style="border:3px solid #000;margin:10px">
    <!-- 3.直接使用props的值 -->
    我是Son组件 {{ title }}
    <button @click="changeFn">修改title</button>
  </div>
</template>

<script>
export default {
  name: 'Son-Child',
  // 父传子  props
  // 2.通过props来接受(数组可以接收多个值)
  props: ['title'], // 这里接收的是渲染title的值
  // 子传父
  methods: {
    changeFn(){
      // 1.$emit触发事件,给父组件发送消息通知
      //             事件名       value
      this.$emit('changeTitle','改变的值')
    }
  },
}
</script>

<style>

</style>
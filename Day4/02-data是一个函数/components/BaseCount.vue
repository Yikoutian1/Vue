<template>
  <div class="base-count">
    <button @click="count--">-</button>
    <span>{{ count }}</span>
    <button @click="count++">+</button>
  </div>
</template>

<script>
export default {
  // data必须为一个函数，保证每个组件实例，维护独立
  data() {
    return {
      count: 100,
    }
  },
}
</script>

<!--
   scoped原理：
   1.给当前组件模板的所有元素，都会添加一个自定义的属性
      data-v-hash 值
      例如data-v-45d6w9fd 来区分不同的组件
   2.css选择器的后面，被自动处理，添加上了属性选择器
      div[data-v-45d6w9fd]
-->
<style scoped>
.base-count {
  margin: 20px;
}
</style>
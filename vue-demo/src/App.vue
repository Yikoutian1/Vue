<template>
  <div>
    <h1 v-color="red">指令的值1测试</h1>
    <h1 v-color="blue">指令的值2测试</h1>
  </div>
</template>

<script>
export default {
  data() {
    return {
      red: 'red',
      blue: 'blue'
    };
  },
  directives: {
    color:{
      // 1. inserted 提供的是元素被添加到页面时添加（后续在修改网页的时候不会触发）
      inserted(el,binding){
        // binding.value 就是指令的值
        el.style.color = binding.value
      },
      // 2. update 指令的值修改的时候触发，提供值变化后，dom更新的逻辑
      // 在网页实例（F12切换vue）
      update(el,binding){
        el.style.color = binding.value
      }
    }
  },
};
</script>

<style></style>

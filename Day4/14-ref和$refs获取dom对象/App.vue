<template>
  <div class="app">
    <!-- 
      如果使用的是document.querySelector的话,
      这个class与子类同名,
      则会选择第一个匹配的 
    -->
    <div class="base-chart-box">
      这是一个捣乱的盒子
    </div>
    <BaseChart></BaseChart>
  </div>
</template>

<script>
import BaseChart from './components/BaseChart.vue'
export default {
  components:{
    BaseChart
  }
}
</script>

<style>
.base-chart-box {
  width: 200px;
  height: 100px;
}
</style>
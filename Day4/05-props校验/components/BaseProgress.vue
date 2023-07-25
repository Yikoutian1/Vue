<template>
  <div class="base-progress">
    <div class="inner" :style="{ width: w + '%' }">
      <span>{{ w }}%</span>
    </div>
  </div>
</template>

<script>
export default {
  // props: ["w"],

  // 1.基础写法（类型校验）对象的写法   !!最常用的!!
  // props: {
  //   w: Number // Number String Boolean ...类型约束
  // }
  // 2.完整写法（类型、是否必填、默认值、自定义校验）
  props: {
    w: {
      // 属性
      type: Number, // 需求属性
      required: true, // 必须true
      default: 0, // 默认设置值
      validator(value) {
        // 自定义校验逻辑
        if (value >= 0 && value <= 100) {
          return true;
        } else {
          console.log("传入的prop w,必须在0-100的范围内");
          return false;
        }
      },
    },
  },
};
</script>

<style scoped>
.base-progress {
  height: 26px;
  width: 400px;
  border-radius: 15px;
  background-color: #272425;
  border: 3px solid #272425;
  box-sizing: border-box;
  margin-bottom: 30px;
}
.inner {
  position: relative;
  background: #379bff;
  border-radius: 15px;
  height: 25px;
  box-sizing: border-box;
  left: -3px;
  top: -2px;
}
.inner span {
  position: absolute;
  right: 0;
  top: 26px;
}
</style>

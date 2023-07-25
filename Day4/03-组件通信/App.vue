<template>
  <div class="app" style="border: 3px solid #000; margin: 10px">
    我是APP组件
    <!-- 1.给组件标签，添加属性方式 赋值 -->
    <!-- 父组件对消息进行监听 -->
    <Son :title="myTitle" @changeTitle="handleChange"></Son>
    <!-- 这个时候 son的titleName已经修改了 -->
  </div>
</template>

<script>
import Son from "./components/Son.vue";
export default {
  name: "App",
  components: {
    Son,
  },
  data() {
    return {
      myTitle: "这是传递的值",
    };
  },
  methods: {
    // 提供对应的处理函数
    handleChange(newTitle) {
      this.myTitle = newTitle;
    },
  },
};
</script>

<style></style>

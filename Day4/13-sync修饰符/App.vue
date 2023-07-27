<template>
  <div class="app">
    <button @click="isShow = true">退出按钮</button>
    <!-- .sync   -->
    <!-- 
          :visible.sync="isShow"
  等价于:  :visible="isShow" @update.visible="isShow" = $event
     -->
    <BaseDialog :visible.sync="isShow"></BaseDialog>
    <!-- 传给子类(双向绑定) -->
  </div>
</template>

<script>
import BaseDialog from "./components/BaseDialog.vue";
export default {
  data() {
    return {
      isShow: false,
    };
  },
  methods: {},
  components: {
    BaseDialog,
  },
};
</script>

<style></style>

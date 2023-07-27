<template>
  <div class="app">
    <div v-if="isShowEdit">
      <input ref="inpt" type="text" v-model="editValue"/>
      <button>确认</button>
    </div>
    <div v-else>
      <span>{{ title }}</span>
      <button @click="handleEdit">编辑</button>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      title: "大标题",
      isShowEdit: false,
      editValue: "",
    };
  },
  methods: {
    /**
     * 想要在DOM跟新完成在做某事,用$nextTick
     */
    handleEdit() {
      // 显示输入框
      this.isShowEdit = true;
      // 让输入框获取焦点($nextTick等dom更新完,立刻执行下面语句)
      this.$nextTick(() => {
        this.$refs.inpt.focus();
      });
    },
  },
};
</script>

<style></style>

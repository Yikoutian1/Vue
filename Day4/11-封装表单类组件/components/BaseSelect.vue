<template>
  <div>
    <!-- 父传子 数据渲染 -->
    <select :value="cityId" @change="handleChange">
      <option value="101">北京</option>
      <option value="102">上海</option>
      <option value="103">武汉</option>
      <option value="104">广州</option>
      <option value="105">深圳</option>
    </select>
  </div>
</template>

<script>
export default {
  data() {
    return {
      selectId: "",
    };
  },
  props: {
    // 传输数据
    cityId: String,
  },
  methods: {
    handleChange(e) {
      this.$emit("change",e.target.value)
    },
  },
};
</script>

<style></style>

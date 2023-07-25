<template>
  <!-- 列表区域 -->
  <section class="main">
    <ul class="todo-list">
      <li v-for="(item, index) in list" :key="item.id" class="todo">
        <div class="view">
          <span class="index">{{ index + 1 }}.</span>
          <label>{{ item.name }}</label>
          <button @click="removeById(item.id)" class="destroy"></button>
        </div>
      </li>
    </ul>
  </section>
</template>

<script>
export default {
  data() {
    return {};
  },
  props: {
    list: Array,
  },
  methods: {
    removeById(id) {
      this.$emit("removeById",id);
    },
  },
};
</script>

<style></style>

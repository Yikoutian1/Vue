<template>
  <!-- 主体区域 -->
  <section id="app">
    <!-- 输入框 -->
    <TodoHeader @add="handleAdd"></TodoHeader>
    <!-- 列表区域 -->
    <TodeoMain @removeById="handleRemoveById" :list="list"></TodeoMain>
    <!-- 统计和清空 -->
    <TodoFooter @clear="handleClear" :list="list"></TodoFooter>
  </section>
</template>

<script>
// 导入
import TodoHeader from "./components/TodoHeader.vue";
import TodoFooter from "./components/TodoFooter.vue";
import TodeoMain from "./components/TodoMain.vue";
export default {
  // 注册
  components: {
    TodoHeader,
    TodoFooter,
    TodeoMain,
  },
  // 渲染
  // 1.提供数据 -> 提供在公共的父组件
  // 2.通过父传子,将数据传递给TodoMain
  // 3.利用v-for渲染
  data() {
    return {
      list: JSON.parse(localStorage.getItem('list')) || [
        { id: 1, name: "java" },
        { id: 2, name: "vue" },
        { id: 3, name: "spring" },
      ],
    };
  },
  methods: {
    handleAdd(todoName){
      this.list.unshift({
        id: new Date(),
        name: todoName
      })
    },
    handleClear(todoList){
      this.list = todoList
    },
    handleRemoveById(id){
      this.list = this.list.filter(item=>item.id !== id)
    }
  },
  watch:{
    list:{
      deep: true,
      handler(newValue){
        localStorage.setItem("list",JSON.stringify(newValue))
      }
    }
  }
};
</script>

<style></style>

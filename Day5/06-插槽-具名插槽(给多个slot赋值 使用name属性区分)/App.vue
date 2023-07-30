<template>
  <div>
    <MyDialog>
      <!-- 利用template标签 和v-slot:插槽NAME值 进行绑定-->
      <template v-slot:head>
        这是具名插槽的头部
      </template>
      <!-- 
        插槽名可以简写
        v-slot:插槽名  =>  #插槽名
      -->
      <template #content>
        这是具名插槽的内容
      </template>
      <template v-slot:footer>
        <button>具名插槽按钮</button>
        <button>确认</button>
        <button>取消</button>
      </template>
    </MyDialog>
  </div>
</template>

<script>
import MyDialog from './components/MyDialog.vue'
export default {
  data () {
    return {

    }
  },
  components: {
    MyDialog
  }
}
</script>

<style>
body {
  background-color: #b3b3b3;
}
</style>
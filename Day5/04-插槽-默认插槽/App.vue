<template>
  <div>
    <!--        在标签内部传入(可以在里面写div这些)       -->
    <MyDialog>你确认要退出本系统么？</MyDialog>
    <MyDialog>标签内部传入</MyDialog>
  </div>
</template>

<script>
import MyDialog from "./components/MyDialog.vue"
export default {
  data() {
    return {}
  },
  components: {
    MyDialog,
  },
}
</script>

<style>
body {
  background-color: #b3b3b3;
}
</style>
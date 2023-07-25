<template>
  <div class="app">
    <!-- 双向绑定 -->
    <input v-model="msg1" type="text" />
    <br />
    <!-- 单向绑定 :value="msg2" -->
    <!-- 双向绑定 :value="msg2" @input="msg2 = $event.target.value"-->

    <!-- 
      v-model 原理 :value="msg2" @input="msg2 = $event.target.value"
      从模板中获取事件的形参-> $event 获取 
     -->
    <input :value="msg2" @input="msg2 = $event.target.value" type="text" >
  </div>
</template>

<script>
export default {
  data() {
    return {
      msg1: '',
      msg2: ''
    }
  },
}
</script>

<style>
</style>
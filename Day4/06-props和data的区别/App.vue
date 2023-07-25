<template>
  <div class="app">
    <BaseCount
    :count="count"
    @changeCount = "handleChange"
    ></BaseCount>
  </div>
</template>

<script>
import BaseCount from './components/BaseCount.vue'
export default {
  components:{
    BaseCount
  },
  data(){
    return {
      count:666
    }
  },
  methods:{
    handleChange(newCount){
      this.count = newCount
    }
  }
}
</script>

<style>

</style>
<template>
  <div>
    <MyTable :data="this.list">
      <!-- 通过template #插槽名=“变量名” 接收刚刚传过来的变量 -->
      <template #default="obj">
        <div>
          <!--              对象.传过来的对象.属性 -->
          <button @click="del(obj.row.id)">删除</button>
        </div>
      </template>
    </MyTable>
    <MyTable :data="this.list2">
      <!-- 解构 -->
      <template #default="{ row }"> 
        <button @click="detail(row)">查看</button>
      </template>
    </MyTable>
  </div>
</template>

<script>
import MyTable from "./components/MyTable.vue";
export default {
  data() {
    return {
      list: [
        { id: 1, name: "张小花", age: 20 },
        { id: 2, name: "孙大明", age: 19 },
        { id: 3, name: "刘德忠", age: 18 },
      ],
      list2: [
        { id: 1, name: "赵小云", age: 22 },
        { id: 2, name: "刘蓓蓓", age: 34 },
        { id: 3, name: "姜肖泰", age: 18 },
      ],
    };
  },
  methods: {
    del(id) {
      this.list = this.list.filter((item) => item.id !== id);
    },
    detail(row){
      alert(row.id+row.name+row.age)
    }
  },
  components: {
    MyTable,
  },
};
</script>

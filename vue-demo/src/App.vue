<template>
  <div id="app">
    <div style="display: flex">
      <ul>
        <li v-for="item in heroes1" :key="item.id" @click="moveLeft(item)">{{ item.name }}</li>
      </ul>
      <div style="padding-top: 50px">
        <button @click="moveLeftAll()">←←</button>
        <br />
        <button @click="moveRightAll()">→→</button>
      </div>
      <ul>
        <li v-for="item in heroes2" :key="item.id" @click="moveRight(item)">{{ item.name }}</li>
      </ul>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      heroes1: [
        { id: 1, name: "林冲" },
        { id: 2, name: "武松" },
        { id: 3, name: "白胜" },
      ],
      heroes2: [
        { id: 1, name: "林冲" },
        { id: 2, name: "哈哈" },
      ],
    };
  },
  methods: {
    moveLeft(item) {
      this.heroes2.push(item);
      this.heroes1 = this.heroes1.filter((i) => i !== item);
    },
    moveRight(item) {
      this.heroes1.push(item);
      this.heroes2 = this.heroes2.filter((i) => i !== item);
    },
    moveLeftAll() {
      this.heroes2.forEach((item) => {
        this.heroes1.push(item);
      });
      this.heroes2 = [];
    },
    moveRightAll() {
      this.heroes1.forEach((item) => {
        this.heroes2.push(item);
      });
      this.heroes1 = [];
    },
  },
};
</script>

<style>
* {
  margin: 0px;
  padding: 0px;
  list-style: none;
}
ul {
  border: 1px solid #666;
  width: 100px;
  height: 200px;
  padding: 10px;
  margin: 10px;
}
li:hover {
  background-color: #beb4b4;
  cursor: pointer;
}
button {
  min-width: 20px;
}
</style>

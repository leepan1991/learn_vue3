<template>
  <div class="person">
    <h2>姓名：{{ name }}</h2>
    <h2>年龄：{{ age }}</h2>
    <button @click="changeName">修改名称</button>
    <button @click="changeAge">修改年龄</button>
    <button @click="showTel">查看联系方式</button>
  </div>

</template>

<script>
export default {
  name: "Person",
  data() {
    return {
      name: '张三',
      age: 18,
      tel: '1385525252'
    }
  },
  methods: {
    showTel() {
      alert(this.tel)
    },
    changeName() {
      this.name = 'zhang.san'
    },
    changeAge() {
      this.age += 1
    }
  }
}
</script>

<style scoped>
.person {
  background-color: #2c3e50;
  box-shadow: 0 0 10px;
  border-radius: 10px;
  padding: 20px;
}

button {
  margin: 5px;
}
</style>
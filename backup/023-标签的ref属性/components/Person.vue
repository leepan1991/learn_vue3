<template>
  <div class="person">
    <h2>中国</h2>
    <h2 ref="title2">北京</h2>
    <button @click="showLog">点我查看日志</button>
  </div>

</template>

<script lang="ts" setup name="Person">
import {ref} from "vue";

//数据
let title2 = ref()

//方法
function showLog() {
  console.log(title2.value)
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
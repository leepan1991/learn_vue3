<template>
  <div class="person">
    <h2>需求：当水温达到60度，或水位达到80cm时，给服务器发请求</h2>
    <h2>当前水温：{{ temp }}</h2>
    <h2>当前水位：{{ height }}</h2>
    <button @click="changeTemp">点我修改水温</button>
    <button @click="changeHeight">点我修改水位</button>
  </div>

</template>

<script lang="ts" setup name="Person">
import {ref, watch, watchEffect} from "vue";

//数据
let temp = ref(10)
let height = ref(0)

//方法
function changeTemp() {
  temp.value += 10
}

function changeHeight() {
  height.value += 10
}

/*监视，watch实现*/
// watch([temp, height], value => {
//   //从value中获取最新的水温newTemp，最新的水位newHeight
//   let [newTemp, newHeight] = value
//   //逻辑
//   if (newTemp >= 60 || newHeight >= 80) {
//     console.log('给服务器发送请求')
//   }
// })

/*监视，watchEffect实现*/
watchEffect(() => {
  if (temp.value >= 60 || height.value >= 80) {
    console.log('给服务器发请求')
  }
})


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
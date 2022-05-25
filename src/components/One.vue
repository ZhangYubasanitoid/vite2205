
<script >
import HelloWorld from './HelloWorld.vue'
 import {defineComponent, reactive, toRefs, onBeforeMount, onMounted } from 'vue'
export default defineComponent({
   provide:{
   age:'22323'
  },
  name: '',
  components:{
    HelloWorld
  },
setup() {
const state = reactive({
id:1,
list:[1,2,3,4,5]
})
const methods={
 change1(){
},
}
onMounted(() => {
})
return {
// toRefs转换为响应式数据
...toRefs(state),
...methods
}
}
})
</script>

<template>
  <div>
    <li v-for="(v,i) in list" :key="i"> {{v}} </li>
    one
  </div>
  <hr>
  <HelloWorld msg="Hello Vue 3 + Vite" />
 
</template>

<style scoped lang='less'>
</style>
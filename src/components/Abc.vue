<template>
  <div>
    <button @click="change1">14</button>
    <button v-if="show">666</button>
  </div>
</template>

<script >
import {defineComponent, reactive, toRefs, onMounted,watch,ref } from 'vue'
export default defineComponent({
  name: '',
  
setup() {
const state = reactive({
    id:1,
  show:true,
   obj1 : {
      name: "张三",
      age: 20,
      friend:{
        name:'李四',
        age:21
      }
    }
})
const methods={
 change1(){
   change_sum()
   state.show=!state.show
   state.obj1.age=50 
},
fn(){
  console.log(1);
  return '0'
}

}
 let sum = ref(0);
    function change_sum() {
      sum.value++
    }
     watch(sum, (newvalue, oldvalue) => {
      console.log(newvalue, oldvalue);
    });
watch(state.obj1, (newvalue, oldvalue) => {
    console.log(newvalue, oldvalue);
})
return {
// toRefs转换为响应式数据
...toRefs(state),
...methods,
 sum,
      change_sum,
}
}
})

</script>
<style scoped lang='less'>
</style>
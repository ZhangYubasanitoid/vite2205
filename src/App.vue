<script >
// This starter template is using Vue 3 <script setup> SFCs
// Check out https://vuejs.org/api/sfc-script-setup.html#script-setup
import abc from './components/Abc.vue'
import One from './components/One.vue'
import {provide,ref} from 'vue'
export default{
  components: {
    abc,
    One
  },
  provide:{
    age:20,
    obj:{name:555}
  },
  setup() {
    const location = ref('North Pole')
    provide('location', location)
    provide('geolocation', {
      longitude: 90,
      latitude: 135
    })
    return{
      location
    }
  },
   methods: {
    updateLocation() {
      this.location = 'South Pole'
    }
  }
}
</script>



<template>
<button @click="updateLocation">12</button>
  <abc></abc>
  <One></One>

</template>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>

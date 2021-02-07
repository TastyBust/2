<template>
  <div class="home">
    <img alt="Vue logo" src="../assets/logo.png">
    <HelloWorld msg="Welcome to Your Vue.js App"/>
    <button @click="click">sahjdk</button>
  </div>

</template>

<script>
// @ is an alias to /src
import HelloWorld from '@/components/HelloWorld.vue'


export default {
 methods:{
   click:function(){
this.axios.get("http://37.77.104.246/api/jsonstorage/?id=7c1ddaec79baa8a4f419449d062a24a7").then(response =>{
    console.log(response.data);
})
   }
 }
}
</script>

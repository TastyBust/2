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
this.axios.get("http://37.77.104.246/api/jsonstorage/?id=2716ef404c324ddc5c9fea59215e724a").then(response =>{
    console.log(response.data);
})
   }
 }
}
</script>

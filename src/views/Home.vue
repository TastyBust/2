<template>
  <div class="home">
    <img alt="Vue logo" src="../assets/logo.png">
    <HelloWorld msg="Welcome to Your Vue.js App"/>
    <button @click="press">sahjdk</button>
  </div>

</template>

<script>
// @ is an alias to /src
import HelloWorld from '@/components/HelloWorld.vue'


export default {
 methods:{
   press:function(){
this.axios.get("http://37.77.104.246/api/jsonstorage/?id=2716ef404c324ddc5c9fea59215e724a").then(response =>{
 let users = response.data;
 let found = false;
 for (let index in users){
   if (this.login == users[index].login&& this.password == users[index].password){
     this.$router.push('/users/' + this.myId);
     found =  true;
     break;

   }
 }
 if (!found) window.alert('Неверный логин или пароль');
})
   }
 }
}
</script>

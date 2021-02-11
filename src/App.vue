<template>
  <v-app>
    <router-link to="/">Главная</router-link>
        <router-link v-if="users==''" to="/login">Вход</router-link>
            <router-link v-else :to="`/users/${users.login}`">{{users.name}}</router-link>
  <router-view v-on:login="mylogin" />
  </v-app>
</template>

<script>
import HelloWorld from './components/HelloWorld';

export default {
data(){
  return {
    users:'',
    
  }
},
  methods:{
mylogin($login){
//this.users=$login;
//console.log(this.users);
console.log($login);
}

  },

  data: () => ({
    //
  }),
  
};

</script>


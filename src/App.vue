<template>
  <v-app>
  <router-view v-on:login="updateUser" />
  </v-app>
</template>

<script>
import HelloWorld from './components/HelloWorld';

export default {
  name: 'App',
id:-1,
login:"",
  components: {
  
  },
  methods:{
login: function (id,login){
  this.id = id;
  alert(id);
  this.login = login;

},
updateUser: function(){
 
if (this.id!=-1) this.$router.push('/users/' + this.id); else this.$router.push('/login');
}

  },

  data: () => ({
    //
  }),
  
};

</script>


<template>
    <div class="d-flex justify-center">
        <v-card width="600px" class="mt-12 pa-10">
            <v-card-title>
                Войдите в аккаунт
            </v-card-title>

            <v-text-field
                label="Введите логин"
                v-model="login"
                outlined
            ></v-text-field>

            <v-text-field
                label="Введите пароль"
                v-model="password"
                outlined
            ></v-text-field>

            <v-btn @click="authenticate">
                Войти
            </v-btn>
        </v-card>
    </div>
</template>
<script>
export default {
    data:()=>({
         login:"",
    password:"",  
    
 }),
 methods:{
  authenticate(){
this.axios.get("http://37.77.104.246/api/jsonstorage/?id=2716ef404c324ddc5c9fea59215e724a").then(response =>{
 let users = response.data;
 let found = false;

 for (let index in users){
     
   if (this.login == users[index].login&& this.password == users[index].password){
       this.$emit('login',users[index]);
     this.$router.push('/users/' + index);
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
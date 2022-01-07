<template>
 <div>
   <form class="login" @submit.prevent="login">
     <h1>Sign in</h1>
     <label>Email</label>
     <input required v-model="email" type="email" placeholder="Email"/>
     <label>Mot de passe</label>
     <input required v-model="password" type="password" placeholder="Mot de passe"/>
     <hr/>
     <button type="submit">Se connecter</button>
   </form>
 </div>
</template>
<script>
  export default {
    data(){
      return {
        email : "",
        password : ""
      }
    },
    methods: {
      login: function () {
        let email = this.email
        let password = this.password
        this.$store.dispatch('login', { email, password })
       .then(() => this.$router.push('/'))
       .catch(err => console.log(err))
      }
    }
  }
</script>
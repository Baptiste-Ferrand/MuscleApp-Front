<template>
  <div class="py-4">
    <v-img
      class="mx-auto mb-10"
      max-width="228"
      :src="img"
    ></v-img>

    <v-card
      class="mx-auto pa-12 pb-8"
      elevation="8"
      max-width="448"
      rounded="lg"
    >

      <div class="text-subtitle-1 text-medium-emphasis">Account</div>

      <v-text-field
        density="compact"
        placeholder="Nom"
        v-model="user.name"
        variant="outlined"
      ></v-text-field>

      <v-text-field
        density="compact"
        placeholder="Prénom"
        v-model="user.surname"
        variant="outlined"
      ></v-text-field>

      <v-text-field
        density="compact"
        placeholder="Pseudo"
        v-model="user.username"
        variant="outlined"
      ></v-text-field>

      <v-text-field
        density="compact"
        placeholder="Email"
        v-model="user.email"
        prepend-inner-icon="mdi-email-outline"
        variant="outlined"
      ></v-text-field>
      <div class="text-subtitle-1 text-medium-emphasis d-flex align-center justify-space-between">
        Password
      </div>
      <v-text-field
        :append-inner-icon="visible ? 'mdi-eye-off' : 'mdi-eye'"
        :type="visible ? 'text' : 'password'"
        density="compact"
        v-model="user.password"
        placeholder="Enter your password"
        prepend-inner-icon="mdi-lock-outline"
        variant="outlined"
        @click:append-inner="visible = !visible"
      ></v-text-field>
      <v-text-field
        :append-inner-icon="visible ? 'mdi-eye-off' : 'mdi-eye'"
        :type="visible ? 'text' : 'password'"
        density="compact"
        placeholder="Confirm your password"
        prepend-inner-icon="mdi-lock-outline"
        variant="outlined"
        @click:append-inner="visible = !visible"
      ></v-text-field>

      <v-btn
        block
        class="mb-8"
        color="blue"
        size="large"
        variant="tonal"
        @click="gotoLogin"
      >
        Log In
      </v-btn>
    </v-card>
  </div>
</template>

<script>
export default {
  name: "Register",
  layout: "login",
  data(){
    return{
      img: require('../assets/img/logo.png'),
      visible: false,
      condition: true,
      user:{
        name:'',
        surname:'',
        username:'',
        email:'',
        password:''
      }
    }
  },
  methods:{
    async gotoLogin(){
      try {
        await this.$axios.post('user', this.user).then((responce)=>{
          console.log(responce.data)
          this.$router.push('/login')
        })
      }catch (e){
        console.log("false!!");
      }
    }
  }
};
</script>

<style scoped>

</style>

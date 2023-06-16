<template>
  <div class="py-4">
    <v-img :src="img" class="mx-auto mb-10" max-width="228"></v-img>

    <v-alert
      v-if="error"
      border="left"
      class="error"
      color="orange"
      dense
      elevation="8"
      outlined
      type="error"
      >Login ou mot de passe incorrect
    </v-alert>
    <v-card
      class="mx-auto pa-12 pb-8"
      elevation="8"
      max-width="448"
      rounded="lg"
    >
      <div class="text-subtitle-1 text-medium-emphasis">Account</div>

      <v-text-field
        v-model="user.email"
        density="compact"
        placeholder="Email address"
        prepend-inner-icon="mdi-email-outline"
        variant="outlined"
      ></v-text-field>

      <div
        class="text-subtitle-1 text-medium-emphasis d-flex align-center justify-space-between"
      >
        Password

        <a
          class="text-caption text-decoration-none text-blue"
          href="#"
          rel="noopener noreferrer"
          target="_blank"
        >
          Forgot login password?</a
        >
      </div>

      <v-text-field
        v-model="user.password"
        :append-inner-icon="visible ? 'mdi-eye-off' : 'mdi-eye'"
        :type="visible ? 'text' : 'password'"
        density="compact"
        placeholder="Enter your password"
        prepend-inner-icon="mdi-lock-outline"
        variant="outlined"
        @click:append-inner="visible = !visible"
      ></v-text-field>

      <v-card class="mb-12" color="surface-variant" variant="tonal">
        <v-card-text class="text-medium-emphasis text-caption">
          Warning: After 3 consecutive failed login attempts, you account will
          be temporarily locked for three hours. If you must login now, you can
          also click "Forgot login password?" below to reset the login password.
        </v-card-text>
      </v-card>

      <v-btn
        block
        class="mb-8"
        color="blue"
        size="large"
        variant="tonal"
        @click="gotoHome"
      >
        Log In
      </v-btn>

      <v-card-text class="text-center" @click="gotoRegister">
        <a class="text-blue text-decoration-none">
          Sign up now
          <v-icon icon="mdi-chevron-right"></v-icon>
        </a>
      </v-card-text>
    </v-card>
  </div>
</template>
<script>
export default {
  name: 'Login',
  layout: 'login',
  data() {
    return {
      user: {
        email: '',
        password: '',
      },
      error: false,
      visible: false,
      img: require('../assets/img/logo.png'),
    }
  },
  methods: {
    gotoRegister() {
      this.$router.push('/register')
    },
    async gotoHome() {
      const data = new FormData()
      data.append('email', this.user.email)
      data.append('password', this.user.password)
      try {
        await this.$auth
          .loginWith('local', {
            data,
            headers: {
              'Content-Type': 'multipart/form-data',
            },
          })
          .then((response) => {
            console.log(response)
            this.$router.push('/')
          })
      } catch (e) {
        this.error = true
        console.log(e)
      }

      // try {
      //   await this.$axios.post('auth/login', data).then((responce) => {
      //     console.log(responce.data);
      //     this.$router.push('/')
      //   })
      // } catch (e) {
      //   this.error = true;
      //   console.log('caaaca')
      //   console.error(e)
      // }
    },
  },
}
</script>

<style scoped>
.error {
  display: block;
  margin-left: auto;
  margin-right: auto;
  width: 20%;
}
</style>

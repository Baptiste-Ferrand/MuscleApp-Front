<template>
  <div class="py-4">
    <v-img :src="img" class="mx-auto mb-10" max-width="228"></v-img>

    <v-card
      class="mx-auto pa-12 pb-8"
      elevation="8"
      max-width="448"
      rounded="lg"
    >
      <div align="center" class="text-subtitle-1 text-medium-emphasis">
        Creation de Profil
      </div>

      <v-text-field
        v-model="user.name"
        :rules="nameRules"
        density="compact"
        label="Nom"
        variant="outlined"
      ></v-text-field>

      <v-text-field
        v-model="user.surname"
        :rules="nameRules"
        density="compact"
        label="Prénom"
        variant="outlined"
      ></v-text-field>

      <v-text-field
        v-model="user.username"
        :rules="nameRules"
        density="compact"
        label="Pseudo"
        variant="outlined"
      ></v-text-field>

      <v-text-field
        v-model="user.email"
        :rules="emailRules"
        density="compact"
        label="Email"
        prepend-inner-icon="mdi-email-outline"
        variant="outlined"
      ></v-text-field>
      <div
        class="text-subtitle-1 text-medium-emphasis d-flex align-center justify-space-between"
      >
        Mot de passe
      </div>
      <v-text-field
        v-model="user.password"
        :append-inner-icon="visible ? 'mdi-eye-off' : 'mdi-eye'"
        :rules="nameRules"
        :type="visible ? 'text' : 'password'"
        density="compact"
        label="Entrer vôtre mot de passe"
        prepend-inner-icon="mdi-lock-outline"
        variant="outlined"
        @click:append-inner="visible = !visible"
      ></v-text-field>
      <v-text-field
        v-model="user.confirmPassword"
        :append-inner-icon="visible ? 'mdi-eye-off' : 'mdi-eye'"
        :error-messages="confirmPasswordErrors"
        :type="visible ? 'text' : 'password'"
        density="compact"
        label="Confirmer mot de passe"
        prepend-inner-icon="mdi-lock-outline"
        variant="outlined"
        @click:append-inner="visible = !visible"
      ></v-text-field>

      <v-btn
        :disabled="!isFormValid"
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
  auth: false,
  name: 'Register',
  layout: 'login',
  data() {
    return {
      img: require('../assets/img/logo.png'),
      visible: false,
      condition: false,
      nameRules: [(v) => !!v || 'E-mail is required'],
      emailRules: [
        (v) => !!v || 'E-mail is required',
        (v) =>
          /^(([^<>()[\]\\.,;:\s@']+(\.[^<>()\\[\]\\.,;:\s@']+)*)|('.+'))@((\[[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\])|(([a-zA-Z\-0-9]+\.)+[a-zA-Z]{2,}))$/.test(
            v
          ) || 'E-mail dois être sous la forme suivante : example@mail.com',
      ],
      user: {
        name: '',
        surname: '',
        username: '',
        email: '',
        password: '',
        confirmPassword: '',
      },
    }
  },
  computed: {
    isFormValid() {
      return (
        this.user.name &&
        this.user.surname &&
        this.user.username &&
        this.user.email &&
        this.user.password &&
        this.user.password === this.user.confirmPassword
      )
    },
    passwordMatch() {
      return this.user.password === this.user.confirmPassword
    },
    confirmPasswordErrors() {
      return this.passwordMatch
        ? []
        : ['Le mot de passe de confirmation ne correspond pas']
    },
  },
  methods: {
    async gotoLogin() {
      try {
        await this.$axios.post('user', this.user).then((response) => {
          if (response) {
            this.$router.push('/login')
          }
        })
      } catch (e) {
        console.error(e)
      }
    },
  },
}
</script>

<style scoped></style>

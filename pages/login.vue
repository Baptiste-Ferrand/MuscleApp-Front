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
      <div class="text-subtitle-1 text-medium-emphasis">Compte</div>

      <v-text-field
        v-model="user.email"
        density="compact"
        label="Adress Email"
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
        :type="visible ? 'text' : 'password'"
        density="compact"
        label="Entrer vôtre mot de passe"
        prepend-inner-icon="mdi-lock-outline"
        variant="outlined"
        @click:append-inner="visible = !visible"
      ></v-text-field>

      <v-card class="mb-12" color="surface-variant" variant="tonal">
        <v-card-text class="text-medium-emphasis text-caption">
          Avertissement : Après trois échecs consécutifs, votre compte sera
          temporairement bloqué pendant trois heures. sera temporairement bloqué
          pendant trois heures. Si vous devez vous connecter maintenant, vous
          pouvez également cliquer sur "Mot de passe oublié" ci-dessous pour
          réinitialiser le mot de passe.
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
        Se connecter
      </v-btn>

      <v-card-text class="text-center" @click="gotoRegister">
        <a class="text-blue text-decoration-none">
          Créer un compte
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
            if (response) {
              this.$router.push('/')
            }
          })
      } catch {
        this.error = true
      }
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

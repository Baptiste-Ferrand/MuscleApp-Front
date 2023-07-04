<template>
  <v-app class="background">
    <v-main>
      <v-container>
        <Nuxt />
      </v-container>
    </v-main>
  </v-app>
</template>

<script>
export default {
  name: 'Login',
  auth: false,
}
</script>

<style scoped>
.background {
  background: rgba(0, 0, 10, 0.96);
}

body {
  background: rgba(0, 0, 10, 0.96);
}
</style>

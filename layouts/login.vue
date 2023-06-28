<template>
  <v-app class="bakcground">
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
.bakcground {
  /*background: radial-gradient(#000000, #040815);*/
  background: rgba(0, 0, 10, 0.96);
}

body {
  background-color: #f61111;
}
</style>

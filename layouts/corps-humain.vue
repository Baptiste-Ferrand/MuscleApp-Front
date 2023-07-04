<template>
  <v-app dark>
    <v-app-bar
      :clipped-left="true"
      :clipped-right="true"
      :shrink-on-scroll="true"
      :src="headerimg"
      app
      height="250"
    >
      <v-fab-transition>
        <v-btn
          bottom
          class="v-btn--example"
          color="primary"
          dark
          fab
          left
          small
          @click="GoBack"
        >
          <v-icon>mdi-arrow-left-bold</v-icon>
        </v-btn>
      </v-fab-transition>
    </v-app-bar>

    <v-navigation-drawer
      :clipped="true"
      app
      class="right-drawer"
      fixed
      width="150"
    >
    </v-navigation-drawer>

    <v-main>
      <v-container>
        <Nuxt />
      </v-container>
    </v-main>

    <v-navigation-drawer
      :clipped="true"
      :right="true"
      app
      class="left-drawer"
      fixed
      width="150"
    >
    </v-navigation-drawer>
  </v-app>
</template>

<script>
export default {
  name: 'CorpsHumain',
  data() {
    return {
      headerimg: require('../assets/img/IMG_1709.JPG'),
    }
  },
  methods: {
    GoBack() {
      this.$router.push('/corps-humain')
    },
  },
}
</script>

<style scoped>
.right-drawer {
  background: radial-gradient(#000000, #0a0a0a, #101010, #0e1434);
  height: 100%;
}

.left-drawer {
  background: radial-gradient(#000000, #0a0a0a, #101010, #0e1434);
  width: 10%;
}
</style>

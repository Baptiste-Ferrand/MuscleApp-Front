<template>
  <v-app class="mt-8 mb-10">
    <v-navigation-drawer
      v-model="drawer"
      :clipped="true"
      app
      color="rgb(20,20,30)"
      fixed
    >
      <v-list>
        <v-list-item
          v-for="(item, i) in items"
          :key="i"
          :to="item.to"
          exact
          router
        >
          <v-list-item-action>
            <v-icon>{{ item.icon }}</v-icon>
          </v-list-item-action>
          <v-list-item-content>
            <v-list-item-title>{{ item.title }}</v-list-item-title>
          </v-list-item-content>
        </v-list-item>
      </v-list>
    </v-navigation-drawer>
    <v-app-bar :clipped-left="true" app color="rgb(20,20,30)" fixed>
      <v-app-bar-nav-icon @click.stop="drawer = !drawer" />
      <v-img :src="img" class="mx-auto" max-width="80"></v-img>
      <v-spacer />
      <v-btn icon to="/profil">
        <v-icon>mdi-account</v-icon>
      </v-btn>
    </v-app-bar>
    <v-main class="background">
      <v-container>
        <Nuxt />
      </v-container>
    </v-main>
  </v-app>
</template>

<script>
export default {
  name: 'DefaultLayout',
  middleware: 'auth',
  data() {
    return {
      img: require('../assets/img/logo.png'),
      drawer: true,
      fixed: true,
      items: [
        {
          icon: 'mdi-home-heart',
          title: "Vue d'ensemble",
          to: '/',
        },
        {
          icon: 'mdi-format-list-numbered',
          title: 'Exercices',
          to: '/list-exos',
        },
        {
          icon: 'mdi-arm-flex',
          title: 'Morphologie',
          to: '/corps-humain',
        },
        {
          icon: 'mdi-clipboard-edit',
          title: 'Entraînement',
          to: '/cree-workout',
        },
        {
          icon: 'mdi-shield-crown',
          title: 'Admin',
          to: '/admin',
        },
      ],
      right: true,
      rightDrawer: false,
      title: 'MusculApp',
    }
  },
}
</script>

<style>
.background {
  background: #0a0a14;
}

body {
  background-color: #0a0a14;
}
</style>

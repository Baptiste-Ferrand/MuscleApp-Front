<template>
  <v-app >
    <v-navigation-drawer
      v-model="drawer"
      :clipped="true"
      fixed
      app
      color="rgb(20,20,30)"
    >
      <v-list>
        <v-list-item
          v-for="(item, i) in items"
          :key="i"
          :to="item.to"
          router
          exact
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
    <v-app-bar :clipped-left="true" fixed app color="rgb(20,20,30)">
      <v-app-bar-nav-icon @click.stop="drawer = !drawer" />
      <v-img
        class="mx-auto"
        max-width="80"
        :src="img"
      ></v-img>
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
  data() {
    return {
      img: require('../assets/img/logo.png'),
      drawer: true,
      fixed: true,
      items: [
        {
          icon: 'mdi-apps',
          title: 'Welcome',
          to: '/',
        },
        {
          icon: 'mdi-chart-bubble',
          title: 'list exos',
          to: '/list-exos',
        },
        {
          icon: 'mdi-chart-bubble',
          title: 'corps humain',
          to: '/corps-humain',
        },
        {
          icon: 'mdi-chart-bubble',
          title: 'cree workout',
          to: '/cree-workout',
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
.background{
  background: #0a0a14;
}
</style>

<template>
  <v-app dark>
    <v-app-bar
      :clipped-left="true"
      :clipped-right="true"
      :shrink-on-scroll="true"
      height="250"
      app
      :src="headerimg"
    >
    </v-app-bar>

    <v-navigation-drawer
    fixed
    app
    :clipped="true"
    class="right-drawer"
    width='150'
    >
    </v-navigation-drawer>



    <v-main>
      <v-container>
        <Nuxt />
      </v-container>
    </v-main>

    <v-navigation-drawer
    fixed
    :right="true"
    app
    :clipped="true"
    class="left-drawer"
    width='150'>

    </v-navigation-drawer>

<!--    <v-footer :absolute="!fixed" app class="footer">-->
<!--      <span>&copy; {{ new Date().getFullYear() }}</span>-->
<!--    </v-footer>-->
  </v-app>
</template>

<script>
export default {
  name: "Corps-humain",
  data(){
    return{
      headerimg : require('../assets/img/IMG_1709.JPG')
    }
  }
};
</script>

<style scoped>
.right-drawer{
  background: radial-gradient(#000000, #0a0a0a, #101010, #0e1434);
  height: 100%;

}
.left-drawer{
  background: radial-gradient(#000000, #0a0a0a, #101010, #0e1434);
  width: 10%;
}
</style>

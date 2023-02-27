<template>
  <v-app white>
    <v-navigation-drawer
      v-model="drawer"
      :mini-variant="miniVariant"
      :clipped="!clipped"
      fixed
      app
    >
      <v-list>
        <v-list-item
          v-for="(item, i) in item"
          :key="i"
          :to="localePath(item.to)"
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
    <v-app-bar
      :clipped-left="!clipped"
      fixed
      app
    >
      <v-app-bar-nav-icon @click.stop="drawer = !drawer" />
      <v-toolbar-title>{{ $t('welcome') }}</v-toolbar-title>
      <v-spacer />
      <v-btn
        icon
        @click.stop="rightDrawer = !rightDrawer"
      >
        <v-icon>mdi-account</v-icon>
      </v-btn>
    </v-app-bar>
    <v-main>
      <v-container>
        <Nuxt />
      </v-container>
    </v-main>
    <v-navigation-drawer
      v-model="rightDrawer"
      :right="right"
      temporary
      fixed
    >
      <v-list>
        <div>
          <v-alert
            v-model="alert"
            dismissible
            color="cyan"
            border="left"
            elevation="2"
            colored-border
            icon="mdi-twitter"
          >
            <strong>5</strong>{{ $t('notify') }}
          </v-alert>
        </div>
        <v-btn @click="switchTheme">
          Switch
        </v-btn>
        <lang-button />
      </v-list>
    </v-navigation-drawer>
    <v-footer
      :absolute="!fixed"
      app
    >
      <span>&copy; {{ new Date().getFullYear() }}</span>
    </v-footer>
  </v-app>
</template>

<script>

export default {

  name: 'DefaultLayout',
  data () {
    return {
      clipped: false,
      drawer: false,
      fixed: false,
      statuscookie: true,
      miniVariant: false,
      right: true,
      rightDrawer: false,
      valrdm: 0,
      alert: true,
      item: []

    }
  },
  beforeMount () {
    this.valrdm = Math.floor(Math.random() * 2)
    if (this.valrdm === 0) {
      this.alert = false
    } else {
      this.alert = true
    }
    this.item = [
      {
        icon: 'mdi-human-greeting',
        title: this.$t('list_pages.home'),
        to: 'index'
      },
      {
        icon: 'mdi-clipboard-list',
        title: this.$t('list_pages.list_exercises'),
        to: 'list-exos'
      },
      {
        icon: 'mdi-human-edit',
        title: this.$t('list_pages.human_body'),
        to: 'corps-humain'
      },
      {
        icon: 'mdi-arm-flex',
        title: this.$t('list_pages.create_workout'),
        to: 'cree-workout'
      }
    ]
  },

  methods: {
    switchTheme () {
      this.$vuetify.theme.isDark = !this.$vuetify.theme.isDark
    }

  }

}
</script>

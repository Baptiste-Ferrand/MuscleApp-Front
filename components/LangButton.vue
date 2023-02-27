<template>
  <v-menu>
    <template #activator="{on, attrs}">
      <v-btn
        class="ma-2"
        :outlined="!fixedStyle"
        :text="fixedStyle"
        :color="fixedStyle ? '' : 'primary'"
        v-bind="attrs"
        v-on="on"
      >
        <v-img
          :src="require(`~/assets/img/lang/${$i18n.locale}.svg`)"
          width="20"
          max-width="20"
          height="20"
          contain
        />
        <v-icon right>
          mdi-menu-down
        </v-icon>
      </v-btn>
    </template>
    <v-list>
      <v-list-item
        v-for="(locale) in $i18n.locales.filter(e => !e.disabled)"
        :key="locale.code"
        nuxt
        :to="switchLocalePath(locale.code)"
      >
        <v-list-item-title class="d-flex align-center justify-start">
          <v-img
            :src="require(`~/assets/img/lang/${locale.code}.svg`)"
            width="20"
            max-width="20"
            height="20"
            contain
          />
          <span class="ml-2">{{ locale.name }}</span>
        </v-list-item-title>
      </v-list-item>
    </v-list>
  </v-menu>
</template>

<script>

export default {
  name: 'LangButton',
  props: {
    fixedStyle: {
      type: Boolean,
      default: false
    }

  }

}
</script>

<style scoped>

</style>

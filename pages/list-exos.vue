<template>
  <div>
    <v-card class="background">
      <v-card-title>
        List Exercices
        <v-spacer />
        <v-text-field
          v-model="search"
          append-icon="mdi-magnify"
          hide-details
          label="Search"
          single-line
        />
      </v-card-title>
      <v-data-table
        :expanded.sync="expanded"
        :headers="itemsHeaders"
        :item-key="items.id"
        :items="items"
        :search="search"
        :single-expand="singleExpand"
        class="elevation-1 background"
        show-expand
      >
        <template #top />
        <template #expanded-item="{ headers, item }">
          <td :colspan="headers.length">
            {{ item.description }}
            <v-btn
              class="pa-4 secondary text-no-wrap rounded-pill"
              @click="gotoExo(item)"
            >
              Voir plus
            </v-btn>
          </td>
        </template>
      </v-data-table>
    </v-card>
  </div>
</template>

<script>
export default {
  name: 'ListExos',
  data() {
    return {
      expanded: [],
      search: '',
      singleExpand: true,
      itemsHeaders: [
        {
          text: 'Exercices',
          align: 'start',
          sortable: false,
          value: 'title',
        },
        { text: 'Cible', value: 'type' },
        { text: 'Membre', value: 'member' },
        { text: 'Dificulter', value: 'difficulty' },
      ],
      items: [],
    }
  },
  async fetch() {
    await this.$axios.get('exercise/some/9999').then((response) => {
      this.items = response.data
    })
  },
  methods: {
    gotoExo(item) {
      this.$router.push({
        path: '/exercice',
        query: { id: item.id },
      })
    },
  },
}
</script>

<style scoped>
.background {
  background: #0a0a14;
}
</style>

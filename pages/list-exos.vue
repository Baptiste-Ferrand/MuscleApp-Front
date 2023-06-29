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
        :items="items"
        :search="search"
        :single-expand="singleExpand"
        class="elevation-1 background"
        item-key="name"
        show-expand
      >
        <template #top />
        <template #expanded-item="{ headers, item }">
          <td :colspan="headers.length">
            More info about {{ item.name }}
            <v-btn
              class="pa-4 secondary text-no-wrap rounded-pill"
              @click="OnClick(item)"
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
      logo_existing: false,
      search: '',
      singleExpand: true,
      itemsHeaders: [
        {
          text: 'Dessert (100g serving)',
          align: 'start',
          sortable: false,
          value: 'name',
        },
        { text: 'Type', value: 'type' },
        { text: 'Cible', value: 'cible' },
        { text: 'Membre', value: 'membre' },
        { text: 'Dificulter', value: 'difficult' },
      ],
      items: [
        // {
        //   name: 'Barre au front',
        //   type: '-',
        //   membre: 'triceps',
        //   difficult: 7,
        //   cible: 'Long Portion'
        //
        // },
        // {
        //   name: 'Curl marteau',
        //   type: 'biceps court',
        //   membre: 'biceps',
        //   difficult: 5
        //
        // },
        // {
        //   name: 'Eclair',
        //   type: 262,
        //   membre: 16.0,
        //   difficult: 23
        //
        // },
        // {
        //   name: 'Cupcake',
        //   type: 305,
        //   membre: 3.7,
        //   difficult: 67
        //
        // },
        // {
        //   name: 'Gingerbread',
        //   type: 356,
        //   membre: 16.0,
        //   difficult: 49
        //
        // },
        // {
        //   name: 'Jelly bean',
        //   type: 375,
        //   membre: 0.0,
        //   difficult: 94
        //
        // },
        // {
        //   name: 'Lollipop',
        //   type: 392,
        //   membre: 0.2,
        //   difficult: 98
        // },
        // {
        //   name: 'Honeycomb',
        //   type: 408,
        //   membre: 3.2,
        //   difficult: 87
        //
        // },
        // {
        //   name: 'Donut',
        //   type: 452,
        //   membre: 25.0,
        //   difficult: 51
        //
        // },
        // {
        //   name: 'KitKat',
        //   type: 518,
        //   membre: 26.0,
        //   difficult: 65
        // }
      ],
    }
  },
  methods: {
    OnClick(item) {
      switch (item.name) {
        case 'Barre au front':
          break
        default:
          break
      }
    },
  },
}
</script>

<style scoped>
.background {
  background: #0a0a14;
}
</style>

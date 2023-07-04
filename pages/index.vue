<template>
  <div>
    <v-row>
      <v-col cols="12" lg="3">
        <weight-card
          :subtitle="parseInt(user.first_weight.toFixed(1))"
          title="Poids Initial"
        />
      </v-col>
      <v-col cols="12" lg="3">
        <weight-card
          :subtitle="parseInt(user.actual_weight.toFixed(1))"
          title="Poids Actuel"
        />
      </v-col>
      <v-col cols="12" lg="3">
        <weight-card
          :subtitle="parseInt(user.last_weight.toFixed(1))"
          title="Poids Final"
        />
      </v-col>
      <v-col cols="12" lg="3">
        <weight-card :subtitle="user.objectif" title="Objectif" />
      </v-col>
    </v-row>
    <graph-stats-weight />
    <v-spacer class="mb-10"></v-spacer>
    <v-sheet class="mx-auto" elevation="8" max-width="800">
      <v-slide-group
        active-class="success"
        class="pa-4"
        show-arrows
        style="background: #0a0a14"
      >
        <v-slide-item v-for="item of user.seance" :key="item.id">
          <v-card
            class="ma-4 seance"
            height="200"
            style="border: 1px solid darkgreen"
            width="200"
            @click="seeSeance(item)"
          >
            <v-card-title>{{ item.title }}</v-card-title>
            <v-card-text>{{ item.description }}</v-card-text>
          </v-card>
        </v-slide-item>
      </v-slide-group>
    </v-sheet>
    <v-row justify="center">
      <v-dialog v-model="show_seance" max-width="600px">
        <v-card>
          <v-card-title>
            <span class="text-h5">{{ select_seance.title }}</span>
            <v-icon color="red" @click="show_seance = false"
              >mdi-window-close
            </v-icon>
          </v-card-title>
          <v-card-text>
            <v-data-table
              :headers="seance_headers"
              :items="select_seance.exercises"
              :items-per-page="5"
              class="elevation-1"
            ></v-data-table>
          </v-card-text>
        </v-card>
      </v-dialog>
    </v-row>
  </div>
</template>

<script>
import GraphStatsWeight from '~/components/GraphStatsWeight.vue'
import WeightCard from '~/components/WeightCard.vue'

export default {
  name: 'IndexPage',
  components: { WeightCard, GraphStatsWeight },
  data() {
    return {
      user: {
        first_weight: 0,
        actual_weight: 0,
        last_weight: 0,
        objectif: '',
        seance: [],
      },
      seance_headers: [
        {
          text: 'Exercice',
          align: 'start',
          sortable: false,
          value: 'name',
        },
        { text: 'Nombre Séries', value: 'serie' },
        { text: 'Nombre Répétitions', value: 'repetition' },
        { text: 'Temps Repos', value: 'rest_time' },
        { text: 'Methods', value: 'method' },
      ],
      select_seance: {},
      show_seance: false,
    }
  },
  async fetch() {
    await this.$axios.get('weight/initial').then((response) => {
      this.user.first_weight = response.data.value
    })

    await this.$axios.get('/').then((response) => {
      this.user.seance = response.data
    })

    await this.$axios.get('weight/latest').then((response) => {
      this.user.actual_weight = response.data.value
    })
    await this.$axios.get('objective').then((response) => {
      this.user.objectif = response.data[0].title
      this.user.last_weight = response.data[0].weight
    })

    await this.$axios.get('weight/latest').then((response) => {
      this.user.actual_weight = response.data.value
    })
  },
  methods: {
    seeSeance(item) {
      this.select_seance = item
      this.show_seance = true
    },
  },
}
</script>

<style scoped>
.seance {
  background: radial-gradient(#000000, #2c5a57);
  border-radius: 10px;
  align-content: center;
}
</style>

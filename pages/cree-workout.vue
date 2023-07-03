<template>
  <div>
    <v-text-field
      v-model="seance.title"
      align="center"
      clearable
      label="Nom de vôtre séance"
      solo
    ></v-text-field>
    <v-textarea
      v-model="seance.description"
      align="center"
      clearable
      label="Description de vôtre séance"
      solo
    />
    <div class="card-container">
      <v-card
        v-for="(item, index) of temp_exercices"
        :key="index"
        class="exo-card"
      >
        <v-card-title>
          <v-icon color="red" @click="deleteExo(item)">mdi-delete</v-icon>
          {{ item.name }}
        </v-card-title>
        <hr />
        <v-card-text>
          nombre de série : {{ item.serie }} <br />
          nombre de répétition : {{ item.repetition }} <br />
          temps de repos: {{ item.rest_time }} <br />
          methode d'entrainement: {{ item.methods }}
        </v-card-text>
      </v-card>
    </div>
    <template>
      <v-row justify="center">
        <v-dialog v-model="dialog" max-width="600px" persistent>
          <template #activator="{ on, attrs }">
            <v-btn class="add-button" v-bind="attrs" v-on="on">
              Ajouter exercice
            </v-btn>
          </template>
          <v-card>
            <v-icon color="red" @click="cancelledExo">mdi-window-close</v-icon>
            <v-card-title>
              <span class="text-h5">Creation exercice</span>
            </v-card-title>
            <v-card-text>
              <v-container>
                <v-row>
                  <v-col cols="12" md="4" sm="6">
                    <v-combobox
                      v-model="temp_data_exo.name"
                      :items="exercice"
                      clearable
                      filled
                      hide-selected
                      outlined
                      small-chips
                    ></v-combobox>
                  </v-col>
                  <v-col cols="12" md="4" sm="3">
                    <v-text-field
                      v-model="temp_data_exo.serie"
                      label="Séries"
                    ></v-text-field>
                  </v-col>
                  <v-col cols="12" md="4" sm="3">
                    <v-text-field
                      v-model="temp_data_exo.repetition"
                      label="Répétition"
                      persistent-hint
                      required
                    ></v-text-field>
                  </v-col>
                  <v-col cols="12">
                    <v-text-field
                      v-model="temp_data_exo.rest_time"
                      label="Temps Repos"
                      required
                    ></v-text-field>
                  </v-col>
                  <v-chip-group v-model="selectedChip" column>
                    <v-chip
                      v-for="chip in chips"
                      :key="chip.value"
                      :value="chip.value"
                      filter
                      outlined
                    >
                      {{ chip.label }}
                    </v-chip>
                  </v-chip-group>
                </v-row>
              </v-container>
            </v-card-text>
            <v-card-actions>
              <v-spacer></v-spacer>
              <v-btn color="blue darken-1" text @click="saveExo"> Save</v-btn>
            </v-card-actions>
          </v-card>
        </v-dialog>
      </v-row>
    </template>
    <v-btn class="add-button" @click="creatSeance"> Créer Séance</v-btn>
  </div>
</template>

<script>
import Vue from 'vue'

export default {
  name: 'CreeWorkout',
  data() {
    return {
      dialog: false,
      exercice: [],
      chips: [
        { label: 'Pyramidal', value: 'pyramidal' },
        { label: 'Tempo', value: 'tempo' },
        { label: 'Dropset', value: 'dropset' },
        { label: 'Concentrique', value: 'concentrique' },
        { label: 'Excentrique', value: 'excentrique' },
      ],
      selectedChip: null,
      last_id: 0,
      temp_data_exo: {
        name: '',
        serie: 0,
        repetition: 0,
        rest_time: 0,
        method: '',
        id: 0,
      },
      temp_exercices: [],
      seance: { title: '', description: '', exercises: [] },
    }
  },
  async fetch() {
    try {
      await this.$axios.$get('exercise/some/999').then((response) => {
        this.exercice = response.map((item) => item.title)
      })
    } catch (error) {
      console.log(error)
    }
  },
  methods: {
    cancelledExo() {
      this.temp_data_exo.rest_time = 0
      this.temp_data_exo.repetition = 0
      this.temp_data_exo.serie = 0
      this.temp_data_exo.name = ''
      this.temp_data_exo.method = ''
      this.dialog = false
    },
    deleteExo(item) {
      this.temp_exercices = this.temp_exercices.filter(function (list) {
        return list.id !== item.id
      })
    },
    saveExo() {
      this.last_id++
      this.temp_data_exo.method = this.selectedChip
      this.temp_data_exo.id = this.last_id
      this.temp_data_exo.repetition = parseInt(this.temp_data_exo.repetition)
      this.temp_data_exo.serie = parseInt(this.temp_data_exo.serie)
      this.temp_data_exo.rest_time = parseFloat(this.temp_data_exo.rest_time)
      Vue.set(
        this.temp_exercices,
        this.temp_exercices.length,
        Object.assign({}, this.temp_data_exo)
      )
      this.temp_data_exo.rest_time = 0
      this.temp_data_exo.repetition = 0
      this.temp_data_exo.serie = 0
      this.temp_data_exo.name = ''
      this.temp_data_exo.method = ''
      this.dialog = false
    },
    async creatSeance() {
      this.seance.exercises = this.temp_exercices
      try {
        await this.$axios.$post('session/', this.seance)
        this.seance.title = ''
        this.seance.description = ''
        this.seance.exercises = []
        this.temp_exercices = []
        this.last_id = 0
      } catch (error) {
        console.log(error)
      }
    },
  },
}
</script>

<style scoped>
.card-container {
  flex-wrap: wrap; /* Sauter à la ligne lorsque nécessaire */
  display: flex; /* Afficher les cards en ligne */
  justify-content: center; /* Aligner horizontalement les cards au centre */
}

.exo-card {
  background-color: #333333;
  border-radius: 8px;
  box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
  padding: 4px;
  width: 300px;
  height: auto;
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  margin-right: 16px;
  color: #ffffff;
}

v-card-title {
  display: flex;
  align-items: center;
  font-weight: bold;
  font-size: 18px; /* Taille de la police pour le titre */
  margin-top: -8px;
}

v-card-title v-icon {
  font-size: 16px; /* Taille de la police pour l'icône */
  margin-right: 8px; /* Espacsement entre l'icône et le titre */
}

v-card-actions {
  display: flex;
  justify-content: flex-end;
}

v-card-text {
  font-size: 14px; /* Taille de la police pour le texte du contenu */
}

.add-button {
  border-radius: 25px 25px 25px 25px;
  display: block;
  margin-left: auto;
  margin-right: auto;
  width: 20%;
  margin-top: 10%;
}
</style>

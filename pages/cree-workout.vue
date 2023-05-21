<template>
  <div>
    <v-text-field
      v-model="seance.title"
      align="center"
      clearable
      label="Nom de vôtre séance"
      solo
    ></v-text-field>
    <div class="card-container">
      <v-card
        v-for="(item, index) of temp_exercices"
        :key="index"
        class="exo-card"
        @click="infoExo(item)"
      >
        <v-card-title>
          <v-icon color="red" @click="deleteExo(item)">mdi-delete</v-icon>
          {{ item.title }}
        </v-card-title>
        <hr />
        <v-card-text>
          nombre de série : {{ item.series }} <br />
          nombre de répétition : {{ item.repetitions }} <br />
          temps de repos: {{ item.repos }} <br />
          methode d'entrainement: {{ item.methods }}
        </v-card-text
        >
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
            <v-icon color="red" @click="dialog = false"
            >mdi-window-close
            </v-icon
            >
            <v-card-title>
              <span class="text-h5">Creation exercice</span>
            </v-card-title>
            <v-card-text>
              <v-container>
                <v-row>
                  <v-col cols="12" md="4" sm="6">
                    <v-combobox
                      v-model="temp_data_exo.title"
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
                      v-model="temp_data_exo.series"
                      label="Séries"
                    ></v-text-field>
                  </v-col>
                  <v-col cols="12" md="4" sm="3">
                    <v-text-field
                      v-model="temp_data_exo.repetitions"
                      label="Répétition"
                      persistent-hint
                      required
                    ></v-text-field>
                  </v-col>
                  <v-col cols="12">
                    <v-text-field
                      v-model="temp_data_exo.repos"
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
import Vue from "vue";

export default {
  name: "CreeWorkout",
  data() {
    return {
      dialog: false,
      exercice: ["barre au front", "Bench", "squat"],
      chips: [
        { label: "Pyramidal", value: "pyramidal" },
        { label: "Tempo", value: "tempo" },
        { label: "Dropset", value: "dropset" },
        { label: "Concentrique", value: "concentrique" },
        { label: "Excentrique", value: "excentrique" }
      ],
      selectedChip: null,
      last_id: 0,
      temp_data_exo: {
        title: "",
        series: 0,
        repetitions: 0,
        repos: 0,
        methods: "",
        id: 0
      },
      temp_exercices: [
        {
          title: "Barre au front",
          series: 4,
          repetitions: 10,
          repos: 1.3,
          methods: "pyramidal",
          id: 0
        },
        {
          title: "Curl Marteau",
          series: 4,
          repetitions: 10,
          repos: 1.3,
          methods: "pyramidal",
          id: 1
        },
        {
          title: "Curl inversée",
          series: 4,
          repetitions: 10,
          repos: 1.3,
          methods: "pyramidal",
          id: 2
        },
        {
          title: "Extention triceps",
          series: 4,
          repetitions: 10,
          repos: 1.3,
          methods: "pyramidal",
          id: 3
        }
      ],
      seance: { title: "", exercices: [] }
    };
  },
  mounted() {
    this.GetLastId();
  },
  methods: {
    cancelledExo() {
      // clear cash
      this.dialog = false;
    },
    infoExo(item) {
      console.log(item);
    },
    deleteExo(item) {
      this.temp_exercices = this.temp_exercices.filter(function(list) {
        return list.id !== item.id;
      });
    },
    saveExo() {
      this.last_id++;
      this.temp_data_exo.methods = this.selectedChip;
      this.temp_data_exo.id = this.last_id;
      Vue.set(
        this.temp_exercices,
        this.temp_exercices.length,
        Object.assign({}, this.temp_data_exo)
      );
      this.dialog = false;
    },
    GetLastId() {
      this.last_id = this.temp_exercices.reduce((prev, current) => {
        return current.id > prev.id ? current : prev;
      });
      this.last_id = this.last_id.id;
    },
    creatSeance() {
      this.seance.exercices = this.temp_exercices;
      console.log(this.seance);
      // appelle de la route pour ajouter la seance
    }
  }
};
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

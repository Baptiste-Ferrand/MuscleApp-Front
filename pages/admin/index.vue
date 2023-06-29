<template>
  <div align="center">
    <h2>Créer Exercices</h2>
    <v-card class="card">
      <v-col cols="12" sm="12">
        <v-text-field v-model="exo.title" label="Titre Exercice"></v-text-field>
      </v-col>
      <v-col cols="12" sm="12">
        <v-text-field v-model="exo.video" label="Vidéo Exercice"></v-text-field>
      </v-col>
      <v-col cols="12" sm="12">
        <v-text-field
          v-model="exo.difficulty"
          label="Difficulter Exercice (0-10)"
        ></v-text-field>
      </v-col>
      <v-col cols="12" sm="12">
        <v-text-field
          v-model="exo.member"
          label="Membre Exercice"
        ></v-text-field>
      </v-col>
      <v-col cols="12" sm="12">
        <v-text-field v-model="exo.type" label="Type Exercice"></v-text-field>
      </v-col>
      <v-col cols="12" sm="12">
        <v-textarea
          v-model="exo.description"
          label="Description Exercice"
        ></v-textarea>
      </v-col>
      <v-card-actions>
        <v-btn @click="createExo">Créer</v-btn>
      </v-card-actions>
    </v-card>
  </div>
</template>

<script>
export default {
  name: 'Admin',
  data() {
    return {
      exo: {
        title: '',
        description: '',
        video: '',
        difficulty: 0,
        member: '',
        type: '',
      },
    }
  },
  methods: {
    async createExo() {
      this.exo.difficulty = parseInt(this.exo.difficulty)
      try {
        await this.$axios
          .post('exercise', this.exo)
          .then(
            (this.exo.title = ''),
            (this.exo.description = ''),
            (this.exo.video = ''),
            (this.exo.difficulty = 0),
            (this.exo.member = ''),
            (this.exo.type = '')
          )
      } catch (e) {
        console.log(e)
      }
    },
  },
}
</script>

<style scoped>
.card {
  margin: 10px;
  max-height: 50%;
  max-width: 100%;
}
</style>
